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
2. Set name of your instance
3. Set **Boot disk**
4. Choose the configuration what you like
5. Allow HTTP and HTTPs
6. Click **Create**
7. Choose VM and click **Edit**
8. Add SSH public Key
9. Insert your public key (.pub)
10. Save

## AWS
1. On progress

## Remote Instance
```shell
ssh -i ~/.ssh/SSH_FILE_NAME USERNAME@ip
```
ex : ssh -i ~/.ssh/findryanssh findryan@111.2.3.4

