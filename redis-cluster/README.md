# ansible-playbook

1. 集群最少是6个节点，3个主作切片,另外3个作副本
2. 需要注意的是,每个分片至少需要一个副本,否则集群无法正常初始化
3. 支持的redis版本仅为4.0.9
4. 修改host文件里IP地址以及你要设置的端口,其余redis参与都在group_vars文件夹all变量文件里,可以根据实际情况修改。
5. 删除原来redis集群，去掉注释执行：ansible-playbook -i hosts site.yml --tags clear
6. 后期想部署和清除集群，可以在hosts建立不同名字即可


# 无密码配置
删除requirepass变量即可


# 操作命令

ansible-playbook -i hosts site.yml --tags clear \\只执行clear

ansible-playbook -i hosts site.yml \\下发部署