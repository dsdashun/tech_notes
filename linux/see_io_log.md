# 如何查看系统的IO情况

> sar -f /var/log/sa/sa03 -s 03:00:01 -e 10:10:01 -d -p 

关键参数是-d

## 参数介绍: 
* -d: 它指定要输出的指标，-d表示block device指标
* -p: 它指定输出是pretty-print的
* -s, -e: 开始和结束时间
* -f: 从什么文件读取数据源

如果想查看变化趋势，可以把header和最后的average去掉：
> sar -f /var/log/sa/sa03 -s 03:00:01 -e 10:10:01 -d -p | grep -Ev 'Linux|Average'

## 参考：
man sar
