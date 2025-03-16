# Install Procedure for Security Vulnerability Reporting and Disclosure

This is the recommended install procedure to be used by Decent Espresso to install
a basic level of [Security Vulnerability Reporting and Disclosure](README.md) process.

## Assumptions and defaults

The following assumptions and defaults are made for this install procedure.
String search or replace can be used to customize the install for different choices.

* Organization is named `Decent Espresso`
* Domain name `decentespresso.com`
* Security email address `security@decentespresso.com`
* GPG private and public keys for decryption/encryption of emails
  * private key stored in a secure non-public location
  * public key available at `https://decentespresso.com/security-public-key.asc`

## Install Procedure

### GPG Key Generation

1. We recommend using [GnuPG](https://gnupg.org/) for all related key, encryption, and decryption tasks.
   * Generate keys on a secure system and private keys stored in a secure non-public location
   * Generate keys with a passphrase for additional security
   * Generate keys with the ECC algorithm having 25519 curve
   * Generate keys with an expiration date of 1 year or less for regular review and renewal
2. Run the gpg command to generate a new key pair. This is an interactive process.
   ```bash
   gpg --full-generate-key
   ```
3. Store the private key in a secure non-public location. Ensure the key is backed up and recoverable.
4. Export the public key to a file. Replace `{key-id}` with the key ID from the end of step 2.
   ```bash
    gpg --armor --export {key-id} > security-public-key.asc
    ```
5. Distribute the public key at `https://decentespresso.com/security-public-key.asc`
6. Test the public key is available for anyone to download from `https://decentespresso.com/security-public-key.asc`
7. Test the key pair by encrypting and decrypting a test email message.
8.  Run the following gpg command to publish the public key to a keyserver. Replace `{key-id}` with the key ID from the end of step 2.
   ```bash
    gpg --keyserver keyserver.ubuntu.com --send-keys {key-id}
   ```
9. Ensure the key pair is regularly reviewed and renewed before its expiration.

### Email

1. Ensure the email server is secure and protected from unauthorized access
2. Create a new email address `security@decentespresso.com` for security vulnerability reporting.
3. Create a server-side rule to forward all received emails to the security email address or service
   to be read by the internally designated security team.
4. Create a server-side automated email response to acknowledge receipt of emails. This should be instant
   but no later than 24 hours after receipt. This response should follow the recommendations for
   subject and body as described in [autoreply-email.md](autoreply-email.md).
5. Ensure the email server is regularly monitored for incoming security vulnerability reports that may
   have been incorrectly classified as spam.

### securitytxt

1. Generate a `security.txt` file on [securitytxt.org](https://securitytxt.org/).
   * Enter `security@decentespresso.com` as _Contact_
   * Choose 1 year from now as _Expires_
   * Enter `https://decentespresso.com/security-public-key.asc` as _Encryption_
   * Enter `en` as _Preferred-Languages_
   * Leave all other field empty for now
2. Store the Output at _Step 2_ of the website to a file named `security.txt`
3. Distribute the file at `https://decentespresso.com/.well-known/security.txt` and if possible at `https://decentespresso.com/security.txt`
4. Ensure the security.txt file is regularly reviewed and renewed before its expiration.
