ciphertrust_pki_role
====================

This role allows the administrator to set up a local CA, create Certificate Signing Request with the private key, and get a PKI certificate signed by the same local CA all using Thales CipherTrust Manager APIs.

Install role -
```ansible-galaxy install anugram.ciphertrust_pki_role```

Requirements
------------

The only requirement apart from Ansible is availability of a running instance of Thales CipherTrust Manager for which you may use the free-forever community edition available at https://ciphertrust.io

Role Variables
--------------
Update the below variables in default/main.yml file
Please refer to the actual Ansible collection documentation for more info around the role variable [here] (https://anugram.github.io/ciphertrust.crypto/collections/anugram/cm_pki/cm_local_ca_module.html#ansible-collections-anugram-cm-pki-cm-local-ca-module)

| Variable Name | Description |
|---|---|
| this_node_address | IP or FQDN of thr CipherTrust Manager or CM |
| this_node_username | admin username of CM |
| this_node_password | password of the admin user |
| ca_names_var | key-value formatted subject names for the CA cert |
| ca_cn | common name for the CA cert |
| ca_name | CM name for the local CA |
| ca_algo | CA key algorthm RSA or ECDSA |
| ca_key_size | Key size depending on algorithm |
| ca_duration | length for which CA is valid |
| csr_cn | common name to include in the certificate signing request |
| csr_name | CM name for the CSR |
| csr_algo | key algorthm RSA or ECDSA |
| csr_key_size | Key size depending on algorithm |
| server_ip | IP address to include in teh certificate if any |
| enc_algo | encryption algo |
| csr_names_var | key-value formatted subject names for the issued cert |
| cert_purpose | purpose of cert like server or client |
| cert_duration | length for which certificate is valid |
| cert_name | CM name for the certificate |

Dependencies
------------
Install below collection -
```ansible-galaxy collection install anugram.cm_pki```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      roles:
         - ciphertrust_pki_role

License
-------

MIT

Author Information
------------------

Anurag Jain, Developer Advocate at ThalesGroup
