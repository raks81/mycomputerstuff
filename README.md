##TODO after a fresh Linux install

1. ln -s /path/to/.mozilla .mozilla
1. Install these:

    ```wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add - ```

    ```sudo sh -c 'echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list'```

    ```sudo apt-get update```

    ```sudo apt-get install git subversion maven2 terminator wine vpnc vim ruby-full gnome-do gnome-do-plugins pidgin openjdk-7-jdk icedtea-7-plugin flashplugin-installer google-chrome-stable xmlstarlet curl```

    ```sudo gem install rhc```

1. Install Crossover
    
    `wget http://crossover.codeweavers.com/redirect/crossover.deb`

    `sudo dpkg --add-architecture i386`

    `sudo apt-get update`

    `sudo dpkg -i crossover.deb`

    `ln -s /path/to/.cxoffice .cxoffice`

1. Install ```rhc``` client:
    
     `sudo gem install rhc`

1. [Test WebEx](https://cisco.webex.com)

1. Unity Indicators

    `sudo apt-get install indicator-multiload`
1. Copy vpnc config files

    `sudo cp /media/pathto/etc/vpnc/*.conf /etc/vpnc/`


