```bash
1、打开三个节点（我的是三个）

①master ②slave1 ③slave2

2、创建密钥

  $ ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa

3、追加密钥到autorized_keys文件，并设置权限

$ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
$ chmod 0600 ~/.ssh/authorized_keys

4、三个节点都进行 2 .3 两步操作之后
5.$ cd ~/.ssh



6.将slave1和slave2中 authorized_keys中的内容全部拷贝到master中的authorized_keys中来

将slave2和master中 authorized_keys中的内容全部拷贝到slave1中的authorized_keys中来

将slave1和master中 authorized_keys中的内容全部拷贝到slave1中的authorized_keys中来

（也就是说任何一个节点的authorized_keys中都有三个节点的秘钥，而且内容还都相同）

7.$ssh master(此处为id地址或者在host中设置的节点名)

最后就发现不用密码可以连接其他节点了
```

