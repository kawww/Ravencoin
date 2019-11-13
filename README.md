Test Ravencoin full node on Android.

1. Install Termux app and open it. (https://f-droid.org/packages/com.termux/)
2. Install proot and wget.

pkg i -y proot wget

termux-chroot

3. Install ubuntu 

mkdir ubuntu

cd ubuntu

wget https://raw.githubusercontent.com/Neo-Oli/termux-ubuntu/master/ubuntu.sh

bash ubuntu.sh

./start-ubuntu.sh


4. Update and install aarch ravencoin clint for test termux

apt-get update && apt-get -y upgrade

cd /home

apt-get install wget -y

wget https://github.com/kawww/Ravencoin/releases/download/2.5.1/raven-2.5.1-aarch64-linux-gnu.tar.gz


5. If you want to use official client, please compile build by yourself or wait offical aarch client.

6. unzip and run node

tar xzvf raven-2.5.1-aarch64-linux-gnu.tar.gz

cd raven-2.5.1

cd bin

./ravend -daemon

./raven-cli -getinfo


----------------


if you want to test Galaxy

./raven-cli stop

apt-get install vim -y

vim /root/.raven/raven.conf


rpcuser=one

rpcpassword=rvn

rpcport=2222

server=1

assetindex=1

addressindex=1

rpcallowip=127.0.0.1

whitelist=127.0.0.1


1.input :wq ,then press enter to save


./ravend -daemon -reindex


2.open a new session in termux (slide screen from left to middle)

pkg i -y php git

git clone https://github.com/kawww/Galaxy.git

php -S 127.0.0.1:8080 -t Galaxy

3.Now you can use localhost:8080 or 127.0.0.1:8080 to open GalaxyOS for Ravencoin.


ref:https://blog.bitcoinprivacy.net/2019/05/25/ive-built-the-worlds-cheapest-bitcoin-node-and-so-can-you/

Raven Core integration/staging tree
=====================================

https://ravencoin.org

What is Ravencoin?
----------------

Ravencoin is an experimental digital currency that enables instant payments to
anyone, anywhere in the world. Ravencoin uses peer-to-peer technology to operate
with no central authority: managing transactions and issuing money are carried
out collectively by the network. 



License
-------

Raven Core is released under the terms of the MIT license. See [COPYING](COPYING) for more
information or see https://opensource.org/licenses/MIT.

Development Process
-------------------

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/RavenProject/Ravencoin/tags) are created
regularly to indicate new official, stable release versions of Raven Core.

The contribution workflow is described in [CONTRIBUTING.md](CONTRIBUTING.md).

Developer IRC can be found on Freenode at #raven-core-dev.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test on short notice. Please be patient and help out by testing
other people's pull requests, and remember this is a security-critical project where any mistake might cost people
lots of money.

Testnet is now up and running and available to use during development. There is an issue when connecting to the testnet that requires the use of the -maxtipage parameter in order to connect to the test network initially. After the initial launch the -maxtipage parameter is not required.

Use this command to initially start ravend on the testnet. <code>./ravend -testnet -maxtipage=259200</code>

### Automated Testing

Developers are strongly encouraged to write [unit tests](src/test/README.md) for new code, and to
submit new unit tests for old code. Unit tests can be compiled and run
(assuming they weren't disabled in configure) with: `make check`. Further details on running
and extending unit tests can be found in [/src/test/README.md](/src/test/README.md).

There are also [regression and integration tests](/test), written
in Python, that are run automatically on the build server.
These tests can be run (if the [test dependencies](/test) are installed) with: `test/functional/test_runner.py`


### Manual Quality Assurance (QA) Testing

Changes should be tested by somebody other than the developer who wrote the
code. This is especially important for large or high-risk changes. It is useful
to add a test plan to the pull request description if testing the changes is
not straightforward.


About Ravencoin
----------------
A digital peer to peer network for the facilitation of asset transfer.



In the fictional world of Westeros, ravens are used as messengers who carry statements of truth. Ravencoin is a use case specific blockchain designed to carry statements of truth about who owns what assets. 



Thank you to the Bitcoin developers. 

The Ravencoin project is launched based on the hard work and continuous effort of over 400 Bitcoin developers who made over 14,000 commits over the life to date of the Bitcoin project. We are eternally grateful to you for your efforts and diligence in making a secure network and for their support of free and open source software development.  The Ravencoin experiment is made on the foundation you built.


Abstract
----------------
Ravencoin aims to implement a blockchain which is optimized specifically for the use case of transferring assets such as securities from one holder to another. Based on the extensive development and testing of Bitcoin, Ravencoin is built on a fork of the Bitcoin code. Key changes include a faster block reward time and a change in the number, but not weighed distribution schedule, of coins. Ravencoin is free and open source and will be issued and mined transparently with no pre-mine, developer allocation or any other similar set aside. Ravencoin is intended to prioritize user control, privacy and censorship resistance and be jurisdiction agnostic while allowing simple optional additional features for users based on need.



A blockchain is a ledger showing the value of something and allowing it to be transferred to someone else. Of all the possible uses for blockchains, the reporting of who owns what is one of the core uses of the technology.  This is why the first and most successful use case for blockchain technology to date has been Bitcoin.

The success of the Ethereum ERC 20 token shows the demand for tokenized assets that use another blockchain.  Tokens offer many advantages to traditional shares or other participation mechanisms such as faster transfer, possibly increased user control and censorship resistance and reduction or elimination of the need for trusted third parties.

Bitcoin also has the capability of serving as the rails for tokens by using projects such as Omnilayer, RSK or Counterparty. However, neither Bitcoin nor Ethereum was specifically designed for facilitating ownership of other assets. 

Ravencoin is designed to be a use case specific blockchain designed to efficiently handle one specific function: the transfer of assets from one party to another.

Bitcoin is and always should be focused on its goals of being a better form of money. Bitcoin developers will unlikely prioritize improvements or features which are specifically beneficial to the facilitation of token transfers.  One goal of the Ravencoin project is to see if a use case specific blockchain and development effort can create code which can either improve existing structures like Bitcoin or provide advantages for specific use cases.

In the new global economy, borders and jurisdictions will be less relevant as more assets are tradable and trade across borders is increasingly frictionless. In an age where people can move significant amounts of wealth instantly using Bitcoin, global consumers will likely demand the same efficiency for their securities and similar asset holdings.

For such a global system to work it will need to be independent of regulatory jurisdictions.  This is not due to ideological belief but practicality: if the rails for blockchain asset transfer are not censorship resistance and jurisdiction agnostic, any given jurisdiction may be in conflict with another.  In legacy systems, wealth was generally confined in the jurisdiction of the holder and therefore easy to control based on the policies of that jurisdiction. Because of the global nature of blockchain technology any protocol level ability to control wealth would potentially place jurisdictions in conflict and will not be able to operate fairly.  

