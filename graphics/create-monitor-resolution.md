# Create custom resolution 

## 3360 x 1890, 30 f/s

1. Calculate value with command "cvt" or "gft"

  ```shell
  $ cvt 3360 1890 30
  
  # 3360x1890 29.99 Hz (CVT) hsync: 57.74 kHz; pclk: 257.75 MHz
  Modeline "3360x1890_30.00"  257.75  3360 3560 3912 4464  1890 1893 1898 1925 -hsync +vsync
  ```

  What interests us is the following:

  ​	`257.75  3360 3560 3912 4464  1890 1893 1898 1925 -hsync +vsync`

2. `Xrandr` give us information about our monitors. We proceed to add the new mode as follows

  ```shell
  $ xrandr --newmode "3360x1890_30.00"  257.75  3360 3560 3912 4464  1890 1893 1898 1925 -hsync +vsync
  ```

3. Add new mode to HDMI-1

  ```SHELL
  $ xrandr --addmode HDMI-1 3360x1890_30.00
  ```

4. Enable new resolution

  ```shell
  $ xrandr --output HDMI-1 --mode 3360x1890_30.00
  ```

5. We can select new resolution from System > Preferences > Monitors or we can do it from from command line

  ```shell
  $ xrandr -s 3360x1890_30.00
  ```

6. This process is valid only during session, so when rebooting the system the changes don't be saved. To solve this problem we can create a script that runs on startup. Edit file `~/.profile` , add the follow lines at the end.

  ```shell
  # set HDMI-1 new resolution for 4k monitors
  xrandr --newmode "3360x1890_30.00"  257.75  3360 3560 3912 4464  1890 1893 1898 1925 -hsync +vsync
  xrandr --addmode HDMI-1 "3360x1890_30.00"
  xrandr --output HDMI-1 --mode "3360x1890_30.00"
  
  ```

  `/etc/profile` file is loaded for every users, while `~/.profile` is only loaded for the user.