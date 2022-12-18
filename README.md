# Team: SharpShooter

## Title

Outdoor Long Range Ubiquitous Projectiles Tracking System Using LoRa and Computer Vision

### Group Members

| Name             | University                 | Department                                   | Email                 | Contact                           |
| ---------------- | -------------------------- | -------------------------------------------- | --------------------- | --------------------------------- |
| Donghyeon Na     | Sangmyung University       | Dept. of Human Centered AI                   | skehdgus401@gmail.com | https://github.com/xialGuri       |
| Hansu Jeong      | Sangmyung University       | Dept. of Computer Science                    | 7471919@naver.com     | https://github.com/8471919        |
| Minjae Kim       | KyungHee University        | Dept. of Software Convergence                | kmj5596@khu.ac.kr     | https://github.com/MinJaeKim2796  |
| Jeongwon Moon    | Kyungpook Nat’l University | Dept. of Computer Science & Engineering      | bella7365@knu.ac.kr   | https://github.com/gaarden        |
| Woojin Choi      | Sun Moon University        | Dept. of Computer Science & Engineering      | twinsno119@gmail.com  | https://github.com/woojin-choi518 |
| Ethan O'Sullivan | Purdue University          | Dept. of Computer and Information Technology | ethanext17@gmail.com  | https://github.com/ethanext       |
| Sophia Kim       | Purdue University          | Dept. of Computer and Information Technology | phia9130@gmail.com    | https://github.com/lee3155        |

---

## Problem Statement

Shotmarker is a program designed for a F-class shooting competition, which is conducted from 300 to 1000 yards only using prone position. This system has several complications, initially, it is overpriced. Secondly, this system depends on environmental factors such as wind and rain. The average error in an ideal state is within 2~3mm, but an error rate can be higher when the weather is not at its best for shooting. Lastly, this system is dedicated to a specific type of gun, a gun that uses supersonic bullet. In other words, if the gun does not use a supersonic bullet Shotmarker is not functional. For the gunshot detection, ShotSpotter is used to detect gunshots in cities such as New York and Chicago, however it has a low accuracy issue. In effect, around 50,000 alerts for probable gunshots has been notified with only 9.1% resulting in evidence of a gun-related offense. Also, LoRa is the fastest growing technology that researchers are interested in these days, the benefits of LoRa are long battery life, long distance communication, and low cost of the application. However, LoRa is not the best in outdoors because there are chances of having packet loss using LoRa due to various environmental factors.

## Novelty

This program presents a new approach to the projectile mark detecting system. The proposed system shows high accuracy without any environmental constraints by using LoRa, Computer Vision and sound detection. Similarly to Shotmarker, this system uses LoRa networks to facilitate at a long-range. However, transmitting large data using LoRa, takes a while due to low power. Therefore, instead of transmitting an image or video, this system transmits coordinates. Also, unlike ShotSpotter, the proposed module starts only when a gun shot sound is detected; this method is also cost-effective. Therefore, the gunshot detection system that derives high accuracy is developed by this program. In this program, the proposed system applies the handshaking algorithm to ensure that transferring data is successful. Additionally, this algorithm is beneficial when LoRa network transfers large data such as images or videos.

## Project Overview

<img align="center" width="800" alt="도식화" src="https://user-images.githubusercontent.com/77319785/196273713-43df42f2-068c-4285-ab9c-fec79f087b1b.png">

## ~Environment Settings~ -> Technologies used

| Division        | Stack                                                                                                                                                                                                                                                                                                                             |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Client          | <img src="https://img.shields.io/badge/React-blue?style=for-the-badge&logo=React&logoColor=61DAFB">                                                                                                                                                                                                                               |
| Server          | <img src="https://img.shields.io/badge/NodeJs-green?style=for-the-badge&logo=Node.js&logoColor=339933"/> <img src="https://img.shields.io/badge/Express-grey?style=for-the-badge&logo=Express&logoColor=000000"/> <img src="https://img.shields.io/badge/TypeScript-black?style=for-the-badge&logo=TypeScript&logoColor=3178C6"/> |
| Code Management | <img src="https://img.shields.io/badge/git-F05032?style=for-the-badge&logo=git&logoColor=black"/> <img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white"/>                                                                                                                         |
| Formatting      | <img src="https://img.shields.io/badge/prettier-F7B93E?style=for-the-badge&logo=prettier&logoColor=black"> <img src="https://img.shields.io/badge/ESLint-purple?style=for-the-badge&logo=ESLint&logoColor=4B32C3">                                                                                                                |
| Computer Vison  | <img src="https://img.shields.io/badge/OpenCV-purple?style=for-the-badge&logo=OpenCV&logoColor=5C3EE8"/> <img src="https://img.shields.io/badge/Python-skyblue?style=for-the-badge&logo=Python&logoColor=3776AB"/>                                                                                                                |
| IoT             | <img src="https://img.shields.io/badge/Raspberry Pi-red?style=for-the-badge&logo=Raspberry Pi&logoColor=A22846">                                                                                                                                                                                                                  |
| Deep Learning   | <img src="https://img.shields.io/badge/Python-blue?style=for-the-badge&logo=Python&logoColor=3776AB"/> <img src="https://img.shields.io/badge/Pytorch-Gray?style=for-the-badge&logo=Pytorch&logoColor=EE4C2C"/>                                                                                                                   |

## Environment

### Raspberry pi 1 (For camera)
- This Raspberry pi is placed near by target.

- Raspberry pi model : Raspberry pi 4B 8G RAM

- LoRa Hat : Waveshare SX1262 915M LoRa HAT(915M model is for USA)

- Camera : Raspberry pi HQ Camera

- OS : Raspberry pi OS 64bit(Raspbian)

- Language : Python(3.9.2)

- **Before you read, you should make a directory for setting and all cloned files/directories must be in that directory.**

**Camera Setting**

1. put camera into Raspberry pi
2. After turn on Raspberry pi, Menu -> Preferences -> Raspberry pi configuration -> Interfaces -> select `Camera : Enable`

**LoRa Hat Setting**

1. Set the LoRa mode using jumpers
  - Using the Yellow jumpers on photo, place the jumper like photo.
  <img width="474" alt="LoRa hat" src="https://user-images.githubusercontent.com/27190776/208315417-e3962ef9-8917-48e3-ab4b-d9282e87832e.png">

2. Enable Serial port
  - In terminal, run command `sudo raspi-config` -> Interfacing Options -> Serial -> No -> Yes

**LoRa Setting**

1. Install Python version 3.9.2

2. clone the LoRa(pi1) code from Github.

```linux
git clone https://github.com/Purdue-K-SW-Capstone/SharpShooter-pi1
```

3. change working directory
```
cd SharpShooter-pi1
```

4. Install python dependencies
```
pip install -r requirements.txt
```

5. Run
```
python main.py
```


### Raspberry pi 2 (For sound sensor)
- This Raspberry pi is placed near by shooter.

- Raspberry pi model : Raspberry pi 4B 8G RAM

- LoRa Hat : Waveshare SX1262 915M LoRa HAT(915M model is for USA)

- Microphone : HP-DK40(SIZHENG)

- OS : Raspberry pi OS 64bit(Raspbian)

- Language : Python(3.7.15), Node.js(16.17.1)

- **Before you read, you should make a directory for setting and all cloned files/directories must be in that directory.**

- **Every setting must be run in separate terminal window

**Microphone setting**
- just put microphone into Raspberry pi

**Access Point(Wifi generator) Setting**



**LoRa Hat Setting**

1. Set the LoRa mode using jumpers
  - Using the Yellow jumpers on photo, place the jumper like photo.
  <img width="474" alt="LoRa hat" src="https://user-images.githubusercontent.com/27190776/208315417-e3962ef9-8917-48e3-ab4b-d9282e87832e.png">

2. Enable Serial port
  - In terminal, run command `sudo raspi-config` -> Interfacing Options -> Serial -> No -> Yes

**Server setting**
- Server is made with node.js.
- In server, There are many secret keys. so, If you want to set the server, Please ask us to get `.env`file.
- `.env`file must be placed on root directory(SharpShooter-Server directory)

1. Install node.js version 16.17.1

2. clone the server code from Github
```
git clone https://github.com/Purdue-K-SW-Capstone/SharpShooter-Server
```

3. change working directory
```
cd SharpShooter-Server
```

4. Install node.js dependencies
```
npm install
```

5. Run
```
npm start
```

**LoRa Setting**
- In LoRa, There are many secret keys. so, If you want to set the LoRa, Please ask us to get `.env`file.
- `.env`file must be placed on root directory(SharpShooter-pi2 directory)
- Before setting this, You must finish Server setting first.

1. Install python version 3.7.15

2. clone the LoRa(pi2) code from Github
```
git clone https://github.com/Purdue-K-SW-Capstone/SharpShooter-pi2
```

3. change working directory
```
cd SharpShooter-pi2
```

4. Install python dependencies
```
pip install -r requirements.txt
```

5. Run
```
python main.py
```

**Client server setting**
- Client server is made with react.
- In client server, There are many secret keys. so, If you want to set the client server, Please ask us to get `.env`file.
- `.env`file must be placed on root directory(SharpShooter-Front directory)
- Before setting this, You must finish Server setting first.

1. Install node.js version 16.17.1

2. clone the front code from Github
```
git clone https://github.com/Purdue-K-SW-Capstone/SharpShooter-Front
```

3. change working directory
```
cd SharpShooter-Front
```

4. Install node.js dependencies
```
npm install
```

5. Run
```
npm start
```

