# Getting Started

## How to do a Raspberry Pi 4 Model B headless setup

#### 1 - Download Raspbian Buster Lite
---
- [Download Raspbian](https://www.raspberrypi.org/downloads/raspbian/)


> _Note: Python2 and Python3 are pre installed on raspbian_

---
#### 2 - Flash/Burn MicroHSD Card (32GB Recomemded)
---

##### To Burn SD Card On Windows
- [Download Win32DiskImager](https://sourceforge.net/projects/win32diskimager/)


##### To Burn SD Card On MacOS
- [Download Etcher](https://etcher.io/)

---
#### 3 - Boot Raspberry Pi with MicroHSD Card
---
Prerequisites:
- HDMI -> TV/Monitor Screen
- Micro USB Power Cable -> 2A-5V Power Adopter
- USB Keyboard

Login Credentials:
- Login: pi
- Password: raspberry

---
#### 4 - Configure Raspberry Pi
---
```console
pi@raspberry:~ $ sudo raspi-config
```


_Note: Use keyboard Tab key to navigate between options_

##### a) Change Host Name
- 2 Network Options -> N1 Hostname -> N1 -> YOUR-HOST-NAME -> OK

##### b) Enable SSH
- 5 Interfacing Options -> P2 SSH -> Yes -> OK

> _Alternatively_

```console
pi@raspberry:~ $ sudo systemctl enable ssh
pi@raspberry:~ $ sudo systemctl start ssh
```

##### c) - Enable Camera
- 5 Interfacing Options -> P1 Camera -> Yes -> OK

##### d) - Enable Wifi
- 2 Network Options -> N2 Wi-fi -> Select Country -> SSID -> Passphrase -> OK
- 4 Localisation Options -> I4 Change Wi-fi Country -> Select Country -> OK

##### e) - Configure Timezone
- 4 Localisation Options -> I2 Change Timezone -> Select Country -> Select City -> OK

##### f) - Expand Filesystem
- 7 Advanced Options -> A1 Expand Filesystem -> Enter

##### g) - Finish Configuration
- Choose Finish

##### h) - IP Address

```console
pi@raspberry:~ $ ifconfig
```

> _Note: Write down **eth0** and **wlan0** ip addresses_

> _Alternatively_

```console
pi@raspberry:~ $ hostname -I
```

> _Note: Write down first two ips_
