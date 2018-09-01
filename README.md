# Prometheus-Alertmanager
这不是个完整的监控项目，是本地测试要使用上线的一个项目！

1.收报警渠道有三个（微信，钉钉，邮件）

#微信<br/>
得申请企业微信号后得到id配置在prometheus_alert_config_map.yaml文件里既可!



#钉钉<br/>
创建个钉钉收报警的群后再改群里创建个机器人把给的url写到prometheus-webhook-dingtalk.yaml文件里即可！



#邮件<br/>
邮件开通IMAP4服务/SMTP服务后在prometheus_alert_config_map.yaml文件里既可!



#部署grafana时首先在一台node上打标签，因为为了bashboard的json文件的数据持久化没用共享存储所以用了下策<br/>
kubectl label nodes 192.168.10.1  LB=grafana



所有的访问模式只用了nodePort方式访问，创建完成后请看一下service端口再访问！


1：主机系统：CentOS Linux release 7.5.1804 (Core)
2：系统只配置了IP，并且能联网，其他无任何配置
3：ansible服务器已经和所有节点做了root用户免密码登陆
4: 所有执行均采用root用户
5：github下载地址：https://github.com/xiaotian45123/ansible-k8s10x_and_k8s11x
6：安装测试通过的K8S版本有：1.10.3、1.10.4、1.10.5、1.11.0、1.11.1，其他版本请大家自行测试
7：在阿里云不能使用阿里云得SLB服务代替keepalived+haproxy，因为阿里云的SLB不支持后端真实服务器既做服务端又做客户端，我研究过阿里云K8S部署脚本，阿里云SLB只做node节点kebelet访问master的负载功能
8：本ansible一键安装可用于生产环境
9：同时欢迎大家改进并提交到github,这个我后期一直会维护，由于不太会用github，所以大家有问题也可以先留言
