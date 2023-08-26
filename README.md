### ansible-codes

#### login to ec2 instance

``` bash
ssh -i "blrk-lpc.pem" ec2-user@ec2-54-224-2-239.compute-1.amazonaws.com
```
####  enable password based login

``` bash
sudo vi /etc/ssh/sshd_config
```
####  change the PasswordAuthentication no to yes
``` bash
PasswordAuthentication yes
```
####  start the service and check the status
``` bash
sudo systemctl restart sshd.service 
sudo systemctl status sshd.service 
```
####  copy the ssh key to the aws instance 
``` bash
scp -i blrk-lpc.pem ~/.ssh/id_rsa.pub ec2-user@ec2-54-224-2-239.compute-1.amazonaws.com:~/
```
####  log into aws instance and copy the id to authorised key file
``` bash
cat id_rsa.pub >> .ssh/authorized_keys
```
####  verify the password less login
``` bash
ssh ec2-user@ec2-54-224-2-239.compute-1.amazonaws.com
```

* you can login into ec2 instacne without using the pem key




