# lazy-rpi-bluetooth-passthrough

Very lazy implementation of mouse interception using a raspberryPI with a bluetooth module.

This is a **slightly** modified version of: [https://thanhle.me/emulate-bluetooth-mouse-with-raspberry-pi/](https://thanhle.me/emulate-bluetooth-mouse-with-raspberry-pi/)

###   
**Installation (RPI):**

```
wget https://github.com/quangthanh010290/keyboard_mouse_emulate_on_raspberry/blob/master/setup.sh
chmod a+x setup.sh
sudo ./setup.sh
git clone https://github.com/johndongus/lazy-rpi-bluetooth-passthrough/
```

### **Usage:**

Run server script and wait for connection from PC  
`sudo ./emu/server/btk_server.py`  
  
Once connected run this script to enable the mouse / bypass, set your device name to whatever you want in the script  
`sudo ./emu/mouse/mouse_client.py`

Example Usage in bot (python):

```
UDP_IP = "192.168.1.213"
UDP_PORT = 5005
sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM) 
sock.sendto( str.encode(X,Y), (UDP_IP, UDP_PORT))
```

###   
**Issues:**  
[_Edit line 28 in btk\_server.py to change device Name_](https://github.com/johndongus/lazy-rpi-bluetooth-passthrough/blob/759035ece58483a134cfe69ff35e0096f56d249d/btk_server.py#L28)

  
_Cant connect your RPI to your PC via bluetooth after a successful first connection?_  
_Remove the paired device from Windows then on the RPI:_  
``sudo bluetoothctl remove `DEVICEID` ``
