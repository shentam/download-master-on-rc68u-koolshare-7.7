# download-master-on-rc68u-koolshare-7.7

在/jffs/scripts目录下增加firewall-start文件【chmod +755 firewall-start】，或者直接在nat-start、wan-start文件中增加一段脚本：

sh username@192.168.2.1
password
vi /jffs/script/firewall-start


para_old=`nvram get rc_support`
install_appnet_flag=$(echo $para_old | grep appnet)
if [[ "$install_appnet_flag" != "" ]]
then
    echo "已安装appnet(download master)，无需处理!"
else
    para_new=${para_old}" appnet"
    nvram set rc_support="${para_new}"
fi
esc, :wq
重启后dm就不会消失，但是需要install一下。
