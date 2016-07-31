X-Originating-IP
================

Add the [X-Originating-IP](https://en.wikipedia.org/wiki/X-Originating-IP) header to all outgoing [Backdrop](https://backdropcms.org/) emails to assist with investigation of the sources for spam and unsolicited bulk email.

A standard Backdrop install sends email as if it was originating from the web server when in fact, the email originated with a person's web browser. Use this module to include information in the outgoing email header about the IP address of the person who submitted a request to a Backdrop website.

Without this module, Backdrop effectively becomes an anonymizing service because the standard email headers will have the email origin listed as the web server IP address instead of the user elsewhere on the Internet. By using the information from X-Originating-IP, you can track down individuals who send undesirable communications through contact forms.

`X-Originating-IP: [xxx.xxx.xxx.xxx]`

The originating IP is based on the
[ip_address()](https://api.backdropcms.org/api/backdrop/core!includes!bootstrap.inc/function/ip_address/1)
Backdrop API function.

> If Backdrop is behind a reverse proxy, we use the X-Forwarded-For header
> instead of $_SERVER['REMOTE_ADDR'], which would be the IP address of the proxy
> server, and not the client's. The actual header name can be configured by the
> reverse_proxy_header variable.

There is no configuration. Just enable the module and it will start working.

Current Maintainer
------------------

- David Norman (https://github.com/deekayen)

Credits
-------

- Originally written for Drupal, then ported to Backdrop by
  David Norman (https://github.com/deekayen)

License
-------

This project is GPL v2 software. See the LICENSE.txt file in this directory for
complete text.
