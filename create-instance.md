# New Instance
**Development by:** 
- Findryankp

## Generate SSH
```shell
ssh-keygen -t rsa -f ~/.ssh/KEY_FILENAME -C USERNAME -b 2048
```
ex : ssh-keygen -t rsa -f ~/.ssh/findryanssh -C findryan -b 2048

## GCP
1. **Create Instance** on top navbar
2. Choose the configuration what you like
3. Allow HTTP and HTTPs
4. Click **Create**
5. Choose VM and click **Edit**
6. Add SSH public Key
7. Insert your public key (.pub)
8. Save

## AWS
1. On progress

## Remote Instance
```shell
ssh -i ~/.ssh/SSH_FILE_NAME USERNAME@ip
```
ex : ssh -i ~/.ssh/findryanssh findryan@111.2.3.4

