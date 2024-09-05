# Ubuntu_install
> ubuntu-18.04.4 설치 및 설정 관련

### Ubuntu-18.04 부팅 USB 제작
1. [ubuntu-18.04.4desktop-amd4.iso](http://old-releases.ubuntu.com/releases/18.04.4/) download
2. [rufus](https://rufus.ie/en/) 최신버전 download
3. 8GB 이상의 USB 준비 //내부 데이터는 format
4. rufus 실행 </br>
   4-1. 장치: USB
   4-2. 부팅선택: ubuntu.iso
   4-3. 시작 -> ISO 이미지 모드로 쓰기 (권장) -> 확인 -> 완료 후 닫기

### Ubuntu 설치
1. 우분투 부팅 USB 연결 후 PC 시작
2. Try Ubuntu without Installing
3. Welcome: English
4. KeyBoard layout: English(US)-English(US)
5. Wifi connect: BMIL
6. Updates and other software: Normal installation + Download updates while installing Ubuntu
7. Installation type: Erase disk and install Ubuntu
8. Seoul -> name and password
9. Restart Now
10. 부팅 전 USB 제거

### 발생하는 오류
1. 버전 문제 </br>
18.04.4 하위버전은 네트워크 드라이버 탑재 x </br>
18.04.4 상위버전은 설치 오류 발생 </br>
-->18.04.4로 부팅 USB 제작
2. 무한 Login </br>
```
sudo ubuntu-drivers autoinstall
sudo reboot
```
   --> 모든 우분투 드라이버 설치

### 검은 화면 발생 시
1. 시작 시 e 누르기 </br>
```
quit slash nomodeset
```
2. noodeset 추가 후 F10 reboot </br>
3. Terminal에서 아래 명령어 입력 </br>
```
sudo gedit /etc/default/grub
```
4. 내용 추가 </br>
```
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash nomodeset"으로 변경
```
5. grub update </br>
```
sudo update-grub
```
6. reboot </br>

[참고 Link](https://www.dell.com/support/kbdoc/ko-kr/000123893/manual-nomodeset-kernel-boot-linux-%EB%B6%80%ED%8C%85%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%98%B5%EC%85%98%EC%9E%85%EB%8B%88%EB%8B%A4)
### 처음 sudo 사용 시
1. passward 초기화 </br>
```
sudo passwd root
```
2. root 계정으로 들어간 후 sudo 설치 </br>
```
apt install sudo
```
