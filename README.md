**Supported gpus:**

GCN 4 architecture or newer (RX 400/500 series and above)

**Installation:**

copy mesafhs dir in /usr, mesa-amd in /bin, radeon_icd.x86_64.json in /usr/share/vulkan/icd.d If such a file exists, simply overwrite it.


**How to use:**
There are two general ways to use it.

For simple use, you can run the mesa-amd script to launch programs.
For example: mesa-amd wine64 explorer.

If you want to permanently install libraries, you can copy zzZ_mesa-amd.conf to /etc/ld.so.conf.d and then enter ldconfig in the terminal. This will allow ld.so to overwrite libraries when called, without affecting the system.

**Minimum requirements for running:**

All dependencies are the same as in Debian 13, except for libllvm19. It turned out to be unnecessary when building for recent AMD graphics cards.

---
**possible errors:**

Obviously, if you are using an Intel or Nvidia discrete graphics card, you will get a black screen when rebooting.

If you have hybrid graphics, you can use only vulkan driver (libvulkan_radeon.so)

**Compilation parameters:**

meson setup -D b_ndebug=true -D microsoft-clc=disabled -D gbm=enabled -D gles2=enabled -D egl=enabled -D android-libbacktrace=disabled -Dbuildtype=release -D b_lto=false -Dprefix=/usr/mesafhs -D llvm=false
and meson.options file

### Links to the sources

* https://mesa3d.org/
* https://gitlab.freedesktop.org/mesa/mesa
