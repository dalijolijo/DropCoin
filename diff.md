# Diff

```sh
diff -b lib/bitcore-explorers.js ../moneypacket.org/lib/bitcore-explorers.js
38c38
<               url = 'https://insight.bitcore.cc';
---
>       url = 'https://insight.bitpay.com';
98c98
<  * Broadcast a transaction to the bitcore network
---
>  * Broadcast a transaction to the bitcoin network
```

```sh
diff -b lib/bitcore.js ../moneypacket.org/lib/bitcore.js
183c183
<  * Internal function to transform a Bitcore address buffer
---
>  * Internal function to transform a bitcoin address buffer
254c254
<  * The addresses will be sorted lexicographically, as that is the trend in bitcore.
---
>  * The addresses will be sorted lexicographically, as that is the trend in bitcoin.
269c269
<  * Internal function to transform a bitcore address string
---
>  * Internal function to transform a bitcoin address string
376c376
<  * @param {string} str - An string of the bitcore address
---
>  * @param {string} str - An string of the bitcoin address
465c465
<  * @returns {Buffer} bitcore address buffer
---
>  * @returns {Buffer} Bitcoin address buffer
494c494
<  * @returns {string} bitcore address
---
>  * @returns {string} Bitcoin address
503c503
<  * @returns {string} bitcore address
---
>  * @returns {string} Bitcoin address
3796c3796
<       var hash = Hash.sha512hmac(hexa, new buffer.Buffer('Bitcore seed'));
---
>   var hash = Hash.sha512hmac(hexa, new buffer.Buffer('Bitcoin seed'));
4639c4639
<       pubkeyhash: 0x03,
---
>   pubkeyhash: 0x00,
4641c4641
<       scripthash: 0x7D,
---
>   scripthash: 0x05,
4645c4645
<       port: 8556,
---
>   port: 8333,
4647c4647,4652
<       'seed.bitcore.biz'
---
>     'seed.bitcoin.sipa.be',
>     'dnsseed.bluematt.me',
>     'dnsseed.bitcoin.dashjr.org',
>     'seed.bitcoinstats.com',
>     'seed.bitnodes.io',
>     'bitseed.xf2.org'
5804c5809
<  * Bitcore transactions contain scripts. Each input has a script called the
---
>  * Bitcoin transactions contain scripts. Each input has a script called the
6040c6045
<  * Translated from Bitcored's CheckSignatureEncoding
---
>  * Translated from bitcoind's CheckSignatureEncoding
6064c6069
<  * Translated from Bitcored's CheckPubKeyEncoding
---
>  * Translated from bitcoind's CheckPubKeyEncoding
6075c6080
<  * Based on Bitcored's EvalScript function, with the inner loop moved to
---
>  * Based on bitcoind's EvalScript function, with the inner loop moved to
8946c8951
< Transaction.FEE_PER_KB = 1000;
---
> Transaction.FEE_PER_KB = 10000;
9008c9013
<  * * `disableMoreOutputThanInput`: disable checking if the transaction spends more bitcores than the sum of the input amounts
---
>  * * `disableMoreOutputThanInput`: disable checking if the transaction spends more bitcoins than the sum of the input amounts
9024c9029
<  * Retrieve a hexa string that can be used with Bitcored's CLI interface
---
>  * Retrieve a hexa string that can be used with bitcoind's CLI interface
9342c9347
<  * Can receive, as output information, the output of Bitcored's `listunspent` command,
---
>  * Can receive, as output information, the output of bitcoind's `listunspent` command,
9364c9369
<  * // From a pay to public key hash output from Bitcored's listunspent
---
>  * // From a pay to public key hash output from bitcoind's listunspent
9907c9912
<  * CheckTransaction in Bitcore core.
---
>  * CheckTransaction in bitcoin core.
9970c9975
<  * Analagous to Bitcored's IsCoinBase function in transaction.h
---
>  * Analagous to bitcoind's IsCoinBase function in transaction.h
10002,10003c10007,10008
<  * @param {number} data.amount amount of Bitcores associated
<  * @param {number=} data.satoshis alias for `amount`, but expressed in satoshis (1 BTX = 1e8 satoshis)
---
>  * @param {number} data.amount amount of bitcoins associated
>  * @param {number=} data.satoshis alias for `amount`, but expressed in satoshis (1 BTC = 1e8 satoshis)
10109c10114
<  * Utility for handling and converting Bitcores units. The supported units are
---
>  * Utility for handling and converting bitcoins units. The supported units are
10351,10352c10356,10357
<  * Instantiate an URI from a Bitcore URI String or an Object. An URI instance
<  * can be created with a Bitcore uri string or an object. All instances of
---
>  * Instantiate an URI from a bitcoin URI String or an Object. An URI instance
>  * can be created with a bitcoin uri string or an object. All instances of
10362c10367
<  * var uri = new URI('Bitcore:12A1MyfXbW6RhdRAZEqofac5jCQQjwEPBu?amount=1.2');
---
>  * var uri = new URI('bitcoin:12A1MyfXbW6RhdRAZEqofac5jCQQjwEPBu?amount=1.2');
10366c10371
<  * @param {string|Object} data - A Bitcore URI string or an Object
---
>  * @param {string|Object} data - A bitcoin URI string or an Object
10368c10373
<  * @throws {TypeError} Invalid Bitcore address
---
>  * @throws {TypeError} Invalid bitcoin address
10423c10428
<  * Check if an Bitcore URI string is valid
---
>  * Check if an bitcoin URI string is valid
10428c10433
<  * var valid = URI.isValid('Bitcore:12A1MyfXbW6RhdRAZEqofac5jCQQjwEPBu');
---
>  * var valid = URI.isValid('bitcoin:12A1MyfXbW6RhdRAZEqofac5jCQQjwEPBu');
10432c10437
<  * @param {string|Object} data - A Bitcore URI string or an Object
---
>  * @param {string|Object} data - A bitcoin URI string or an Object
10446c10451
<  * Convert a Bitcore URI string into a simple object.
---
>  * Convert a bitcoin URI string into a simple object.
10448,10449c10453,10454
<  * @param {string} uri - A Bitcore URI string
<  * @throws {TypeError} Invalid Bitcore URI
---
>  * @param {string} uri - A bitcoin URI string
>  * @throws {TypeError} Invalid bitcoin URI
10455,10456c10460,10461
<       if (info.protocol !== 'bitcore:') {
<       throw new TypeError('Invalid Bitcore URI');
---
>   if (info.protocol !== 'bitcoin:') {
>     throw new TypeError('Invalid bitcoin URI');
10472c10477
<  * @throws {TypeError} Invalid Bitcore address
---
>  * @throws {TypeError} Invalid bitcoin address
10480c10485
<       throw new TypeError('Invalid Bitcore address');
---
>     throw new TypeError('Invalid bitcoin address');
10535c10540
<  * @returns {string} Bitcore URI string
---
>  * @returns {string} Bitcoin URI string
10554c10559
<       protocol: 'bitcore:',
---
>     protocol: 'bitcoin:',
10563c10568
<  * @returns {string} Bitcore URI
---
>  * @returns {string} Bitcoin URI
25543d25547
<       "bitcore",
```

```sh
diff -b controller.js ../moneypacket.org/controller.js
2,3c2,4
<  * DropCoin by dArkjON 2018 - Bitcore BTX Core Developer
<  * https://github.com/dArkjON/DropCoin
---
>  * HIGH
>  * bugs in the rendering of total with mBtc and bits
>  * collapse flows, create new money packet rolls into transactions
5,6c6,45
<  * Copyright (c) 2017 moneypacket.org
<  * Copyright (c) 2018 DropCoin.cc
---
260c299
<                               text:"bitcore:" + imported_public_address,
---
>                               text:"bitcoin:" + imported_public_address,
328c367
<                       $("#new_mp_qrcode").attr("href", "bitcore:" + new_mp_public_address);
---
>                       $("#new_mp_qrcode").attr("href", "bitcoin:" + new_mp_public_address);
330c369
<                               text:"bitcore:" + new_mp_public_address,
---
>                               text:"bitcoin:" + new_mp_public_address,
579c618
<       if (get_unit_code() != "BTX" && get_unit_code() != "mBTX" && get_unit_code() != "bits") {
---
>       if (get_unit_code() != "BTC" && get_unit_code() != "mBTC" && get_unit_code() != "bits") {
775,776c814,815
<       str += "This is a DropCoin envelope for bitcores. \n";
<       str += "Funds can be claimed at https://bitcore.cc/DropCoin/ or https://dropcoins.cc .\n";
---
>       str += "This is a money packet envelope for bitcoins.\n";
>       str += "Funds can be claimed at https://moneypacket.org.\n";
797c836
<       return "btx_dropcoin_" + year + month + day + hour + min + ".txt";
---
>       return "money_packet_" + year + month + day + hour + min + ".txt";
1124c1163
<               $("#unlocked_mp_add_btc_conversion").text(amt_num + " BTX");
---
>               $("#unlocked_mp_add_btc_conversion").text(amt_num + " BTC");
1128c1167
<               $("#unlocked_mp_qrcode").attr("href", "bitcore:" + imported_public_address + "?amount=" + amt_num);
---
>               $("#unlocked_mp_qrcode").attr("href", "bitcoin:" + imported_public_address + "?amount=" + amt_num);
1145c1184
<               $("#unlocked_mp_qrcode").attr("href", "bitcore:" + imported_public_address);
---
>               $("#unlocked_mp_qrcode").attr("href", "bitcoin:" + imported_public_address);
1147c1186
<                       text:"bitcore:" + imported_public_address,
---
>                       text:"bitcoin:" + imported_public_address,
1185c1224
<               $("#new_mp_qrcode").attr("href", "bitcore:" + new_mp_public_address + "?amount=" + total_btc);
---
>               $("#new_mp_qrcode").attr("href", "bitcoin:" + new_mp_public_address + "?amount=" + total_btc);
1193c1232
<               $("#new_mp_add_btc_conversion").text(total_btc + " BTX");
---
>               $("#new_mp_add_btc_conversion").text(total_btc + " BTC");
1199c1238
<               $("#new_mp_qrcode").attr("href", "bitcore:" + new_mp_public_address);
---
>               $("#new_mp_qrcode").attr("href", "bitcoin:" + new_mp_public_address);
1201c1240
<                       text:"bitcore:" + new_mp_public_address,
---
>                       text:"bitcoin:" + new_mp_public_address,
1247,1248c1286,1287
<       if (get_unit_code() == "BTX") return satoshis_to_unit_str(amt, decimals) + " BTX";
<       if (get_unit_code() == "mBTX") return satoshis_to_unit_str(amt, decimals) + " mBTX";
---
>       if (get_unit_code() == "BTC") return satoshis_to_unit_str(amt, decimals) + " BTC";
>       if (get_unit_code() == "mBTC") return satoshis_to_unit_str(amt, decimals) + " mBTC";
1260,1261c1299,1300
<       if (get_unit_code() == "BTX") return parseFloat(satoshis_to_unit(amt).toFixed(8)) + "";
<       if (get_unit_code() == "mBTX") return parseFloat(satoshis_to_unit(amt).toFixed(8)) + "";
---
>       if (get_unit_code() == "BTC") return parseFloat(satoshis_to_unit(amt).toFixed(8)) + "";
>       if (get_unit_code() == "mBTC") return parseFloat(satoshis_to_unit(amt).toFixed(8)) + "";
1281,1282c1320,1321
<       if (code == "BTX") return 1.0;
<       if (code == "mBTX") return 1000.0;
---
>       if (code == "BTC") return 1.0;
>       if (code == "mBTC") return 1000.0;
1285c1324
<               if (exchange_rates[i].symbol == code) return exchange_rates[i].price_usd;
---
>               if (exchange_rates[i].code == code) return exchange_rates[i].rate;
1362d1400
<       console.log("Update");
1370c1408
<               url : "https://api.coinmarketcap.com/v1/ticker/bitcore/",
---
>               url : "https://bitpay.com/api/rates",
1378c1416
<                                               if (obj.symbol != "BTC") select.append($("<option></option>").attr("value", 'USD').text('USD'));
---
>                                               if (obj.code != "BTC") select.append($("<option></option>").attr("value", obj.code).text(obj.code));
1380c1418
<                                       $("#preferred_unit_select option:contains('" + PREFERRED_UNIT_DEFAULT + "')").prop("selected", false);
---
>                                       $("#preferred_unit_select option:contains('" + PREFERRED_UNIT_DEFAULT + "')").prop("selected", true);
1383d1420
<                                       console.log(exchange_rates);
1386d1422
<                                       //console.log(data);
1397,1400d1432
<
<
<
<
1521a1554
>           'CRC': '₡', // Costa Rican Colón
1522a1556,1566
>           'ILS': '₪', // Israeli New Sheqel
>           'INR': '₹', // Indian Rupee
>           'JPY': '¥', // Japanese Yen
>           'KRW': '₩', // South Korean Won
>           'NGN': '₦', // Nigerian Naira
>           'PHP': '₱', // Philippine Peso
>           'PLN': 'zł', // Polish Zloty
>           'PYG': '₲', // Paraguayan Guarani
>           'THB': '฿', // Thai Baht
>           'UAH': '₴', // Ukrainian Hryvnia
>           'VND': '₫', // Vietnamese Dong
```

```sh
diff -b style.css ../moneypacket.org/style.css
35c35
< img[src="img/btx_logo.png"] {
---
> img[src="img/btc_logo.png"] {
```




