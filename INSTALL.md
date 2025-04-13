# Install Procedure for Security Vulnerability Reporting and Disclosure

This is the recommended install procedure to be used by Decent Espresso to install
a basic level of [Security Vulnerability Reporting and Disclosure](README.md) process.

## Assumptions and defaults

The following assumptions and defaults are made for this install procedure.
String search or replace can be used to customize the install for different choices.

* Organization is named `Decent Espresso`
* Domain name `decentespresso.com`
* Security email address `security@decentespresso.com`

## Install Procedure

### Email

1. Ensure the email server is secure and protected from unauthorized access
2. Create a new email address `security@decentespresso.com` for security vulnerability reporting.
3. Implement the email address in a way that ensures that all incoming mail reaches the whole
   internally-designated security team and that the emails are read. Potential options include forwarding
   to everyone in the team or a shared group mailbox.
4. Create a server-side automated email response to acknowledge receipt of emails. This should be instant
   but no later than 24 hours after receipt. This response should follow the recommendations for
   subject and body as described in [autoreply-email.md](autoreply-email.md).
5. Ensure the email server is regularly monitored for incoming security vulnerability reports that may
   have been incorrectly classified as spam.

### security.txt

1. Generate a `security.txt` file on [securitytxt.org](https://securitytxt.org/).
   * Enter `security@decentespresso.com` as _Contact_
   * Choose 1 year from now as _Expires_
   * Enter `en` as _Preferred-Languages_
   * Leave all other field empty for now
2. Store the Output at _Step 2_ of the website to a file named `security.txt`
3. Distribute the file at `https://decentespresso.com/.well-known/security.txt` and if possible at `https://decentespresso.com/security.txt`
4. Ensure the security.txt file is regularly reviewed and renewed before its expiration.
