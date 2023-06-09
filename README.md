# btpanel-v7.7.0
btpanel-v7.7.0-backup  官方原版v7.7.0版本面板备份

**Centos/Ubuntu/Debian安装命令 独立运行环境（py3.7）**

```Bash
curl -sSO https://raw.githubusercontent.com/hczjl/btpanel-v7.7.0/main/install/install_panel.sh && bash install_panel.sh
```

**备用安装链接，适用于不能访问GitHub的服务器。文件公开存放在[d.moe.ms](http://d.moe.ms/?btpanel-v7.7.0)**

```
curl -sSO http://d.moe.ms/AAAAA/btpanel-v7.7.0/install/install_panel.sh && bash install_panel.sh
```

# 手动破解：

1. 屏蔽手机号

```
sed -i "s|bind_user == 'True'|bind_user == 'XXXX'|" /www/server/panel/BTPanel/static/js/index.js
```

2. 删除强制绑定手机js文件

```
rm -f /www/server/panel/data/bind.pl
```

3. 手动解锁宝塔所有付费插件为永不过期

文件路径：`/www/server/panel/data/plugin.json`

搜索字符串：`"endtime": -1`全部替换为`"endtime": 999999999999`

4. 给plugin.json文件上锁防止自动修复为免费版

```
chattr +i /www/server/panel/data/plugin.json
```

============================

！！如需取消屏蔽手机号

```
sed -i "s|if (bind_user == 'REMOVED') {|if (bind_user == 'True') {|g" /www/server/panel/BTPanel/static/js/index.js
```

# 一键脚本

1. 一键优化脚本

```shell
wget -O optimize.sh https://raw.githubusercontent.com/hczjl/btpanel-v7.7.0/main/optimize.sh && bash optimize.sh
```

2. 一键开心

```shell
curl -sSO https://raw.githubusercontent.com/hczjl/btpanel-v7.7.0/main/one_key_happy.sh && bash one_key_happy.sh
```

3. 优化开心二合一脚本

```shell
curl -sSO https://raw.githubusercontent.com/hczjl/btpanel-v7.7.0/main/one_key_optimize.sh && bash one_key_optimize.sh
```

# 网络错误可以改hosts文件试试

```bash
nano /etc/hosts
```
```text
199.232.68.133 raw.githubusercontent.com
199.232.68.133 user-images.githubusercontent.com
199.232.68.133 avatars2.githubusercontent.com
199.232.68.133 avatars1.githubusercontent.com
```

