# LotzaCoins
Merged A Couple of Repos of Coins for Yiimp
Requires a YiiMP Server installation.

git clone https://github.com/IdMineThat/LotzaCoins.git

If you have any coin stratums running (in this example it's Bitcoin or BTC), you can start|stop|restart them with these commands:
    stratum.btc start btc
    stratum.btc stop btc
    stratum.btc restart btc
    

    cd LotzaCoins/LotzaCoins/stratum-lowdiff
    git clone https://github.com/bitcoin-core/secp256k1/tree/2ed54da18add295668ec71c91534b640d2cc029b
    cd stratum-lowdiff/iniparser
    make
    cd ..
    make

    Move stratum file
    sudo mv stratum /home/yiimp-data/yiimp/site/stratum/stratum_lowdiff

After run addport modify run.sh with stratum_lowdiff
