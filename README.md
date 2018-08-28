Letsencrypt
===========

This role permits to deploy letsencrypt certificates. It is mostly based on the letsencrypt ansible module.

Requirements
------------

ansible >= 2.5

Role Variables
--------------

Defaults:

	letsencrypt_domains: {}
	letsencrypt_files_owner: 'www-data'
	letsencrypt_files_group: 'www-data'
	letsencrypt_path: /etc/letsencrypt/live
	letsencrypt_webroot: /var/www
	letsencrypt_agreement: https://letsencrypt.org/documents/LE-SA-v1.2-November-15-2017.pdf
	letsencrypt_acme_directory: https://acme-v01.api.letsencrypt.org/directory
	letsencrypt_remaining_days: 365
	letsencrypt_intermediate_cert_url: https://letsencrypt.org/certs/letsencryptauthorityx3.pem.txt
	letsencrypt_root_ca_certificate: https://letsencrypt.org/certs/isrgrootx1.pem.txt

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: webserver
      roles:
         - { role: letsencrypt }

with host_vars:

letsencrypt_domains:
  - { "name": "mysuperapp.mydomain.com", "renew": True }

License
-------

Apache 2

Author Information
------------------

Benoit Petit <bpetit@b0rk.in>
