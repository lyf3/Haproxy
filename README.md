# 
Haproxy说明：一般用海外服务器的都会遇到线路爆炸，网络不好的情况，这时候连接SSH或者使用55R的时候，会出现连接不上或者速度变慢的问题，为了改善这种状况，我们可以使用haproxy转发端口进行中转加速。

假设你的本地电脑为A，haproxy服务器为B，需要转发的服务器为C。A当然可以直接去连C，但效果可能不会很理想。如果B是一个对C和A连接效果都好的服务器。那么A连接C就等于A连接B，通过B连接C，这样一来，虽然成本有所上升，但却能明显改善网络带宽情况。

安装
系统支持：CentOS，Debian，Ubuntu

使用root登录做中转的那台服务器，执行下面的命令：

wget --no-check-certificate https://www.moerats.com/usr/down/haproxy.sh && bash haproxy.sh
然后会要求你依次输入起始端口、结束端口，需要中专的服务器IP。

卸载方法：
Debian或Ubuntu系统

apt-get -y remove haproxy
CentOS系统

yum -y remove haproxy
然后删掉haproxy的配置文件目录

rm -rf /etc/haproxy
使用命令：
启动：/etc/init.d/haproxy start
停止：/etc/init.d/haproxy stop
重启：/etc/init.d/haproxy restart
状态：/etc/init.d/haproxy status

脚本来源：https://www.gaomingsong.com/480.html

