# LotzaCoins
Merged A Couple of Repos of Coins for Yiimp
Requires a YiiMP Server installation.

git clone https://github.com/IdMineThat/LotzaCoins.git

If you have any coin stratums running (in this example it's Bitcoin or BTC), you can start|stop|restart them with these commands:

    stratum.btc start btc
    stratum.btc stop btc
    stratum.btc restart btc
    
Make a back up of all your old coin.conf files:

    mkdir /home/yiimp-data/yiimp/site/stratum/oldconfig
    cp /home/yiimp-data/yiimp/site/stratum/config/*.conf /home/yiimp-data/yiimp/site/stratum/oldconfig

Get into one of these .conf files and note the following settings:

    [TCP]
    server = stratum.YourWebsite.com
    port = 7268
    password = This_Is_A_Password_That_Either_You_Or_Yiimp_Created

    [SQL]
    host = localhost
    database = DatabaseNameThatYiimpCreated
    username = StratumdmOreLettersNStuff
    password = Different_Password_Here

    [STRATUM]
    algo = x11
    difficulty = 0.016
    max_ttf = 40000


    cd LotzaCoins/LotzaCoins/stratum-lowdiff
    git clone https://github.com/bitcoin-core/secp256k1/tree/2ed54da18add295668ec71c91534b640d2cc029b
    cd stratum-lowdiff/iniparser
    make
    cd ..
    make

    Move stratum file
    sudo mv stratum /home/yiimp-data/yiimp/site/stratum/stratum_lowdiff

After run addport modify run.sh with stratum_lowdiff
