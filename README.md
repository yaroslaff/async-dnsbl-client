# async-dnsbl-client
Asynchronous dnsbl client

## Install
~~~
pip3 install async-dnsbl-client
~~~
or
~~~
pip3 install git+https://github.com/yaroslaff/async-dnsbl-client
~~~

## CLI usage:
~~~
$ adnsbl.py 117.207.230.178 
dnsbl.sorbs.net
dul.dnsbl.sorbs.net
spam.dnsbl.sorbs.net
zen.spamhaus.org
noptr.spamrats.com
b.barracudacentral.org
web.dnsbl.sorbs.net
pbl.spamhaus.org

# or with hostname
$ bin/adnsbl.py gmail-smtp-in.l.google.com
~~~

## Usage in your python code
See adnsbl.py sources, it's simple.
~~~python
import asyncio
import async_dnsbl_client

result = asyncio.run(async_dnsbl_client.dnsbl('gmail-smtp-in.l.google.com'))

~~~

## Why not adns?
There is already python3 adns support in [python3-adns](https://github.com/trolldbois/python3-adns) package. But it crashes on ARM machines (such as Raspberri Pi and Oracle Ampere A1). (maybe you know why?)

~~~python3
>>> import adns
>>> adns.init()
Segmentation fault (core dumped)
~~~

on 'normal' amd64 it works fine.

## See also
https://github.com/saghul/aiodns

