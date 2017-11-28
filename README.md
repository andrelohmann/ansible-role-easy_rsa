easy-rsa
====================

[![Build Status](https://travis-ci.org/andrelohmann/ansible-role-easy_rsa.svg?branch=master)](https://travis-ci.org/andrelohmann/ansible-role-easy_rsa)

Use this role to deploy and run easy-rsa for the creation of openvpn certificates and keys.

Requirements
------------

It's strongly suggested, to store your ca somewhere secure and not on the openvpn server itself.

Role Variables
--------------

The following mandatory variables need to be set in group_vars/host_vars

    openvpn_use_tls_auth: True/False
    openvpn_key_country: "__TWO_LETTER_COUNTRY_CODE__"
    openvpn_key_province: "__PROVINCE__"
    openvpn_key_city: "__CITY__"
    openvpn_key_org: "__ORGANISATION__"
    openvpn_key_email: "__EMAIL__"
    openvpn_key_cn: "__UNIQUE_COMMON_NAME__"
    openvpn_key_name: "__KEY_NAME__"
    openvpn_key_ou: "__OPERATIONAL_UNIT__"
    openvpn_key_size: 4096 # key size
    openvpn_key_expire: 3650 #days
    openvpn_ca_expire: 3650 # days

Example Playbook
----------------

    - hosts: easy-rsa
      roles:
         - { role: andrelohmann.easy_rsa }

License
-------

MIT

Author Information
------------------

https://github.com/andrelohmann
