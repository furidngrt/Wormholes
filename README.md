# Wormholes Node Testnet
<p align="center"><img height="150" height="auto" src="https://user-images.githubusercontent.com/63885192/212291690-c2abc119-babe-4238-836a-8da3f788c3eb.png"></p>

### Software/OS Requirements

| Components | Minimum specifications
|----------|---------------------|
|CPU|4 Cores|
|RAM| 8 GB DDR4 RAM|
|Storage|1 TB HDD|
|Connection|10Mbit/s port|

| Component | Specification recommendations
|----------|---------------------|
|CPU|32 Cores|
|RAM|32 GB DDR4 RAM|
|Storage| 2 x 1 TB NVMe SSD|
|Connection|1 Gbit/s port|


### install docker
```
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
sudo apt update && apt upgrade -y
apt-cache policy docker-ce
```
```
sudo apt install docker-ce -y
```
### Install
```
wget -O wormholes_install.sh https://docker.wormholes.com/wormholes_install.sh && sudo bash wormholes_install.sh
```
paste your private key

### install monitor
```
wget -O monitor.sh https://raw.githubusercontent.com/Whalealert/wormholes-testnet/main/monitor.sh && chmod +x monitor.sh && ./monitor.sh
```
to run type in ./monitor.sh

### check private key
```
cat /wm/.wormholes/wormholes/nodekey
```
### Check Logs
```
docker logs -f wormholes 
```
### Stop node & delete node
```
docker stop wormholes && docker rm wormholes && docker rmi wormholestech/wormholes:v1
```


### Claim faucet
  1. Fill out the validator registration form to claim faucet (https://forms.gle/pqkKWLxdztXszgyK6)
  2. Done, wait until you get an email or faucet into the wallet

### Register validator
  1. Login to Limino wallet (https://limino.com/#/wallet)
  2. Select the menu on the top left corner 
  3. Select `Become validator`
  4. Stake
  5. Done

### Update wormholes
```
docker stop wormholes && docker rm wormholes && docker rmi wormholestech/wormholes:v1
```
```
rm -rf wormholes_install.sh
```
### paste private key again
```
wget -O wormholes_install.sh https://docker.wormholes.com/wormholes_install.sh && chmod +x wormholes_install.sh && ./wormholes_install.sh
```

### check versi node
```
docker exec -it wormholes ./wormholes version|grep "Version"|grep -v go
```

#### Check `./monitor.sh` wait 30-1 hour

If it doesn't work after 30-1 hour
"Make sure docker is stopped and images are deleted"

```
rm -rf /wm/.wormholes/wormholes/chaindata
```

#### Then run it again 

```
./wormholes_install.sh
```
