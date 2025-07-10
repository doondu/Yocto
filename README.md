# Yocto
This repository contains the artifact for cutom yocto.

## Overveiw of the Artifact
```
yocto  
|---- bitbake_src
|---- bitbake_test
|---- poky
```

## System Requirement (Tested Environment)
#### 1. Hardware
Oracle VM VirtualBox
- 4 CPU
- 4096 MB Memory

#### 2. Software
- Working OS environment: Ubuntu 18.04
- Linux kernel version: 4.15.0-213-generic

#### 3. Dependent packages
```shell
sudo apt install gawk wget git-core diffstat unzip texinfo gcc-multilib build-essential chrpath socat cpio python3 python3-pip python3-pexpect xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa libbsd11.2-dev pylint3 xterm make xsltproc docbook-utils fop dblatex xmlto
```

<br/>

## Get Started
#### 1. Set bitbake path
This setting need to repeat every system reload. If this command going well, you can use `bitbake --version`.
```
export /home/{your username}/bitbake_src/bitbake1.46.0/bin:$PATH
```

#### 2. Use poky to build qemu
- First, clone poky.
```
git clone git://git.yoctoproject.org/poky
git checkout dunfell
```
- Then build the poky source.
```
source poky/oe-init-build-env
```
- After source, YOU NEED TO CHANGE `local.conf` FILE IF YOU DON'T WANT TO BUILD FOREVER
```
/* build/conf/local.conf*/
...
BB_NUMBER_THREAD = "4" // Change number with your CPU spec
PARALLEL_MAKE = "-j4" // too
```
```
/* build/ */
bitbake core-image-minimal -k
```
