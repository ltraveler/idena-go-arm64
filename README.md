# idena-go-arm64 (v0.30.0)
#### 🤖📲 AArch64 aka ARM64 compiled build of idena-go client.
Put simply, the binary that you would need to run IDENA node on your Android phone.

## 🏗️ Some preparation
You must have an ARM64 virtual machine (e.g. QEMU) or real device (e.g. Android device)
* To install Ubuntu on Android you can use (Andronix.app)[https://andronix.app/]
* If you want to emulate ARM64 architecture on your computer you can use (QEMU)[https://www.qemu.org]

## 👨‍💻 In case if you want to compile an ARM64 idena-go build by yourself
1. #### Download and install latest *Ubuntu 18.x LTS* [release](https://cdimage.ubuntu.com/releases/18.04/release/) version for **ARM64** <br> E.g. https://cdimage.ubuntu.com/releases/18.04/release/ubuntu-18.04.6-server-arm64.iso <br>
2. #### Download and install Golang v1.18.6<br>
```
wget https://go.dev/dl/go1.18.6.linux-arm64.tar.gz
tar -xvf go1.18.6.linux-arm64.tar.gz
mv go /usr/local
```
3. #### Installing required gcc library
```
apt install gcc -y
```

4. #### Adding GO required environment variables
```
cd ~/
tee -a .profile <<EOF
#GO required environment variables
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
EOF
```
5. #### Clone latest idena-go repository
```
wget https://github.com/idena-network/idena-go/archive/refs/tags/v0.30.0.tar.gz
tar -xzf v0.30.0.tar.gz
cd idena-go-0.30.0
```
6. #### Get the QUIC implementation (v0.26.0)
```
go get github.com/lucas-clemente/quic-go@v0.26.0
```
7. #### Compile arm64 idena-go binary
```
go build -ldflags "-X main.version=0.30.0"
```
8. #### You can find the compiled ARM64 binary file in the same folder with the name `idena-go`
