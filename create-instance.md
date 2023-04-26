# New Instance
**Development by:** 
- Findryankp

## Generate SSH
```shell
ssh-keygen -t rsa -f ~/.ssh/KEY_FILENAME -C USERNAME -b 2048
```
ex : ssh-keygen -t rsa -f ~/.ssh/findryanssh -C findryan -b 2048

## GCP
* Choose VM and click Edit
* Add SSH public Key
* Insert your public key (.pub)

## Remote Instance
```shell
ssh -i ~/.ssh/SSH_FILE_NAME USERNAME@ip
```
ex : ssh -i ~/.ssh/findryanssh findryan@111.2.3.4

