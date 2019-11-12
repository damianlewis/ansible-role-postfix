# Ansible Role: Postfix
Role for installing and configuring Postfix.

## Requirements
None.

## Role Variables
Available variables are listed below, along with their default values.

```yaml
postfix_packages:
- mailutils
- postfix
- sasl2-bin
```
Installing Postfix.
- `postfix_packages:list` - Specifies the packages to install.

```yaml
postfix_myorigin: (default Postfix value)
postfix_myhostname: (default Postfix value)
postfix_mynetworks: (default Postfix value)
postfix_mydestination: (default Postfix value)
postfix_inet_interfaces: (default Postfix value)
postfix_inet_protocols: (default Postfix value)
postfix_relayhost: (default Postfix value)
postfix_disable_vrfy_command: (default Postfix value)
```
Configuring basic Postfix settings.
- `postfix_myorigin:string` - Specifies the internet domain name of this mail system. See [mydomain](http://www.postfix.org/postconf.5.html#mydomain).
- `postfix_myhostname:string` - Specifies the internet hostname of this mail system. See [myhostname](http://www.postfix.org/postconf.5.html#myhostname).
- `postfix_mynetworks:list` - Specifies the list of "trusted" remote SMTP clients that have more privileges than "strangers". See [mynetworks](http://www.postfix.org/postconf.5.html#mynetworks).
- `postfix_mydestination:list` - Specifies the list of domains that are delivered via the `local_transport` mail delivery transport. See [mydestination](http://www.postfix.org/postconf.5.html#mydestination).
- `postfix_inet_interfaces:string` - Specifies the network interface addresses that this mail system receives mail on. See [inet_interfaces](http://www.postfix.org/postconf.5.html#inet_interfaces).
- `postfix_inet_protocols:string` - Specifies the Internet protocols Postfix will attempt to use when making or accepting connections. See [inet_protocols](http://www.postfix.org/postconf.5.html#inet_protocols).
- `postfix_relayhost:string` - Specifies the next-hop destination of non-local mail. See [relayhost](http://www.postfix.org/postconf.5.html#relayhost).
- `postfix_disable_vrfy_command:boolean` - Disable the SMTP VRFY command. This stops some techniques used to harvest email addresses. See [disable_vrfy_command](http://www.postfix.org/postconf.5.html#disable_vrfy_command).

```yaml
postfix_smtp_use_tls: (default Postfix value)
postfix_smtp_tls_security_level: (default Postfix value)
postfix_smtp_tls_note_starttls_offer: (default Postfix value)
postfix_smtp_sasl_auth_enable: (default Postfix value)
postfix_smtp_sasl_type: (default Postfix value)
postfix_smtp_sasl_password_maps: (default Postfix value)
postfix_smtp_sasl_security_options: (default Postfix value)
```
Configuring SMTP settings.
- `postfix_smtp_use_tls:boolean` - Opportunistic mode, uses TLS when a remote SMTP server announces STARTTLS support. See [smtp_use_tls](http://www.postfix.org/postconf.5.html#smtp_use_tls).
- `postfix_smtp_tls_security_level:int` - Specifies the default SMTP TLS security level for the Postfix SMTP client. See [smtp_tls_security_level](http://www.postfix.org/postconf.5.html#smtp_tls_security_level).
- `postfix_smtp_tls_note_starttls_offer:boolean` - Specifies the hostname of a remote SMTP server that offers STARTTLS. See [smtp_tls_note_starttls_offer](http://www.postfix.org/postconf.5.html#smtp_tls_note_starttls_offer).
- `postfix_smtp_sasl_auth_enable:boolean` - Enable SASL authentication in the Postfix SMTP client. See [smtp_sasl_auth_enable](http://www.postfix.org/postconf.5.html#smtp_sasl_auth_enable).
- `postfix_smtp_sasl_type:string` - Specifies the SASL plug-in type that the Postfix SMTP client should use for authentication. See [smtp_sasl_type](http://www.postfix.org/postconf.5.html#smtp_sasl_type).
- `postfix_smtp_sasl_password_maps:string` - Specifies the Postfix SMTP client lookup tables. See [smtp_sasl_password_maps](http://www.postfix.org/postconf.5.html#smtp_sasl_password_maps).
- `postfix_smtp_sasl_security_options:string` - Specifies the Postfix SMTP client SASL security options. See [smtp_sasl_security_options](http://www.postfix.org/postconf.5.html#smtp_sasl_security_options).

```yaml
postfix_smtpd_use_tls: (default Postfix value)
postfix_smtpd_tls_cert_file: (default Postfix value)
postfix_smtpd_tls_key_file: (default Postfix value)
postfix_smtpd_tls_security_level: (default Postfix value)
postfix_smtpd_tls_loglevel: (default Postfix value)
postfix_smtpd_sasl_auth_enable: (default Postfix value)
postfix_smtpd_sasl_type: (default Postfix value)
postfix_smtpd_sasl_security_options: (default Postfix value)
postfix_smtpd_recipient_restrictions: (default Postfix value)
postfix_smtpd_relay_restrictions: (default Postfix value)
```
Configuring SMTPD settings.
- `postfix_smtpd_use_tls:boolean` - Opportunistic mode, announce STARTTLS support to remote SMTP clients. See [smtpd_use_tls](http://www.postfix.org/postconf.5.html#smtpd_use_tls).
- `postfix_smtpd_tls_cert_file:string` - Specifies the TLS certificate. See [smtpd_tls_cert_file](http://www.postfix.org/postconf.5.html#smtpd_tls_cert_file).
- `postfix_smtpd_tls_key_file:string` - Specifies the TLS private key. See [smtpd_tls_key_file](http://www.postfix.org/postconf.5.html#smtpd_tls_key_file).
- `postfix_smtpd_tls_security_level:int` - Specifies the SMTP TLS security level for the Postfix SMTP server. See [smtpd_tls_security_level](http://www.postfix.org/postconf.5.html#smtpd_tls_security_level).
- `postfix_smtpd_tls_loglevel:int` - Enable additional Postfix SMTP server logging of TLS activity. See [smtpd_tls_loglevel](http://www.postfix.org/postconf.5.html#smtpd_tls_loglevel).
- `postfix_smtpd_sasl_auth_enable:boolean` - Enable SASL authentication in the Postfix SMTP server. See [smtpd_sasl_auth_enable](http://www.postfix.org/postconf.5.html#smtpd_sasl_auth_enable).
- `postfix_smtpd_sasl_type:string` - Specifies the SASL plug-in type that the Postfix SMTP server should use for authentication. See [smtpd_sasl_type](http://www.postfix.org/postconf.5.html#smtpd_sasl_type).
- `postfix_smtpd_sasl_security_options:string` - Specifies the Postfix SMTP server SASL security options. See [smtpd_sasl_security_options](http://www.postfix.org/postconf.5.html#smtpd_sasl_security_options).
- `postfix_smtpd_recipient_restrictions:list` - Specifies the list of restrictions that the Postfix SMTP server applies in the context of a client RCPT TO command. See [smtpd_recipient_restrictions](http://www.postfix.org/postconf.5.html#smtpd_recipient_restrictions).
- `postfix_smtpd_relay_restrictions:list` - Specifies the list of access restrictions for mail relay control that the Postfix SMTP server applies in the context of the RCPT TO command. See [smtpd_relay_restrictions](http://www.postfix.org/postconf.5.html#smtpd_relay_restrictions).

```yaml
postfix_sasl_user: ''
postfix_sasl_password: ''
```
SASL relay user settings.
- `postfix_sasl_user:string` - Specifies the SASL relay username.
- `postfix_sasl_password:string` - Specifies the SASL relay password.

```yaml
postfix_relayhost_port: 587
```
Additional configuration settings.
- `postfix_relayhost_port:int` - Specifies the relay port number.

```yaml
postfix_aliases: []
```
A list of mail aliases to be added.

The following attributes are required:
- `user:string` - Name of the user.
- `alias:string` - The alias for the user.

```yaml
postfix_service_state: started
postfix_service_enabled: yes
```
The default state for the Postfix service.
- `postfix_service_state:string` - Specifies the state the service should be in.
- `postfix_service_enabled:boolean` - Specifies whether the service should start on boot.

## Dependencies
None.

## Example Playbook
```yaml
- hosts: server
  become: yes

  vars:
    postfix_smtpd_use_tls: true
    postfix_aliases:
    - user: root
      alias: admin@example.com

  tasks:
  - import_role:
      name: damianlewis.postfix
```

## License
MIT

## Author
Damian Lewis