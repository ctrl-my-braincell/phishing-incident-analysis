# Email Authentication Analysis

## Authentication-Results

The email's `Authentication-Results` header was examined to determine whether the message successfully passed the sender authentication mechanisms used by the receiving mail server.

The three primary mechanisms reviewed were:

* SPF (Sender Policy Framework)
* DKIM (DomainKeys Identified Mail)
* DMARC (Domain-based Message Authentication, Reporting and Conformance)

### SPF

SPF evaluates whether the sending mail server is authorized to send email on behalf of the domain specified in the envelope sender.

The observed SPF result should be interpreted together with the authenticated sending domain and the IP address recorded in the header.

A passing SPF result indicates that the sending infrastructure was authorized by the domain's SPF policy. However, SPF alone does not prove that the email content or sender identity is trustworthy.

### DKIM

DKIM uses a cryptographic signature to verify that the message was signed by an authorized domain and that signed portions of the message were not modified after signing.

The `d=` value in the DKIM signature identifies the signing domain.

A passing DKIM result provides evidence that the message was successfully signed by the specified domain and that the signature validated against the published public key.

### DMARC

DMARC evaluates whether the authenticated sender domain aligns with the domain visible to the recipient in the `From:` header.

DMARC can use either SPF or DKIM authentication to establish domain alignment.

A passing DMARC result therefore provides stronger evidence that the visible sender domain is aligned with an authenticated sending mechanism.

## Investigation Implications

Authentication results should not be treated as a standalone determination of whether an email is malicious.

A phishing message can use legitimate infrastructure, compromised accounts, or abused services. Conversely, a legitimate message may contain characteristics that appear suspicious when examined without context.

For this investigation, the authentication results must therefore be correlated with:

* The visible sender and `Reply-To` addresses
* The `Return-Path`
* Sending IP address
* SPF result and authenticated domain
* DKIM result and signing domain
* DMARC result and alignment
* URL and redirect behavior
* Destination infrastructure
* Other social-engineering indicators

The authentication evidence will be considered alongside the URL and infrastructure a
