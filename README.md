## [MapleCool](https://github.com/pmkol)的[OpenWrt插件仓库](https://github.com/pmkol/openwrt-feeds/tree/extd-23.05)使用说明

# 使用方法

一键命令（防止插件冲突，删除重复）

```yaml
sed -i '1i src-git MapleCool https://github.com/pmkol/openwrt-feeds/tree/extd-23.05' feeds.conf.default
./scripts/feeds update -a
rm -rf feeds/luci/applications/luci-app-adguardhome
rm -rf feeds/luci/applications/luci-app-smartdns
rm -rf feeds/luci/applications/luci-app-mosdns
rm -rf feeds/packages/net/{adguardhome,mosdns,smartdns}
rm -rf feeds/packages/utils/v2dat
./scripts/feeds install -a 
make menuconfig
```

---
# 若遇到编译报错提示Go版本低

请参照以下方式解决

>在```./scripts/feeds install -a```完成后以下二选一

>@[KenzoK8](https://github.com/kenzok8/golang) golang1.24.*

```yaml
rm -rf feeds/packages/lang/golang
git clone https://github.com/kenzok8/golang feeds/packages/lang/golang
```
>@[sbwml](https://github.com/sbwml/packages_lang_golang) golang 1.25.*

```yaml
rm -rf feeds/packages/lang/golang
git clone https://github.com/sbwml/packages_lang_golang -b 25.x feeds/packages/lang/golang
```

---
## 一键命令（包含删除重复插件和更新go版本）

```yaml
sed -i '1i src-git MapleCool https://github.com/pmkol/openwrt-feeds/tree/extd-23.05' feeds.conf.default
./scripts/feeds update -a
rm -rf feeds/luci/applications/luci-app-adguardhome
rm -rf feeds/luci/applications/luci-app-smartdns
rm -rf feeds/luci/applications/luci-app-mosdns
rm -rf feeds/packages/net/{alist,adguardhome,mosdns,smartdns}
rm -rf feeds/packages/utils/v2dat
./scripts/feeds install -a 
rm -rf feeds/packages/lang/golang
git clone https://github.com/sbwml/packages_lang_golang -b 24.x feeds/packages/lang/golang
make menuconfig
```

---

### 你也喜欢看麻婆女装？
快快加入tg群围观

[DNS交流群](https://t.me/+VeV5wt1E6FA5Ue-x)

MapleCool的[博客](https://apad.pro/)

MapleCool的[openwrt-lite](https://github.com/pmkol/openwrt-lite)项目
