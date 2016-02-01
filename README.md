# Aprx for OpenWrt

This will allow you to package [Aprx](http://ham.zmailer.org/oh2mqk/aprx/) for [OpenWrt](https://openwrt.org). Assuming you have the [build system](https://wiki.openwrt.org/about/toolchain) installed, copy the `aprx` folder into `packages` and run `make menuconfig`. You will find `aprx` under the `Network` category.

Alternatively, you can build the `aprx` package alone with:

```bash
make package/arpx/compile
```

Binaries (ready-made packages) are available under the releases tab.

73 de SV1OAN
