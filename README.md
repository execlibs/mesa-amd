**Supported architecture:**

x86-64

**Supported gpus:**

GCN 4 or newer (RX 400/500 series and above)

**Installation:**

extract mesafhs and mesa-amd to any place


**How to use:**

For simple use, you can run the mesa-amd script to launch programs.
For example: /path/to/mesa-amd glxdemo.

If you want to permanently install libraries, you can download "system" package and replace libs in /usr/lib/x86_64-linux-gnu

**Minimum requirements for running:**

All dependencies are the same as in Debian 13, except for libllvm19. It turned out to be unnecessary when building for recent AMD graphics cards.

---
**possible errors:**

Obviously, if you are using an Intel or Nvidia discrete graphics card, you will get a black screen when rebooting. This also applies to permanent installations.

If you have hybrid graphics, you can use only vulkan driver (libvulkan_radeon.so)

**Compilation parameters:**

meson setup -D b_ndebug=true -D microsoft-clc=disabled -D gbm=enabled -D gles2=enabled -D egl=enabled -D android-libbacktrace=disabled -Dbuildtype=release -D b_lto=false -Dprefix=/usr/mesafhs -D llvm=false
and see meson.options file

### Links to the sources

* https://mesa3d.org/
* https://gitlab.freedesktop.org/mesa/mesa
