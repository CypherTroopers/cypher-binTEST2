
Operating system support
---
Cypherium is a derivative blockchain system compatible with Ethereum. With the integration of blockchains connected to various consensus chains, it will run mixed signature accounts such as ed22519 and ecdsa. This version only supports transaction signatures for ECDSA and consensus signatures for ED25519. To participate in consensus, it is necessary to create a new account through the client-side personan.newAccountEd25519 in order to participate and receive a coin reward. It will be used as a weighted coin to participate in the subsequent consensus and enter the committee. After supporting transactions with ed25519, it can participate in the transfer of this account.

Public iP for VPS is needed
--
Your ip of your machine or VPS which used to deploy cypher node  must be `public IP`.such AWS ec2 which has `public IP` to deploy your cypher node!
Open Consensus port `7100` (UDP), P2P block synchronous port `6000` and `30301` (TCP and UDP) , RPC port `8000` (TCP). The P2P port and RPC port can be any port that is not occupied by the system.
If no `POST, CURL, GET` or other RPC requests are sent to this node, the RPC port should be closed to prevent possible network attacks.


cd /usr/local/src
↓
wget https://www.openssl.org/source/old/1.0.2/openssl-1.0.2u.tar.gz
↓
tar -xvzf openssl-1.0.2u.tar.gz
↓
cd openssl-1.0.2u
↓
./config --prefix=/usr/local/openssl-1.0.2 shared
↓
make -j$(nproc)
↓
sudo make install
↓
export LD_LIBRARY_PATH=/usr/local/openssl-1.0.2/lib:$LD_LIBRARY_PATH
↓
echo 'export LD_LIBRARY_PATH=/usr/local/openssl-1.0.2/lib:$LD_LIBRARY_PATH' >> ~/.bashrc
↓
source ~/.bashrc
↓
sudo cp /usr/local/openssl-1.0.2/lib/libcrypto.so.1.0.0 /lib/x86_64-linux-gnu/
↓
sudo ldconfig
↓
git clone https://github.com/CypherTroopers/cypher-binTEST2.git
↓
cd cypher-binTEST2
↓
./start.sh --detail
