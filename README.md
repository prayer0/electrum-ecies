# Electrum ECIES

Electrum ECIES js implement, encrypt/decrypt message in BIE1 format, like Electrum/Electron Tools -> Encrypt/decrypt message.

### Usage

Encrypt a message, so it can be decrypted in Electrum/Electron Cash Wallet.

Or decrypt message Electrum/Electron Cash Wallet encrypted.

#### Install via NPM

~~~shell

npm install electrum-ecies

~~~

### Examples

#### Encrypt Message with Receiver's PublicKey

~~~javascript

const ECIES = require('electrum-ecies');

//Receiver's PublicKey: 02c01c35eef31acb60386f7fb8e0267f08faf5724d1b2fa1f3588a5fef3e726309

ECIES.encrypt('Hello','02c01c35eef31acb60386f7fb8e0267f08faf5724d1b2fa1f3588a5fef3e726309'); 

//'QklFMQMFmPdvjFe8Wfo+JWmTpo+33LXc+4G8ThfaucU72kieb6lWEv4layTb0x5tzpi6lA2it8rO/ELrXomJqC53uBOd+DZSzDhCSpK6SwR+Itt+Pw=='

//BIE1 use ephemeral keys, so ciphertext is different every time.

~~~

#### Decrypt BIE1 Message with Receiver's PrivateKey

~~~javascript

const ECIES = require('electrum-ecies');

//Receiver's PrivateKey:a1b50c4d420b20059b01e7eea3b3d8a5e943728dfedf962628ca18d04bfa2cfc

//Decrypt Above Message

ECIES.decrypt('QklFMQMFmPdvjFe8Wfo+JWmTpo+33LXc+4G8ThfaucU72kieb6lWEv4layTb0x5tzpi6lA2it8rO/ELrXomJqC53uBOd+DZSzDhCSpK6SwR+Itt+Pw==','a1b50c4d420b20059b01e7eea3b3d8a5e943728dfedf962628ca18d04bfa2cfc')

//<Buffer 68 65 6c 6c 6f>

~~~

#### I Just Want the ECDH Key

~~~javascript

const ECIES = require('electrum-ecies');

const PublicKey = require('bsv').PublicKey;

const PrivateKey = require('bsv').PrivateKey;



var ecdh_key = ECIES.ecdh_key(new PublicKey([Receiver Pubkey]),new PrivateKey([Sender/Ephemeral PrivKey]))



var iv=ecdh_key.subarray(0,16);

var key_aes=ecdh_key.subarray(16,32);

var key_hmac=ecdh_key.subarray(32,64);

~~~

### Donation

If you like it.

BSV address: 1BHcPbcjRZ9ZJvAtr9nd4EQ4HbsUC77WDf

I'm a supporter of BSV, but you are free to use it on BTC/BCH etc.

### License

BSD-2-Clause
