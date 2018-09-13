Russian CA certificates directory and file
==========================================


What is it?
-----------

There are CA and intermediate certificates used in the official document circulation in Russia. 
This set of certificates can be used with classic OpenSSL and LibreSSL libraries.

Certificates files are created using the https://github.com/schors/gost-ca-parse parser.

In fact, this is the task of the [Minsvyaz](http://minsvyaz.ru). It must do this, but it can't. I don't know why.
I don't have to do this. But I can.

Features
--------
* Directory with separate files and one long file
* Releases by official versions
* Powered by [Usher II](https://usher2.club)


Examples
---------

Try to verify Roskomnadzor dump of restricted sites

### via OpenSSL
```console
git clone https://github.com/schors/gost-russian-ca.git ./
openssl smime -verify -engine gost -CAfile gost-russian-ca.git/certs/ca-certificates.pem \
        -in dump.xml.sig -inform DER -content dump.xml  -out /dev/null

```

### via LibreSSL
```console
git clone https://github.com/schors/gost-russian-ca.git ./
openssl smime -verify -CAfile gost-russian-ca.git/certs/ca-certificates.pem \
        -in dump.xml.sig -inform DER -content dump.xml  -out /dev/null

```

Of course, you may run `c_rehash` utility in the _certs_ directory and then use `-CAdir` option.

Notes
-----

This works on OpenSSL versions 1.0.0 - 1.0.2 includes Alpine Linux except CentOS Linux. CentOS users must suffer.
Debian, Mint and Ubuntu Linux with OpenSSL above version 1.1.0 requires extra package libengine-gost-openssl1.1 maintained by unnamed guy Wartan Hachaturow.
LibreSSL tests on Alpine Linux above version 3.5.


Links
-----

* [Gosuslugi e-trust](http://e-trust.gosuslugi.ru/CA) Portal of Russian Federal Authority of using electronic signature

For nuts
--------

* PayPal https://www.paypal.me/schors
* Yandex.Money http://yasobe.ru/na/schors
* BTC: 18YFeAV12ktBxv9hy4wSiSCUXXAh5VR7gE
* LTC: LVXP51M8MrzaEQi6eBEGWpTSwckybqHU5s
* ETH: 0xba53cebd99157bf412a6bb91165e7dff29abd0a2
* ZEC: t1McmUhzdsauoXpiu2yCjNpnLKGGH225aAW
* DGE: D8cZwBsVp1hW4mjTCgspEKG5TpPZycTJBn
* BCH: 1FiXmPZ6eecHVaZbgdadAuzQLU9kqdSzVN
* ETC: 0xeb990a29d4f870b5fdbe331db90d9849ce3dae77
* WAX: 0xba53cebd99157bf412a6bb91165e7dff29abd0a2

---
[![UNLICENSE](noc.png)](UNLICENSE)
