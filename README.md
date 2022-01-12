
```
usage:

ansible-playbook -i inventory/create-cluster create-cluster.yml
ansible-playbook -i inventory/delete-cluster delete-cluster.yml
ansible-playbook -i inventory/scale-up-master scale-up-master.yml
ansible-playbook -i inventory/scale-down-master scale-down-master.yml
ansible-playbook -i inventory/scale-up-node scale-up-node.yml
ansible-playbook -i inventory/scale-down-node scale-down-node.yml
```


待改进：
- 安装keepalived时vip会绑定到非kubeadm init的主机上导致出错
- 没有拷贝/etc/kubernetes/admin.conf到~/.kube/config
- 没有禁止gater_facts，时间较长
- 每个role中install与uninstall两个子role应改成install.yml与uninstall.yml，playbook中应使用include_role或import_role
- kubectl没有像kubelet-kubeadm一样安装指定版本
- 没有去掉master的污点
- 关闭docker的docker0网桥
