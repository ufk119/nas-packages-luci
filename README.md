# nas-packages-luci
luci for [nas-packages](https://github.com/linkease/nas-packages)

## 使用方法

### 增加feed源

```shell
echo >> feeds.conf.default
echo 'src-git nas https://github.com/linkease/nas-packages.git;master' >> feeds.conf.default
echo 'src-git nas_luci https://github.com/linkease/nas-packages-luci.git;main' >> feeds.conf.default
./scripts/feeds update nas nas_luci
./scripts/feeds install -a -p nas
./scripts/feeds install -a -p nas_luci
```

### 集成软件包

```shell
make menuconfig
```

选择软件包
```plain
LuCI --->
3. Applications --->
<*> luci-app-ddnsto.................................. LuCI support for ddnsto
<*> luci-app-linkease.................................. LuCI support for linkease
```

### 构建固件
```shell
make
```






# 之前的版本quickstart不匹配，导致自编译固件出现某些模块显示不出来的问题。看作者最近修复的此问题，所以赶紧copy了一份，保留。 20220502，v0.3.8。
