### AWS-aware ssh wrapper

ssh to a host using ec2_tag_Name, ipaddr or instance-id:
  - assh dev-docker1
  - assh 172.31.1.2
  - assh i-1234abcd

ssh to multiple hosts one by one
  - assh dev-app?
  - assh dev-app* prod-app1 172.31.1.2 i-1234abcd 172.31.2.3

pass ssh params and execute remote commands sequensionally
  - assh dev-docker1 -- -i ~/.ssh/key.pem -l username
  - assh dev-docker* -- 'hostname'

tmux mode: open all the hosts as tmux panes
  - assh prod-app* -t
  - assh prod-app* -t -- 'tail -f /var/log/*-service/app.log | grep ERROR'

TODO:
fabric mode: parallel remote command execution


### Requirements
aws cli, tmux (for -t mode)
