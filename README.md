# Installing ns-allinone-2.35 on Ubuntu 20.04(WSL)

## Step 1: Install Basic Libraries

```bash
sudo apt update
sudo apt install nano git build-essential autoconf automake libxmu-dev -y

```

## Step 2: Install `gcc-4.8` and `g++-4.8`

1. Open the sources list:

```bash
sudo nano /etc/apt/sources.list
```

2. Add the following line at the end of the file:

```
deb http://in.archive.ubuntu.com/ubuntu bionic main universe
```

3. Update and install:

```bash
sudo apt update
sudo apt install gcc-4.8 g++-4.8 -y

```

---

## Step 3: Clone repo and build NS2

1. Clone the repo:

```bash
mkdir ~/otp/
cd ~/otp/
git clone https://github.com/hdkhanh462/ns-allinone-2.35-wsl.git

```

2. Build NS2:

```bash
cd ~/otp/ns-allinone-2.35-wsl/
./install

```

---


## Step 4: Set Environment Variables

1. Open `.bashrc`:

```bash
nano ~/.bashrc
```

2. Add the following lines at the end:

```bash
export PATH=$PATH:/root/otp/ns-allinone-2.35-wsl/bin:/root/otp/ns-allinone-2.35-wsl/tcl8.5.10/unix:/root/otp/ns-allinone-2.35-wsl/tk8.5.10/unix
export LD_LIBRARY_PATH=/root/otp/ns-allinone-2.35-wsl/otcl-1.14:/root/otp/ns-allinone-2.35-wsl/lib
```

---

## Step 5: Apply Changes

```bash
source ~/.bashrc
```

---

# Setup to using nam in WSL

## Download & Run VcXsrv

Install VcXsrv.

Launch XLaunch → Choose:

- Multiple windows

- Start no client

- Disable access control (or configure it securely)

Finish and keep it running — this provides the GUI display backend.

## Configure DISPLAY in WSL

```bash
export DISPLAY=:0
```

## Test X11

Before testing `nam`, confirm X11 works:

```bash
sudo apt install x11-apps -y
xclock

```
