python-hosts-pihole5
========

Minor tweak to allow output of hosts with a space instead of a tab so it works with pihole 5 custom.list
https://github.com/scrytch/unifi-to-pihole5-custom-list-mapping

========
[![Build Status](https://api.travis-ci.org/jonhadfield/python-hosts.svg?branch=devel)](https://travis-ci.org/jonhadfield/python-hosts) [![Coverage Status](https://coveralls.io/repos/jonhadfield/python-hosts/badge.svg?branch=master&service=github)](https://coveralls.io/github/jonhadfield/python-hosts?branch=master) [![Docs](https://img.shields.io/badge/docs-latest-brightgreen.svg?style=flat)](http://python-hosts.readthedocs.org/en/latest/)


This is a python library for managing a hosts file. 
It enables you to add and remove entries, or import them from a file or URL.

Documentation
-------------
The docs are hosted on RTD (Read The Docs) here:  
<http://python-hosts.readthedocs.org/en/latest/index.html>.

Installation
------------
pip install python-hosts

Example usage
------------
Adding an entry to a hosts file

    from python_hosts import Hosts, HostsEntry
    hosts = Hosts(path='hosts_test')
    new_entry = HostsEntry(entry_type='ipv4', address='1.2.3.4', names=['www.example.com', 'example'])
    hosts.add([new_entry])
    hosts.write()

Importing a list of host entries by URL

    from python_hosts import Hosts
    hosts = Hosts(path='hosts_test')
    hosts.import_url(url='https://gist.githubusercontent.com/jonhadfield/5b6cdf853ef629f9b187345d89157280/raw/ddfa4a069fb12bf3c1f285249d44922aeb75db3f/hosts')
    hosts.write()

CLI
---
A command line client using python-hosts can be found here: https://github.com/jonhadfield/hostman


Requirements
------------

Tested on python 2.6, 2.7, 3.3, 3.5, 3.6, 3.7, 3.8, pypy and pypy3


License
-------

MIT
