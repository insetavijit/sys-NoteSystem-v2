

| Tool                  | Purpose                                      | Use Case                                     |
| --------------------- | -------------------------------------------- | -------------------------------------------- |
| **netselect-apt**     | Finds fastest Debian mirror automatically    | Optimize package download speeds             |
| **net-tools**         | Basic networking commands (`ifconfig`, etc.) | Inspect and troubleshoot network interfaces  |
| **curl**              | Transfer data from URLs (HTTP, FTP, etc.)    | Download/upload data, API testing, scripting |
| **wget**              | Non-interactive downloader                   | Download files or websites                   |
| **dnsutils**          | DNS query tools (`dig`, `nslookup`)          | Troubleshoot DNS, check DNS records          |
| **traceroute**        | Trace packet route to a host                 | Diagnose network routing issues              |
| **nmap**              | Network scanner and security tool            | Scan networks for open ports and devices     |
| **tcpdump**           | Packet capture and analysis                  | Inspect network traffic for troubleshooting  |
| **iputils-ping**      | Ping command                                 | Check host connectivity and latency          |
| **htop**              | Interactive process viewer                   | Monitor system resources and processes       |
| **unzip**             | Extract `.zip` archives                      | Decompress downloaded files                  |
| **tree**              | Visual directory tree display                | Visualize folder structures                  |
| **locate**            | Fast file search using indexed database      | Quickly find files by name                   |
| **ack**               | Code-search tool (better grep)               | Search source code efficiently               |
| **silversearcher-ag** | Faster alternative to `ack`                  | Very fast code searching in large projects   |
| **git**               | Distributed version control system           | Track and manage source code changes         |



## Installing bassic tools -

```bash
sudo apt update && sudo apt install -y netselect-apt net-tools curl wget dnsutils traceroute nmap tcpdump iputils-ping htop unzip tree locate ack silversearcher-ag autojump git

```
---
## Refreshing the mirror List
### Search for best mirror with [[netselect-apt]] 

1. **Scan for best Mirror**  ` sudo netselect-apt bullseye `
2. **Back up Current Mirror List** `sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak.$(date +%Y%m%d%H%M%S) `
3. **Choosing a Mirror** `sudo netselect-apt bullseye`
4. **Edit Source. List**  `sudo nano /etc/apt/sources.list`
### Suggested deafult Mirror List

### Suggested Mirror List

```bash
# Debian packages for stable
deb http://ftp.es.debian.org/debian/ stable main contrib
# Uncomment the deb-src line if you want 'apt-get source'
# to work with most packages.
# deb-src http://ftp.es.debian.org/debian/ stable main contr>
# Security updates for stable
deb http://security.debian.org/ stable-security main contrib
```

-----

# Customize look and feel

### install Zsh
***its already installed in bassic tolls installation part***	
Now setup Instructions
1. Set it ` chsh -s $(which zsh) `
2. Download [[Oh-My-Zsh]] And Flow Steps`sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"` 
3. Download Plugins & add them in `nano ~/.zshrc` then  `source ~/.zshrc`

```Bash

git clone https://github.com/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
#
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

```

## install Neovim [[Neovim Setup with NvChad]]
