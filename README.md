### Commands to improve Ubuntu server's network quality

1. Activate Google BBR network algorithm.
   - `sudo nano /etc/sysctl.conf`
   - At the end of the file, add the following lines:
     - `net.core.default_qdisc=fq`
     - `net.ipv4.tcp_congestion_control=bbr`
   - [Link](https://www.imaginelinux.com/enable-bbr-on-ubuntu-22-04/)

2. Run TCP-Tweaker for some improvements on network settings
  - `bash <(curl -Ls https://github.com/ghorbani-mohammad/ubuntu-network-improvement/blob/main/tcp-tweaker --ipv4)`