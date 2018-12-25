---
title: "Cài Ubuntu cho Deep Learning"
excerpt: "Cài Ubuntu, gcc, g++,... vân vân và mây mây"

header:
  #teaser: /assets/images/my-personal-website-th.jpg
  overlay_image:  /assets/images/my-personal-website-th.jpg
  overlay_color: "#000"
  overlay_filter: 0.6
  caption: " "

categories:
  - Ubuntu
  - Driver
  - Run

tags:
  - Ubuntu
  - Driver
  - gcc g++
  -
---
Tại đây trình bày theo thứ tự ngược: dùng trước, cài sau, vì cài chỉ 1 lần, dùng mãi

# Run on server from local

- Anaconda Jupyter Notebook: Run Remote Notebook on server from local:

    1. connect Xshell/ ssh to server.
    2. Run On server: (example: 1080ti server)

    ```bash
    conda info --envs
    source activate tf
    jupyter notebook --no-browser --ip=* --port=1234
    jupyter notebook --no-browser --ip=0.0.0.0 --port=1234  
    ```

    (port can be change)    
    result:
    `http://(ubu or 127.0.0.1):1234/?token=113fbcd684007d6a72f8839c94637951d613b136a39b040c`

    3. Run on local:
        - copy that address, paste to local browser
        - change IP address to real IP:

        `http://10.1.53.1:1234/?token=113fbcd684007d6a72f8839c94637951d613b136a39b040c`
        - Enjoy!

    4. Change jupyter notebook password: `jupyter notebook password`.

# Cài Ubuntu xong rồi => cài các thứ liên quan

## Cài driver

Cài cài này phức tạp phết

- Tại máy trạm có thể truy cập vào máy chủ theo cách: `ssh -Y u@10.1.53.1`

- Mở windows driver & software lên: `sudo software-properties-gtk` cài trên này thì được driver ổn định, nhưng không phải là mới nhất.

- Để cài mới nhất:
    - Download file cài về
    - cài gcc, nếu không phải là ver > 7.2.0:
    ```bash
    u@ubu:~$ gcc-7 -v
    Using built-in specs.
    COLLECT_GCC=gcc-7
    COLLECT_LTO_WRAPPER=/usr/lib/gcc/x86_64-linux-gnu/7/lto-wrapper
    OFFLOAD_TARGET_NAMES=nvptx-none
    OFFLOAD_TARGET_DEFAULT=1
    Target: x86_64-linux-gnu
    Configured with: ../src/configure -v --with-pkgversion='Ubuntu 7.2.0-8ubuntu3.2' --with-bugurl=file:///usr/share/doc/gcc-7/README.Bugs --enable-languages=c,ada,c++,go,brig,d,fortran,objc,obj-c++ --prefix=/usr --with-gcc-major-version-only --program-suffix=-7 --program-prefix=x86_64-linux-gnu- --enable-shared --enable-linker-build-id --libexecdir=/usr/lib --without-included-gettext --enable-threads=posix --libdir=/usr/lib --enable-nls --with-sysroot=/ --enable-clocale=gnu --enable-libstdcxx-debug --enable-libstdcxx-time=yes --with-default-libstdcxx-abi=new --enable-gnu-unique-object --disable-vtable-verify --enable-libmpx --enable-plugin --enable-default-pie --with-system-zlib --with-target-system-zlib --enable-objc-gc=auto --enable-multiarch --disable-werror --with-arch-32=i686 --with-abi=m64 --with-multilib-list=m32,m64,mx32 --enable-multilib --with-tune=generic --enable-offload-targets=nvptx-none --without-cuda-driver --enable-checking=release --build=x86_64-linux-gnu --host=x86_64-linux-gnu --target=x86_64-linux-gnu
    Thread model: posix
    gcc version 7.2.0 (Ubuntu 7.2.0-8ubuntu3.2)
    ```

    Cách cài:

    Xem bản gốc [tại đây](https://askubuntu.com/questions/26498/how-to-choose-the-default-gcc-and-g-version) và [tại đây](https://askubuntu.com/questions/949473/installing-gcc-7-2-via-apt)

        1. Remove:
        ```bash
        sudo update-alternatives --remove-all gcc
        sudo update-alternatives --remove-all g++   
        ```

        2. Install:
        ```bash
        sudo env DEBIAN_FRONTEND=noninteractive                                    \
             bash -c 'apt-get install -y python-software-properties lsb-release && \
                    echo -e "Package: gcc-7\\nPin: release n=$(lsb_release -sc)\\nPin-Priority: 990" > /etc/apt/preferences.d/gcc-7 \
                    apt-add-repository -yu ppa:ubuntu-toolchain-r/test &&              \
                    apt-get install -y gcc-7'
        ```
        3. Set Alternative:
        ```bash
        sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-7.2 10
        sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-7.2 10
        sudo update-alternatives --config gcc
        sudo update-alternatives --config g++        
        ```

    - Cài  NVIDIA DRIVER 390.77:

    Tham khảo [tại đây](https://www.elinuxtutorials.com/2018/07/install-nvidia-driver-390-77-on-ubuntu-linuxmint/)

    INSTALL VIA SOURCE FILE

    ```bash
        1. Remove older version of NVIDIA if your graphic is supported
        sudo apt-get purge nvidia*

        2. Reboot the system

        3. Download the Nvidia Driver 390.77
        wget http://us.download.nvidia.com/XFree86/Linux-x86_64/390.77/NVIDIA-Linux-x86_64-390.77.run

        or: https://www.nvidia.com/object/unix.html

        4. Switch to command prompt and stop the running Graphics session
        sudo service lightdm stop
        sudo service gdm stop

        5. Give execute permissions to the installer
        sudo chmod 755 NVIDIA-Linux-x86_64-390.77.run

        6.Install the Nvidia 390.77 driver
        sudo ./NVIDIA-Linux-x86_64-390.77.run
    ```












.
