
Proxy Configuration Guide for npm, apt, and Git

---

1. npm Proxy Setup & Reset

Set npm proxy
npm config set proxy http://127.0.0.1:10808
npm config set https-proxy http://127.0.0.1:10808

Remove npm proxy (reset to default)
npm config delete proxy
npm config delete https-proxy

Check current npm proxy settings
npm config get proxy
npm config get https-proxy

---

2. apt Proxy Setup & Usage

Run apt update with proxy temporarily
sudo apt update -o Acquire::http::Proxy="http://127.0.0.1:3128"

(Replace 127.0.0.1:3128 with your proxy address and port)

Set apt proxy permanently
Create or edit /etc/apt/apt.conf.d/95proxies with:

Acquire::http::Proxy "http://127.0.0.1:3128/";
Acquire::https::Proxy "http://127.0.0.1:3128/";

Remove apt proxy configuration
sudo rm /etc/apt/apt.conf.d/95proxies

---

3. Git Proxy Setup & Reset

Set Git proxy
git config --global http.proxy http://127.0.0.1:10808
git config --global https.proxy http://127.0.0.1:10808

Remove Git proxy (reset to default)
git config --global --unset http.proxy
git config --global --unset https.proxy

Check current Git proxy settings
git config --global --get http.proxy
git config --global --get https.proxy
