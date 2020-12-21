# jitsi-setup
Automated jitsi setup for ubuntu.\
This configuration management is following the [quick-start-guide](https://jitsi.github.io/handbook/docs/devops-guide/devops-guide-quickstart) on jitsi's handbook.


## Requirements
You need [`cdist`](https://www.cdi.st/) installed on your local machine and a server running ubuntu and `sshd`.\
Enable `PermitRootLogin prohibit-password` in your `/etc/ssh/sshd_config` on your server.

## Install jitsi
Choose a FQDN in the form of `hostname.domain` for your jitsi instance and setup your DNS record to match it's IP.\
Do the following steps on your local machine to setup jitsi on your server:
```
git clone https://github.com/thb42/jitsi-setup.git
ln -s $(pwd)/jitsi-setup/__jitsi ~/.cdist/type/__jitsi
echo "__jitsi --hostname meet --ip xxx.xxx.xxx.xxx --domain example.com --adminmail admin@example.com jitsi-setup" > ~/.cdist/manifest/jitsi-setup
cdist config -v -i ~/.cdist/manifest/jitsi-setup root@yourserver
```
Replace `meet` and `example.com` with your chosen hostname and domain. Replace the ip parameter with the public ip of your server.\
If you omit the parameter `adminmail` your server will generate a self-signed certificate otherwise your server generates
a letsencrypt certificate and provides the given email address for notification mails. See [here](https://jitsi.github.io/handbook/docs/devops-guide/devops-guide-quickstart#generate-a-lets-encrypt-certificate-optional-recommended).


## Secure your server
By default everyone can open new rooms on your server and everyone who has the link to a room can join the conference.\
You can change this by following [these](https://jitsi.github.io/handbook/docs/devops-guide/secure-domain) steps.
