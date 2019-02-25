# ARM-Lab
```
Imagen ISO:

Full on GDrive: https://drive.google.com/file/d/1uX9fRUX-IHitQVD43QUsz9Aocy8pJ8XK/view?usp=sharing
Full on Mega.nz: https://mega.nz/#!1K4k1T5a!hGNAUNbTktPB69dOMRpOT-y2znlIB8LQ1twTp90Uu8s
Split on Mega.nz: https://mega.nz/#F!AO5j0ZCJ!ltZHLnXtpLccI4kkr-j2Xw
Split on GDrive: https://drive.google.com/drive/folders/1p_XdsiVVSGk-LLtSFOov1H1y8z7g_SeK?usp=sharing

Password: azerialabs

------------------------------------

VMWARE Adaptador: (Detección Automática)

Ubuntu Server:
sudo apt-get install uml-utilities
sudo tunctl -t tap1 -u user
sudo ifconfig tap1 172.16.0.1/24

sudo qemu-system-arm -kernel /arm/images/raspbian/kernel-qemu-4.4.34-jessie -cpu arm1176 -m 256 -M versatilepb -serial stdio -append "root=/dev/sda2 rootfstype=ext4 rw" -hda /arm/images/raspbian/raspbian.img -net nic -net tap,ifname=tap1,script=no,downscript=no -no-reboot

Pi:
sudo ifconfig eth0 172.16.0.2/24

-----TUNEL-----

sudo apt-get install ssh; service ssh start

Ubuntu to Pi:
ssh -L 1337:127.0.0.1:23946 pi@172.16.0.2 

Windows to Ubuntu:
ssh -L 1337:127.0.0.1:1337 user@192.168.0.178
P: toor

Config IDAPro :)


-----------------SOLUCIONA-LA-VIDA-OP1-----------------


INSTALL
sudo apt-get install qemu-user gcc-aarch64-linux-gnu
sudo apt install qemu-user-static

(dbg Server port 1337)
# qemu-aarch64-static -strace -g 1337 pseudo


-----------------SOLUCIONA-LA-VIDA-OP2------------------


https://thinkingeek.com/2016/10/08/exploring-aarch64-assembler-chapter1/

INSTALL
sudo apt-get install qemu-user gcc-aarch64-linux-gnu
sudo apt install qemu-user-static


EJEMPLO
**************************
#include <stdio.h>
 
int main(int argc, char *argv[])
{
  printf("Hello AArch64!\n");
  return 0;
}
**************************


COMPILACION
$ aarch64-linux-gnu-gcc -static -o hello hello.c

EJECUCION
./hello
```
