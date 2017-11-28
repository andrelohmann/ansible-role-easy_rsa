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

    easyrsa_user: root
    easyrsa_dir: "/root" # where will your easy-rsa folder be stored
    easyrsa_use_tls_auth: True/False
    easyrsa_key_country: "__TWO_LETTER_COUNTRY_CODE__"
    easyrsa_key_province: "__PROVINCE__"
    easyrsa_key_city: "__CITY__"
    easyrsa_key_org: "__ORGANISATION__"
    easyrsa_key_email: "__EMAIL__"
    easyrsa_key_cn: "__UNIQUE_COMMON_NAME__" # e.g. your.domain
    easyrsa_key_name: "__KEY_NAME__"
    easyrsa_key_ou: "__OPERATIONAL_UNIT__"
    easyrsa_key_size: 4096 # key size
    easyrsa_key_expire: 3650 # days
    easyrsa_ca_expire: 3650 # days
    easyrsa_clients:
    - name: __CLIENT_ONE__
      state: present/absent # absent clients will be
    - name: __CLIENT_TWO__
      state: present/absent

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
