## OpenSSL Basics

**OpenSSL Version**

``openssl version``

``openssl version -a``

``openssl version -help``

**OpenSSL Available Commands**

``openssl help``

> "Standard commands" list available utilities. Linux "man" command display the manual page of utility. (eg. man ciphers)

> "Message Digest commands" list all message digest commands.

> "Cipher commands" list all cipher commands.

**List of cipher suites**

``openssl enc -ciphers``

**Performance**

As you’re probably aware, computation speed is a significant limiting factor for any cryptographic operation. OpenSSL comes with a built-in benchmarking tool that you can use to get an idea about a system’s capabilities and limits. You can invoke the benchmark using the ``speed`` command.

``openssl speed``

**Manual Pages**

``man openssl``

``man enc``

``man dgst``

## References:

1. "OpenSSL Cookbook", by Ivan Ristić
