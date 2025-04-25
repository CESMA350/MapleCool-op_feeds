**[Pmkol OpenWrt-feeds](https://github.com/pmkol/openwrt-feeds/tree/main)**

---

# 说明

## [MapleCool](https://github.com/pmkol)的OpenWrt插件仓库使用说明
* 该插件库适用于OpenWrt23.05版本，其他版本请自行测试。
* 插件库自动跟随各大佬更新，需自行添加编译

---
# 使用

一键命令

```yaml
sed -i '1i src-git MapleCool https://github.com/pmkol/openwrt-feeds/tree/extd-23.05' feeds.conf.default
./scripts/feeds update -a
rm -rf feeds/luci/applications/luci-app-adguardhome
rm -rf feeds/luci/applications/luci-app-smartdns
rm -rf feeds/luci/applications/luci-app-mosdns
rm -rf feeds/packages/net/{alist,adguardhome,mosdns,smartdns}
rm -rf feeds/packages/utils/v2dat
./scripts/feeds install -a 
make menuconfig
```

---
# 若遇到编译报错提示go版本低

## 请参照[packages_lang_golang](https://github.com/sbwml/packages_lang_golang/tree/24.x)

以下是适用于23.x的命令

```yaml
rm -rf feeds/packages/lang/golang
git clone https://github.com/sbwml/packages_lang_golang -b 23.x feeds/packages/lang/golang
```

---
## 一键命令

```yaml
sed -i '1i src-git MapleCool https://github.com/pmkol/openwrt-feeds/tree/extd-23.05' feeds.conf.default
./scripts/feeds update -a
rm -rf feeds/luci/applications/luci-app-adguardhome
rm -rf feeds/luci/applications/luci-app-smartdns
rm -rf feeds/luci/applications/luci-app-mosdns
rm -rf feeds/packages/net/{alist,adguardhome,mosdns,smartdns}
rm -rf feeds/packages/utils/v2dat
rm -rf feeds/packages/lang/golang
git clone https://github.com/sbwml/packages_lang_golang -b 23.x feeds/packages/lang/golang
./scripts/feeds install -a 
make menuconfig
```

---

### 你也喜欢看麻婆女装？
快快加入tg群围观

[DNS交流群](https://t.me/+VeV5wt1E6FA5Ue-x)
MapleCool的[博客](https://apad.pro/)
MapleCool的[openwrt-lite](https://github.com/pmkol/openwrt-lite)项目
