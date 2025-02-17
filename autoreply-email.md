# Automated Acknowledgement Email

When any email (careful spam filtering) is received at <security@decentespresso.com>, an automated email response should be sent within 24 hours.
This aligns with the intention for decent and timely communication.

English is the preferred language and style. It should be the first language in the body.
Other languages are optional and to be appended to the body after English.

## Subject

The subject of the email reply should be either:

<ol type="a">
  <li>regarding echo of the received email <code>Re: this is the original subject</code></li>
  <li>case/incident number used for tracking <code>Case 38123-23: security vunerability report</code></li>
</ol>

## Body

The body of the email reply should include the following items.

* acknowledgement
* timeline for the next step
* reminder to provide needed information

An example is presented below.

```
We received your security vulnerability report.
We appreciate your effort to reduce harm to our customers and systems.

We will personally contact you to verify the vulnerability within 5 business days.
We ask for your patience since we may need additional information or clarification.

We request, when possible, the following information to help us understand the issue.
Please reply to this email with any missing information.

* Brief paragraph describing the vulnerability
* Impact (e.g. data loss, unauthorized access, equipment failure, physical harm, etc.)
* Models or versions affected, configuration, setup
* Very detailed steps to reproduce the vulnerability
* Result or evidence of the vulnerability (e.g. screenshots, logs, etc.)
* Expected behavior which is not observed (how it should be secure)
* Proof of concept or exploit code (if applicable) in a ZIP file, private git repository, etc.
* Your contact information (email, phone number, etc.) for further communication

You may encrypt your email or file attachments using our <<<PGP public key url here>>>.
```
