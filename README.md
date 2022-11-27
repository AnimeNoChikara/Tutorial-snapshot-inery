# Tutorial-snapshot-inery 




## Cek block sekarang
```
curl -sSL -X POST 'http://bis.blockchain-servers.world:8888/v1/chain/get_info' -H 'Accept: application/json' | jq -r '.head_block_num'
```
## Cek block di node sendiri


```
curl -sSL -X POST 'http://localhost:8888/v1/chain/get_info' -H 'Accept: application/json' | jq -r '.head_block_num'
```
#Jika block di node sendiri masih dari block snapshot yaitu 951801 jauh bisa di lanjutkan:

## 1. Stop and clean data blockchain inery
```
cd $HOME/inery-node/inery.setup/master.node/

./stop.sh
```
```
pkill nodine

./clean.sh
```
## 2. Download dan extract snapshot
```
wget -O inery.tar.gz http://38.108.68.200/inery.tar.gz && tar -xzvf inery.tar.gz
```
## 3. Start again
```
./start.sh
```
## 4. Cek log
```
tail -f blockchain/nodine.log
