---
permalink: /product-documents/ocp3/overview/
redirect_from:
- /openshift-container-platform-3/overview/
layout: styleguide
title: OpenShift Container Platform 3.x Overview
category: Product Documents
lead: ""
subnav:
- text: '&mdash; Common Criteria'
  href: '#common-criteria'
- text: '&mdash; FIPS 140-2'
  href: '#fips-140-2'
- text: '&mdash; USGv6 / IPv6'
  href: '#usgv6-/-ipv6'
- text: '&mdash; Section 508 / VPAT'
  href: '#section-508'
- text: '&mdash; Configuration Guides'
  href: '#configuration-guides'
- text: '&mdash; ICS 500-27 Audit Data Standard'
  href: '#ics-500-27-audit-data-standard'
---

OpenShift Container Platform 3.x Overview

## Common Criteria
OpenShift Container Platform 3.x has not undergone Common Criteria certification. A future certification
against the [NIAP Protection Profile for Application Software](https://www.niap-ccevs.org/Profile/Info.cfm?PPID=394&id=394) is being considered.

To help Red Hat track demand for a Common Criteria certification of OpenShift Container Platform 3.x, please open a
customer support case requesting an evaluation.

## FIPS 140-2
Federal Information Processing Standard 140-2 is a legal requirement ensuring cryptographic tools implement algorithms properly. Vendors must certify their cryptographic implementations through NIST's [Cryptographic Module Validation Program](https://csrc.nist.gov/Projects/Cryptographic-Module-Validation-Program).

FIPS 140-2 validation does not constitute an entire product. Rather, underlying cryptographic
subsystems or components, such as OpenSSL and OpenSSH, are validated. 

When OpenShift Container Platform 3.x runs on Red Hat Enterprise Linux 7.x, the following FIPS 140-2 validations
are retained:

| Product | Component | Version | NIST Certificate | Status | Sunset/Expiration? |
|:--------|:----------|:-------:|:----------------:|:------:|:------------------:|
| Red Hat Enterprise Linux 7.x | OpenSSL | 5.0 | [#3016](https://csrc.nist.gov/Projects/Cryptographic-Module-Validation-Program/Certificate/3016) | <span class="usa-label-big">ACTIVE</span> | 9/14/2022 |
| Red Hat Enterprise Linux 7.x | OpenSSH Client | 5.0 | [#3067](https://csrc.nist.gov/Projects/Cryptographic-Module-Validation-Program/Certificate/3067) | <span class="usa-label-big">ACTIVE</span> | 11/26/2022 |
| Red Hat Enterprise Linux 7.x | OpenSSH Server | 5.0 | [#3063](https://csrc.nist.gov/Projects/Cryptographic-Module-Validation-Program/Certificate/3063) | <span class="usa-label-big">ACTIVE</span> | 11/13/2022 |
| Red Hat Enterprise Linux 7.x | Libreswan | 5.0 | [#3083](https://csrc.nist.gov/Projects/Cryptographic-Module-Validation-Program/Certificate/3083) | <span class="usa-label-big">ACTIVE</span> | 12/18/2022 |
| Red Hat Enterprise Linux 7.x | GnuTLS | 5.0 | [#3012](https://csrc.nist.gov/Projects/Cryptographic-Module-Validation-Program/Certificate/3012) | <span class="usa-label-big">ACTIVE</span> | 9/7/2022 |
| Red Hat Enterprise Linux 7.x | libgcrypt | 5.0 | [#2657](https://csrc.nist.gov/Projects/Cryptographic-Module-Validation-Program/Certificate/2657) | <span class="usa-label-big">ACTIVE</span> | 6/12/2021 |
| Red Hat Enterprise Linux 7.x | NSS | 5.0 | [#3070](https://csrc.nist.gov/Projects/Cryptographic-Module-Validation-Program/Certificate/3070) | <span class="usa-label-big">ACTIVE</span> | 2/7/2023 |

#### Known Issues with FIPS 140-2 Enablement
- By default OpenShift utilizes self-signed certificates. These certificates
are generated by Golang cryptographic API calls and do not meet FIPS 140-2
requirements. It is recommended to use external certificates from
an organizationally recognized Certificate Authority as mitigation.
- By default OpenShift APIs utilize Golang TLS which has not undergone
FIPS 140-2 evaluations. To mitigate this, consider using Opportunistic IPSec
which encapsulates all traffic in OpenSSL tunnels (meeting the requirement for
encryption in transit).

### USGv6 / IPv6
OpenShift Container Platform 3.x does not have any US Government IPv6 certifications.

### Section 508 / VPAT
Coming soon.

### Configuration Guides
A NIST National Checklist for OpenShift Container Platform 3.x is currently being developed. Contact your Red Hat
representative for pre-release access!
