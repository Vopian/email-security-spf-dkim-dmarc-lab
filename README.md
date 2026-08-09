# Email Security Lab: SPF, DKIM, DMARC and Anti-Spoofing

This repository documents a controlled email security lab focused on SPF, DKIM, DMARC, DNS-based authentication, and anti-spoofing verification.

The lab was built as part of my **Network Security** studies at Folkuniversitetet and was performed in an isolated virtual environment.

## Lab Goal

The goal of this lab was to understand how modern email authentication works and how SPF, DKIM, and DMARC help protect a domain against spoofed email.

The lab focused on:

- DNS-based email authentication
- SPF policy configuration
- DKIM signing and public key publishing
- DMARC policy enforcement
- Strict alignment with `adkim=s` and `aspf=s`
- Spoofed email testing
- Mail log analysis
- Wireshark traffic verification

## Lab Environment

The lab was built in GNS3 using Debian-based systems.

Main components:

- DNS server with BIND9
- Mail server with Postfix and Dovecot
- OpenDKIM for DKIM signing
- OpenDMARC for DMARC policy enforcement
- Client node for legitimate and spoofed email testing
- Wireshark for SMTP traffic analysis

## What I Configured

- Authoritative DNS zone for a local lab domain
- SPF TXT record
- MX record for mail routing
- Postfix SMTP server
- Dovecot IMAP service
- Self-signed TLS certificate for the mail server
- DKIM key pair using OpenDKIM
- DKIM public key as a DNS TXT record
- OpenDKIM milter integration with Postfix
- OpenDMARC milter integration with Postfix
- Strict DMARC policy using `p=reject`

## Tests Performed

The lab included both legitimate and spoofed email tests.

Test scenarios included:

- Legitimate email delivery
- DKIM-signed outgoing email
- SPF verification
- DMARC rejection of spoofed messages
- Display-name spoofing test
- Lookalike domain scenario
- Subdomain policy inheritance
- Strict vs relaxed DMARC alignment
- Mail log analysis in `/var/log/mail.log`
- SMTP traffic inspection with Wireshark

## Key Learning Outcomes

This lab helped me understand:

- How SPF, DKIM, and DMARC work together
- Why DNS records are critical for email security
- How DKIM protects message integrity
- How DMARC alignment affects spoofing protection
- Why `p=reject` is stronger than monitoring-only policies
- Why display-name spoofing can still bypass domain authentication
- How to verify email authentication using logs and packet captures
- How email security controls support phishing defense and blue team work

## Tools and Technologies

- GNS3
- Debian Linux
- BIND9
- Postfix
- Dovecot
- OpenDKIM
- OpenDMARC
- SPF
- DKIM
- DMARC
- DNS TXT records
- swaks
- sendemail
- Wireshark
- SMTP
- IMAP
- Linux logs

## Security Note

This repository contains only sanitized documentation.

It does not include private keys, real domains, credentials, full mail logs, raw packet captures, or sensitive configuration files.

## Status

Completed as a lab project during my Network Security studies.
