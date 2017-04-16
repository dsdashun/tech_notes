# 如何查看系统的性能情况

## 引子：查看系统IO情况

```sh
sar -f /var/log/sa/sa03 -s 03:00:01 -e 10:10:01 -d -p
```

 关键参数是-d

### 参数介绍: 
* -d: 它指定要输出的指标，-d表示block device指标
* -p: 它指定输出是pretty-print的
* -s, -e: 开始和结束时间
* -f: 从什么文件读取数据源, /var/log/sa/sa03表示最近的一个3号的日志

如果想查看变化趋势，可以把header和最后的average去掉：
```sh
sar -f /var/log/sa/sa03 -s 03:00:01 -e 10:10:01 -d -p | grep -Ev 'Linux|Average'
```

## Sar其它重要性能指标

* -r: 查看内存占用
* -R: 查看内存的cache变化情况
* -B: 查看系统的pging情况
* -S: 查看系统的swap情况
* -d: 查看系统各个设备的IO情况

## 参考：

man sar
