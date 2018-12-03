# 1 公共服务

| 公共服务         | 地址                                                         | 说明                                     |
| ---------------- | ------------------------------------------------------------ | :--------------------------------------- |
| 日志Kafka        | IP： 端口：9092                                | 监控             |
| 日志文件Minio    | 文本 <br/>多媒体 | accesskey:minio<br/>Secret Key:123456789 |
| 代理静态配置     |                        | db0                                      |
| 文本静态配置     |                                                              |                                          |
| 性能监控Telegraf | 代理 ??? 端口 8125<br/>文本 ??? 端口 8125<br/>综管 ??? 端口 8125<br/>配置 ??? 端口 8125<br/>加密 1??? 端口 8125<br/>音视频 ??? 端口 8125 |                                          |
| Consul界面     |  同Astana                                                   |  编写、修改配置文件在k18consul-nc中进行                                 |
| Grafana监控界面     | ??                                                          |   用户名:admin<br/>密码:admin                                  |

# 2 性能监控部署说明
InfluxDB 10.0.5.19-20
## 各业务对应telegra及库表名
| 业务类型           | 库表名                                                         | telegraf地址                            |
| -------------------|-------------------------------------------------------------   | :---------------------------------------|
| 代理(天狗&IP复用)  | proxy_stat                                                     | IP： ??? 端口：8125             |
| 文本(asem&DDOS)    | ntc_stat                                                       | IP： ??? 端口：8125             |
| 综管(kafka&storm)  | k18、file                                                      | IP： ??? 端口：8125             |
| 配置(redis&服务C3) | pzff                                                           | IP： ??? 端口：8125             |
| 加密(Diku)         | app_stat                                                       | IP： ??? 端口：8125             |
| 音视频(YSP)        | ysp_stat                                                       | IP： ??? 端口：8125             |
# 3 国家代理部署说明
## 缓存配置文件
 /home/ceiec/tfe/conf/pangu/pangu_pxy.conf

minio_ip_list=10.3.35.1-48;

minio_listen_port=9000

cache_head_main_redis_ip=10.3.35.50

cache_head_redis_iplist=10.3.35.50-52;

cache_head_redis_port=6379