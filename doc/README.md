Roadcoin 3.0.0

Copyright (c) 2013-2014 Roadcoin Developers
Copyright (c) 2009-2014 Bitcoin Developers


Setup
---------------------
[Roadcoin Core](http://roadcoin.co/en/download) is the original Roadcoin client and it builds the backbone of the network. However, it downloads and stores the entire history of Roadcoin transactions (which is currently several GBs); depending on the speed of your computer and network connection, the synchronization process can take anywhere from a few hours to a day or more. Thankfully you only have to do this once. 

Running
---------------------
The following are some helpful notes on how to run Roadcoin on your native platform. 

### Unix

You need the Qt4 run-time libraries to run Roadcoin-Qt. On Debian or Ubuntu:

	sudo apt-get install libqtgui4

Unpack the files into a directory and run:

- bin/32/roadcoin-qt (GUI, 32-bit) or bin/32/roadcoind (headless, 32-bit)
- bin/64/roadcoin-qt (GUI, 64-bit) or bin/64/roadcoind (headless, 64-bit)


### Windows

Unpack the files into a directory, and then run roadcoin-qt.exe.

### OSX

Drag Roadcoin-Qt to your applications folder, and then run Roadcoin-Qt.

### Need Help?

* Ask for help on [#roadcoin](http://webchat.freenode.net?channels=roadcoin) on Freenode. If you don't have an IRC client use [webchat here](http://webchat.freenode.net?channels=roadcoin).
* Ask for help on the [Roadcoin Forums](https://roadcoin.co/) forums.

Building
---------------------
The following are developer notes on how to build Bitcoin on your native platform. They are not complete guides, but include notes on the necessary libraries, compile flags, etc.

- [OSX Build Notes](build-osx.md)
- [Unix Build Notes](build-unix.md)
- [Windows Build Notes](build-msw.md)

Development
---------------------
The Roadcoin repo's [root README](https://github.com/RDCFoundation/roadcoin/blob/master/README.md) contains relevant information on the development process and automated testing.

- [Coding Guidelines](coding.md)
- [Multiwallet Qt Development](multiwallet-qt.md)
- [Release Notes](release-notes.md)
- [Release Process](release-process.md)
- [Translation Process](translation_process.md)
- [Unit Tests](unit-tests.md)

* Discuss on the [Roadcoin](https://roadcoin.co/) forums.
* Discuss on [#roadcoin](http://webchat.freenode.net/?channels=roadcoin) on Freenode. If you don't have an IRC client use [webchat here](http://webchat.freenode.net/?channels=roadcoin).

### Miscellaneous
- [Assets Attribution](assets-attribution.md)
- [Files](files.md)
- [Tor Support](tor.md)

License
---------------------
Distributed under the [MIT/X11 software license](http://www.opensource.org/licenses/mit-license.php).
This product includes software developed by the OpenSSL Project for use in the [OpenSSL Toolkit](http://www.openssl.org/). This product includes
cryptographic software written by Eric Young ([eay@cryptsoft.com](mailto:eay@cryptsoft.com)), and UPnP software written by Thomas Bernard.
