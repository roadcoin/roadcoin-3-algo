Multiwallet Qt Development and Integration Strategy
===================================================

Changes to class RoadcoinGUI
The principal change to the RoadcoinGUI class concerns the QStackedWidget instance called centralWidget.
This widget owns five page views: overviewPage, transactionsPage, addressBookPage, receiveCoinsPage, and sendCoinsPage.

A new class called *WalletView* inheriting from QStackedWidget has been written to handle all renderings and updates of
these page views. In addition to owning these five page views, a WalletView also has a pointer to a WalletModel instance.
This allows the construction of multiple WalletView objects, each rendering a distinct wallet.

A second class called *WalletFrame* inheriting from QFrame has been written as a container for embedding all wallet-related
controls into RoadcoinGUI. At present it contains the WalletView instances for the wallets and does little more than passing on messages
from DigiByteGUI to the currently selected WalletView. It is a WalletFrame instance
that takes the place of what used to be centralWidget in DigiByteGUI. The purpose of this class is to allow future
refinements of the wallet controls with minimal need for further modifications to RoadcoinGUI, thus greatly simplifying
merges while reducing the risk of breaking top-level stuff.

Changes to bitcoin.cpp
----------------------
bitcoin.cpp is the entry point into roadcoin-qt, and as such, will require some minor modifications to provide hooks for
multiple wallet support. Most importantly will be the way it instantiates WalletModels and passes them to the
singleton BitcoinGUI instance called window. Formerly, BitcoinGUI kept a pointer to a single instance of a WalletModel.
The initial change required is very simple: rather than calling `window.setWalletModel(&walletModel);` we perform the
following two steps:

	window.addWallet("~Default", &walletModel);
	window.setCurrentWallet("~Default");

The string parameter is just an arbitrary name given to the default wallet. It's been prepended with a tilde to avoid name collisions in the future with additional wallets.

The shutdown call `window.setWalletModel(0)` has also been removed. In its place is now:

window.removeAllWallets();
