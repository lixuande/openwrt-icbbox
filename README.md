## 编译环境下载

下载openwrt的编译环境

```

git clone https://github.com/lixuande/openwrt-icbbox


```

## 驱动下载

可以用社区驱动，也可以用纯净的rt2860v2的驱动，还可以使用带探针的rt2860v2驱动，带探针并不会对无线性能有影响。

### 社区的驱动

```

make menuconfig会启动配置页面，进入kernel的无线驱动下面确认下面三个无线驱动配置项都在
Kernel modules-->Wireless Drivers-->kmod-rt2800-soc
Kernel modules-->Wireless Drivers-->kmod-rt2800-pci
Kernel modules-->Wireless Drivers-->kmod-rt2x00-lib

```

### 纯净的rt2860v2的驱动

```

cd openwrt-icbbox/package/
git clone https://github.com/lixuande/rt2860v2

```

### 带探针的rt2860v2的驱动

```

cd openwrt-icbbox/package/
git clone https://github.com/lixuande/rt2860v2-detect

```
  
## openwrt配置和编译

openwrt配置和更新

```

cd openwrt-icbbox/
./scripts/feeds update -a
./scripts/feeds install -a
make menuconfig

```

openwrt编译

```

make V=99

```
想要快一点，可以这样（如果系统是多核的话，比如4核）

```
make -j4 V=99

```


