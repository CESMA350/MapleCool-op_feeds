**[Pmkol OpenWrt-feeds](https://github.com/pmkol/openwrt-feeds/tree/main)**

---

# 说明

## [MapleCool](https://github.com/pmkol)的OpenWrt插件仓库使用说明

## 注意: 这是代理插件的仓库，仅供学术研究，不可使于非法用途。

# 如何使用

一键命令(防止插件冲突，删除重复)

```yaml
sed -i '1i src-git proxy https://github.com/pmkol/openwrt-feeds/tree/lite-23.05' feeds.conf.default
./scripts/feeds update -a
rm -rf feeds/packages/net/{xray*,v2ray*,v2ray*,sing*}
./scripts/feeds install -a 
make menuconfig
```

---
# 注意:
编译新版Sing-box和hysteria，尽量使用golang版本1.22以上版本。

## 请参照[golang](https://github.com/kenzok8/golang)和[packages_lang_golang](https://github.com/sbwml/packages_lang_golang/tree/25.x)

>在```./scripts/feeds install -a```完成后以下二选一

>@[Kenzo](https://github.com/kenzok8/golang) golang1.24.*

```yaml
rm -rf feeds/packages/lang/golang
git clone https://github.com/kenzok8/golang feeds/packages/lang/golang
```
>@[Sbwml](https://github.com/sbwml/packages_lang_golang) golang 1.25.*

```yaml
rm -rf feeds/packages/lang/golang
git clone https://github.com/sbwml/packages_lang_golang -b 25.x feeds/packages/lang/golang
```

---
## 一键命令(包含常用和代理插件，并删除重复插件与更新go版本)

```yaml
sed -i '1i src-git MapleCool https://github.com/pmkol/openwrt-feeds/tree/extd-23.05' feeds.conf.default
sed -i '2i src-git proxy https://github.com/pmkol/openwrt-feeds/tree/lite-23.05' feeds.conf.default
./scripts/feeds update -a
rm -rf feeds/luci/applications/luci-app-adguardhome
rm -rf feeds/luci/applications/luci-app-smartdns
rm -rf feeds/luci/applications/luci-app-mosdns
rm -rf feeds/packages/net/{alist,adguardhome,mosdns,xray*,v2ray*,v2ray*,sing*,smartdns}
rm -rf feeds/packages/utils/v2dat
./scripts/feeds install -a
rm -rf feeds/packages/lang/golang
git clone https://github.com/sbwml/packages_lang_golang -b 24.x feeds/packages/lang/golang
make menuconfig
```
# 喜欢用无污染和精准IP的DNS over HTTPS/TLS嘛？

MapleCool的[EasyMosDNS](https://github.com/pmkol/easymosdns)项目满足你的需求

如果你喜欢开箱到手即用，麻婆也有提供.

https://afdian.com/a/maplecool

付费赞助下即可使用，一季度仅需一杯星巴克的花费。
---
