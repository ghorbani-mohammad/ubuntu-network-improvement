### Commands to improve Ubuntu server's network quality

1. Activate Google BBR network algorithm.
   - `sudo nano /etc/sysctl.conf`
   - At the end of the file, add the following lines:
     - `net.core.default_qdisc=fq`
     - `net.ipv4.tcp_congestion_control=bbr`
   - [Link](https://www.imaginelinux.com/enable-bbr-on-ubuntu-22-04/)

2. Run TCP-Tweaker for some improvements on network settings
  - `bash <(curl -Ls https://raw.githubusercontent.com/ghorbani-mohammad/ubuntu-network-improvement/main/tcp-tweaker --ipv4)`
  - You can see configurations on `/etc/sysctl.conf` file

3. Set configurations on sshd_config
   - `nano /etc/ssh/sshd_config`
   - At the end of the file, add the following lines:
     - `ClientAliveInterval=600`
     - `ClientAliveCountMax=3`
