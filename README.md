# AMap no-libc++ dependency

This project republishes the exact AMap SDK used by `pow-amapall`:

`com.amap.api:navi-3dmap-location-search:11.1.200_3dmap11.1.200_loc11.1.200_sea9.7.4`

The output JAR removes `lib/*/libc++_shared.so` for every ABI. The host application must provide one compatible `libc++_shared.so`; in the ResQ AI app this is provided by Baidu `com.baidu.lbsyun:base:7.6.6`.

## Build

```bash
./gradlew clean assemble
```

The generated artifact is `build/libs/navi-3dmap-location-search-11.1.200-no-libc.1.jar`.

## JitPack

Push this project to a public GitHub repository and create a tag such as `11.1.200-no-libc.1`:

```text
com.github.<github-user>:navi-3dmap-location-search:11.1.200-no-libc.1
```

The tag must be built successfully on JitPack before changing the consuming UTS plugin.
