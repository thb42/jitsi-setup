cdist-type__jitsi(7)
==================

NAME
----
cdist-type__jitsi - install jitsi-meet


DESCRIPTION
-----------
Setup a jitsi-meet instance on a ubuntu machine.

REQUIRED PARAMETERS
-------------------

hostname
    The servers hostname.

ip
    The public ip which later will server the jitsi web interface.


OPTIONAL PARAMETERS
-------------------

domain
    If you want your server to have a FQDN, provide a domain.
    The FQDN is then concatenate ``hostname.domain``

adminmail
    If you provide a mail address, the jitsi script for letsencrypt
    certifcate generation will be called with this mail address.


EXAMPLES
--------

.. code-block:: sh

    __jitsi --hostname jitsi-meet \
        --ip xxx.xxx.xxx.xxx \
        --domain example.com \
        --adminmail admin@example.com


SEE ALSO
--------
:strong: https://jitsi.github.io/handbook/docs/devops-guide/devops-guide-quickstart#add-the-jitsi-package-repository

You might want to secure your jitsi instance:
:strong: https://jitsi.github.io/handbook/docs/devops-guide/secure-domain

AUTHORS
-------
toto <toto@toto.one>


COPYING
-------
Copyright \(C) 2020 toto. You can redistribute it
and/or modify it under the terms of the GNU General Public License as
published by the Free Software Foundation, either version 3 of the
License, or (at your option) any later version.
