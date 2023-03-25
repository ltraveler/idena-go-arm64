# idena-go-arm64 (v1.0.2)
#### 🤖📲 AArch64 aka ARM64 compiled build of idena-go client.
Put simply, the binary that you would need to run IDENA node on your Android phone.

## 🏗️ User guide
You must have an ARM64 virtual machine (e.g. QEMU) or real device (e.g. Android device)<br><br>
🇬🇧 [https://medium.com/@idna.project/b9229c010440](https://medium.com/@idna.project/b9229c010440)<br>
🇷🇺 [https://teletype.in/@idenanetwork/idena-armer](https://teletype.in/@idenanetwork/idena-armer)

## 👨‍💻 In case if you want to compile an ARM64 idena-go build by yourself
1. #### Download and install latest *Ubuntu 18.x LTS* [release](https://cdimage.ubuntu.com/releases/18.04/release/) version for **ARM64** <br> E.g. https://cdimage.ubuntu.com/releases/18.04/release/ubuntu-18.04.6-server-arm64.iso <br>

2. #### Installing required packages
```
apt install gcc wget git -y
```

3. #### Download and install Golang v1.17.13<br>
```
wget https://go.dev/dl/go1.17.13.linux-arm64.tar.gz
tar -xvf go1.17.13.linux-arm64.tar.gz
mv go /usr/local
```

4. #### Adding GO required environment variables
```
cd ~/
tee -a .profile <<'EOF'
#GO required environment variables
GOROOT=/usr/local/go
GOPATH=$HOME/go
PATH=$GOPATH/bin:$GOROOT/bin:$PATH
EOF
source ~/.profile

```

5. #### Clone latest idena-go repository
```
wget https://github.com/idena-network/idena-go/archive/refs/tags/v1.0.2-rc3.tar.gz
tar -xzf v1.0.2.tar.gz
cd idena-go-v1.0.2
```

6. #### Compile arm64 idena-go binary
```
go build -ldflags "-X main.version=1.0.2"
```

7. #### You can find the compiled ARM64 binary file in the same folder with the name `idena-go`

### 🙏 Special Thanks
to Rioda for his [rasberry-pi](https://github.com/rioda-org/idena/tree/main/raspberry_pi) script
