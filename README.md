# LotzaCoins
Merged A Couple of Repos of Coins for Yiimp
Requires YiiMP Server installation. This was built for IdMineThat or DirtyHarryDev Yiimp.

Download the repository:

    git clone https://github.com/IdMineThat/LotzaCoins.git

If you have any coin stratums running (in this example it's Bitcoin or BTC), you can start|stop|restart them with these commands:

    stratum.btc start btc
    stratum.btc stop btc
    stratum.btc restart btc

You will probably need to add coin.conf files to make this all work. Start by making a backup of your old coin.conf files:

    mkdir /home/yiimp-data/yiimp/site/stratum/oldconfig
    cp /home/yiimp-data/yiimp/site/stratum/config/*.conf /home/yiimp-data/yiimp/site/stratum/oldconfig

View one of these config files you just copied, and note the following settings (you'll need it later):

    [TCP]
    server = YourWebsiteOrAddress  <---Note This
    port = 7268
    password = This_Is_A_Password_That_Either_You_Or_Yiimp_Created  <---Note This

    [SQL]
    host = localhost  <---Note This
    database = DatabaseNameThatYiimpCreated  <---Note This
    username = StratumdmOreLettersNStuff  <---Note This
    password = Different_Password_Here  <---Note This


Compile the Stratum:

    cd LotzaCoins/LotzaCoins/stratum-lowdiff
    git clone https://github.com/bitcoin-core/secp256k1/tree/2ed54da18add295668ec71c91534b640d2cc029b
    cd stratum-lowdiff/iniparser
    make
    cd ..
    make

Move stratum file
    
    sudo mv stratum /home/yiimp-data/yiimp/site/stratum/stratum_lowdiff

Copy the new config files into the stratum/config folder. (MAKE SURE YOU'VE BACKED UP YOUR OLD FILES FIRST, see above)

    cd config.sample
    cp *.conf /home/yiimp-data/yiimp/site/stratum/config
    
    
Now you can edit the coin.conf files with your actual settings. This is a rad command, it reads through every .conf file, and replaces the text. If you followed the instructions, you should have notes on the stuff you need to change in a previous step. If this isn't really making sense, try opening one of your backed up .conf files and comparing it to the new .conf files. It will help you see where the tu8tu5 lines up to your actual password, etc... If you didn't read the instructions above before running this stuff, you can probably dig most of this data out of the serverconfig.php file.

    cd /home/yiimp-data/yiimp/site/stratum/config
    sudo sed -i 's/password = tu8tu5/password = 'This_Is_A_Password_That_Either_You_Or_Yiimp_Created'/g' *.conf
    sudo sed -i 's/server = yaamp.com/server = 'YourWebsiteOrAddress'/g' *.conf
    sudo sed -i 's/host = yaampdb/host = localhost/g' *.conf
    sudo sed -i 's/database = yaamp/database = 'DatabaseNameThatYiimpCreated'/g' *.conf
    sudo sed -i 's/username = root/username = 'StratumdmOreLettersNStuff'/g' *.conf
    sudo sed -i 's/password = patofpaq/password = 'Different_Password_Here'/g' *.conf

After run addport modify run.sh with stratum_lowdiff
