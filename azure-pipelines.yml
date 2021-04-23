# This pipeline will just build FreeRDP to be sure we dont break

  trigger:
    - working
    
  pool:
    vmImage: 'ubuntu-latest'
    
  steps:
    - checkout: self
  
    - script: sudo apt-get update && sudo apt-get install --no-install-recommends -y
              build-essential
              cmake
              git
              libcairo2-dev
              libcolord-dev
              libdbus-glib-1-dev
              libdrm-dev
              libffi-dev
              libgbm-dev
              libgles2-mesa-dev
              libgstreamer-plugins-base1.0-dev
              libgstreamer1.0-dev
              libinput-dev
              libjpeg-dev
              liblcms2-dev
              libpam-dev
              libpango1.0-dev
              libpixman-1-dev
              libssl-dev
              libsystemd-dev
              libtool
              libudev-dev
              libudev-dev
              libusb-1.0-0-dev
              libva-dev
              libwayland-dev
              libwebp-dev
              libx11-dev
              libx11-xcb-dev
              libxcb-composite0-dev
              libxcb-xkb-dev
              libxcursor-dev
              libxdamage-dev
              libxext-dev
              libxfixes-dev
              libxi-dev
              libxinerama-dev
              libxkbcommon-dev
              libxkbfile-dev
              libxml2-dev
              libxrandr-dev
              libxrender-dev
              libxtst-dev
              libxv-dev
              lsb-release
              meson
              ninja-build
              pkg-config
              software-properties-common
              squashfs-tools
              uuid-dev
              wayland-protocols
              wget 
      displayName: 'Install Dependencies'
    
    - script: cmake -G Ninja
            -B build
            -DCMAKE_INSTALL_PREFIX=/usr/local 
            -DCMAKE_INSTALL_LIBDIR=/usr/local/lib 
            -DCMAKE_BUILD_TYPE=RelWithDebInfo 
            -DWITH_SERVER=ON 
            -DWITH_CHANNEL_GFXREDIR=ON 
            -DWITH_CHANNEL_RDPAPPLIST=ON 
            -DWITH_CLIENT=OFF 
            -DWITH_CLIENT_COMMON=OFF 
            -DWITH_CLIENT_CHANNELS=OFF 
            -DWITH_CLIENT_INTERFACE=OFF 
            -DWITH_PROXY=OFF 
            -DWITH_SHADOW=OFF 
            -DWITH_SAMPLE=OFF 
      displayName: 'CMake (Ninja)'
    
    - script: ninja -C build -j8
      displayName: 'Ninja build'
    
