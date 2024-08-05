# minimal-mail-server-ubuntu
A minimal mail server setup for Ubuntu system. Use it on cloud or VPS droplets or machines. Good for developers, tech-savvy people, and nerds.


**Minimal Mail Server Ubuntu** is a minimal setup (yet with easy guidance) script designed to configure a secure and functional mail server on an Ubuntu 20.04+ droplet. This script automates the installation and configuration of essential mail server components, including Postfix, Dovecot, SpamAssassin, Fail2ban, Certbot, and OpenDKIM, to provide a complete mail solution for multiple domains.

## Features

- **Postfix**: Configured for SMTP with SSL/TLS support.
- **Dovecot**: Set up for IMAP with secure authentication.
- **SpamAssassin**: Integrated for effective spam filtering.
- **Fail2ban**: Enhanced security with intrusion protection.
- **Certbot**: Automated SSL certificate management for mail server domains.
- **OpenDKIM**: DKIM signing for email authenticity and integrity.

## Key Benefits
- **Automated Setup:** Easily configure your mail server with a single script.
- **Secure Communication:** Enforces SSL/TLS encryption for email transmission.
- **Spam Protection:** Incorporates advanced spam filtering mechanisms.
- **Dynamic Configuration:** Automatically handles multiple domains with individual configurations.
- **DNS Configuration Guide:** Generates detailed DNS records for SPF, DKIM, and DMARC.

## Important Setup Instructions

Before running the script, ensure you have configured DNS settings for your domains:

1. **Point 'mail' CNAME**: Ensure that `mail.yourdomain.com` (replace `yourdomain.com` with your actual domain) is pointing to your server's IP address. If you have multiple domains or subdomains, ensure that the `mail` CNAME is correctly set for all of them.

2. **TLD or Parent Domain**: Alternatively, if your top-level domain (TLD) or parent domain points to this server, make sure it is correctly configured as well.

## Installation

To install and configure your mail server, run the following command:

```bash
curl -fsSL https://raw.githubusercontent.com/digitalsetups/minimal-mail-server-ubuntu/main/setup_mail_server.sh | sudo bash
```
Follow with the prompts after it. 
 
## After Installation

- After running the script, you will receive a guide with DNS configuration details for SPF, DKIM, and DMARC records. Make sure to update your DNS records accordingly to ensure proper email delivery and authentication.
- Send a test email

## Troubleshoot
- **Check Mail Server Status:** Ensure that all mail server services are running by executing:
  ```sudo systemctl status postfix```
  ```sudo systemctl status dovecot```
  ```sudo systemctl status spamassassin```
- **Review Logs in case of issue:** Check the logs for any errors or issues:

  ```sudo tail -f /var/log/mail.log```
  ```sudo tail -f /var/log/mail.err```

## Developed By

This project was developed by **[Aqsa J.](https://digitalsetups.org)** from **[Digital Setups](https://digitalsetups.org)**.

## Contributing

Feel free to fork the repository, submit issues, or contribute improvements via pull requests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

[Back to Top](#minimal-mail-server-ubuntu)
[See the LICENSE file](LICENSE)
