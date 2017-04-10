![Intro](https://raw.githubusercontent.com/thoschm/START-Summit-2017-Blockchain-Machine-Learning-Workshop/master/img/page_0000.jpg)

# START-Summit-2017-Blockchain-Machine-Learning-Workshop
Presentation Material and Sample Code from the Blockchain and Machine Learning Workshop at START Summit 2017 in Switzerland

# Intro
The purpose of this code is to demonstrate in a simple example, how to bring Blockchain technology, smart contracts and Machine Learning together.
It implements a simple chat client that can transmit messages, images and tags to the Blockchain. Tags are automatically extracted via a simple Deep Neural Network using the Keras Python Package with Tensorflow backend.
In addition to just sending messages, the client also supports listening for new messages on the Blockchain from other participants.
For details, please view the workshop presentation.

# Files
```
- runTestnet.sh: launches a local development Blockchain for easy testing
- contract.sol: contains the smart contract code in solidity language
- installContract.py: Python script for sending our contract to the Blockchain
- user.py: Python script that contains the actual chat client
- classify.py: Python script to classifiy an image file
```
# Setup
I really recommend using Linux at this point. The installation guidelines will focus on Ubuntu Linux 16.04 LTS, but should be similar for other distributions.

## We need to install Python 2.7, pip, curl and git first:
```
open a Linux Terminal and enter the following command:
sudo apt-get install python2.7 python-pip curl git build-essential
```

## Install current nodejs version:
```
curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
sudo apt-get install -y nodejs
```

## Install the blockchain test environment:
```
sudo npm install -g ethereumjs-testrpc
```

## Install additional Python packages:
```
sudo pip install -U pip
sudo pip install -U numpy keras tensorflow ethjsonrpc
```

## Now let's clone the workshop code:
```
cd
git clone https://github.com/thoschm/START-Summit-2017-Blockchain-Machine-Learning-Workshop.git workshop_code
```

## Last step of preparation - cloning a ready deep-learning model:
```
cd
git clone https://github.com/fchollet/deep-learning-models.git
cp deep-learning-models/resnet50.py workshop_code/code/
cp deep-learning-models/imagenet_utils.py workshop_code/code/
```
# Simple Image Classification Example
```
cd
cd workshop_code/code
[get some image file in there]
python classify.py image.jpg
```

# Running the complete complete Blockchain + ML Demo

![Architecture](https://raw.githubusercontent.com/thoschm/START-Summit-2017-Blockchain-Machine-Learning-Workshop/master/img/page_0032.jpg)

## Starting the Blockchain testnet
```
cd 
cd workshop_code/code
./runTestNet.sh
```
![TestNet](https://raw.githubusercontent.com/thoschm/START-Summit-2017-Blockchain-Machine-Learning-Workshop/master/img/page_0033.jpg)

We have now created a local testnet that will look and feel the same way as a'normal' node (RPC communication is the same).
The addresses under 'Available Accounts' are the IDs that will identify our network users - like nicknames on a chat platform. Normally they would be sitting on difference computers distributed over the internet and the good news is, the workshop code will work in a 'real' Blockchain network without any modification. 

## Installing the smart contract on the chain
Now open a new terminal and let the testnet run, we need it.
In the new console, enter:
```
cd
cd workshop_code/code
python install








