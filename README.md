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



