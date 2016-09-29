#Internet Relay Chat (IRC) Protocol client library [![Build Status](https://travis-ci.org/itslukej/zirc.svg?branch=master)](https://travis-ci.org/itslukej/zirc) [![Snippets Count](https://codebottle.io/api/v1/embed/searchbadge.php?keywords=%22zirc%22&language=Python)](https://codebottle.io/?q=%22zirc%22)

###Quick Start
```python
import zirc

class Bot(zirc.Client):
    def __init__(self):
        zirc.Client.__init__(self)
        self.connection = zirc.Socket(ssl=True)
        self.config = zirc.IRCConfig(host="irc.freenode.net", 
            port=6697,
            nickname="zirctest",
            ident="bot",
            realname="test bot",
            channels=["#zirc"],
            )
        
        self.connect(self.config)
        
    async def on_privmsg(self, event):
        await irc.reply(event, "It works!")

Bot()
```

This library implements IRC protocol, It's an event-driven IRC Protocol framework.

#Installation

####PyPi

```
sudo pip install zirc
sudo pip3 install zirc
```

####Github:

```
sudo pip install git+https://github.com/itslukej/zirc.git
sudo pip3 install git+https://github.com/itslukej/zirc.git
```

> Github will contain latest bug fixes and improvements but sometimes also "bad quality" code.

#Features

- Automatic PING/PONG between the server
- IRC Message parsing
- A simple set up and connection method
- Easy installation
- Easy CTCP Set-up

#IPv6

To use IPv6 with `zirc.Socket`, you can use the family `socket.AF_INET6`:

```python
import socket

self.connection = zirc.Socket(family=socket.AF_INET6)
```

#Proxy

Initialize `zirc.Socket` with argument `socket_class`:

```python

self.connection = zirc.Socket(socket_class=zirc.Proxy(host="localhost", port=1080, protocol=zirc.SOCKS5))
```

#Examples

You can [find examples for zIRC by me and other users on CodeBottle](https://codebottle.io/?q=%22zirc%22)


#Ideas

- Multiple connection support

#TODO

- More documentation


#Contributing

> Talk to us on #zirc at Freenode

Please discuss code changes that significantly affect client use of the library before merging to the master branch. Change the version in `setup.py` ahead if the change should be uploaded to PyPi.
