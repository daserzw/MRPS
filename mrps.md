![idem-garr-logo]

# IDEM Federation

## Metadata Registration Practice Statement

<table>
  <tr>
    <td>Authors</td>
    <td>Davide Vaghetti</td>
  </tr>
  </tr>
    <td>Reviewers</td>
    <td>Marco Malavolti<br />Barbara Monticini<br /></td>
  </tr>
  <tr>
    <td>Last Modified</td>
    <td>2019-03-28</td>
  </tr>
  <tr>
    <td>Version</td>
    <td>1.0</td>
  </tr>
</table>

**Acknowledgements**

This document is based on the [REFEDS Metadata Registration Practice
Statement template].

**Licence**

![logo]

This document is licensed under Creative Commons CC BY 4.0. You are free
to share, re-use and adapt this document as long as attribution is given.

## 1. Definitions and Terminology

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as described in RFC 2119 [RFC2119].

The following definitions are used in this document:

| Definition                 | Description |
| -------------------------- | ------------- |
| Federation                 | Identity Federation. An association of organisations that come together to securely exchange information as appropriate about their users and resources to enable collaborations and transactions.  |
| Federation Member          | An organisation that has joined the Federation by agreeing to be bound by the Federation Policy in writing. Federation Member can register both Identity and Service Providers. |
| Federation Partner	     | An organisation that signed a memorandum of understanding with the Federation. Federation Partners can register only Service Providers. |
| Federation Participant     | Either a Federation Member or a Federation Partner.|  
| Federation Operator        | Organisation providing the infrastructure for Authentication and Authorisation to Federation Members.|
| Federation Policy          | A document describing the obligations, rights and expectations of the federation members and the Federation Operator. |
| Entity                     | A discrete component that a member wishes to register and describe in metadata.  This is typically an Identity Provider or Service Provider. |
| Registry                   | System used by the Federation Operator to register entity metadata. This may be via a self-service tool or via other manual processes. |
| Registered Representatives | Individuals authorised to act on behalf of the member.  These may take on different roles with different rights attached to them. |

## 2. Introduction and Applicability

The IDEM Federation is the Italian Identity Federation for the research and
educational organisations that belong to the GARR network. GARR provides the
Federation Operator through the GARR IDEM AAI Service.
Normative documents of the IDEM Federation are:
* The IDEM Federation Regulation [IDEM-Reg].
* The IDEM Federation Rules of Participation [IDEM-Part-Rules].

This document describes the metadata registration practices of the GARR IDEM
AAI Federation Operator with effect from the publication date shown on the
cover sheet. All new entity registrations performed in the IDEM Federation
on or after that date SHALL be processed as described here until the
document is superseded.

This document SHALL be published on the Federation website at:

``https://www.idem.garr.it/idem-metadata-registration-practice-statement``

Updates to the documentation SHALL be accurately reflected in entity
metadata.

All the entities that belong to the IDEM Federation SHALL include a
reference to this registration policy.

## 3. Member and Partner Eligibility and Ownership

All the organisations connected to the GARR network are eligible to join
the IDEM Federation as Federation Members.
All the organisations that are not connected to the GARR network, but meet
the Federation policy requirements and can offer valuable services to the
Italian research and education community, are eligible to join the IDEM
Federation as Federation Partners.
Members and Partners of the Federation are also eligible to make use of
a number of services made available by the IDEM Federation Operator, though
to different extent. The main services are:
* the IDEM Registry to register entities: https://registry.idem.garr.it
* the IDEM help desk: <idem-help@garr.it>.
* the IDEM documentation site: https://wiki.idem.garr.it
* the IDEM federaton tools: https://registry.idem.garr.it/idem-tools

The procedure for becoming a member or a partner of the Federation is
documented at:

``https://www.idem.garr.it/en/join`` 

The membership procedure verifies that the prospective member is an
organisation connected to the GARR network. As such it MUST have legal
capacity, and it MUST agree to the Federation policy by signing the IDEM
Federation membership agreement. The Operator makes checks based on the
legal name provided. The checks are conducted on the official GARR
database, which can also be consulted online:

``https://www.garr.it/en/infrastructures/network-infrastructure/connected-organizations-and-sites?key=all``

The partnership procedure verifies that the prospective partner is an
organisation with legal capacity that provide services suitable to and
useful for the research and education community. The prospective partner
MUST also agree to the Federation policy by signing the IDEM
Federation memorandum of understanding.

The membership process also identifies and verifies Registered Legal
Representatives, who are permitted to act on behalf of the organisation in
dealings with third parties. Verification is achieved by the GARR
Secretariat.

The process, for both prospective members and partners, also establishes a
canonical organisation name for the Federation participant.
The canonical organisation name of a participant MAY change during the
membership period, for example as a result of corporate name changes or
mergers.  The participant’s canonical organisation name is disclosed in the
entity’s SAML v2.0 ```<md:OrganizationName>``` element.

## 4. Metadata Format

Metadata for all entities registered by the Federation Operator SHALL make
use of the [SAML-Metadata-RPI-V1.0] metadata extension to indicate that
the IDEM Federation Operator is the registrar for the entity and to detail
the version of the MRPS statement that applies to the entity. The following
is a non-normative example:

```
<mdrpi:RegistrationInfo
    registrationAuthority="https://www.idem.garr.it"
    registrationInstant="2019-04-01T00:00:01Z">
    <mdrpi:RegistrationPolicy xml:lang="en">
        https://www.idem.garr.it/idem-metadata-registration-practice-statement
    </mdrpi:RegistrationPolicy>
</mdrpi:RegistrationInfo>
```

## 5. Entity Eligibility and Validation

### 5.1 Entity Registration

Federation Members and Partners are able to register Service Provders in
the IDEM Federation, while only Members are able to register Identity
Providers.

The Entity eduGAIN publishing policy varies:
* Identity Providers follow an opt-out policy, so they are published to
eduGAIN, unless specifiy differently by the Member they belong to.
* Service Providers follow an opt-in policy: they are published to eduGAIN
 only if the Member or the Partner they belong to explicitly ask for the
 eduGAIN publishing.
 
The process by which a Federation member can register an entity is described
at:

``https://www.idem.garr.it/en/join/``

The Federation Operator SHALL verify the member’s right to use particular
domain names in relation to entityID attributes and, for Identity Provider
entities, any scope elements.

The right to use a domain name SHALL be established in one of the
following ways:

* A member's canonical name matches registrant information in the GARR NIC
database.
* A member's canonical name matches registrant information shown in WHOIS.
* A member MAY be granted the right to make use of a specific domain name
through a permission letter, or other equivalent proofs of permission, from
the domain owner on a per-entity basis.
Permission SHALL NOT be regarded as including permission for the use of
sub-domains.

### 5.2 EntityID Format

Values of the entityID attribute registered MUST be an absolute URI using
the http, https or urn schemes.

https-scheme URIs are RECOMMENDED to all members.

http-scheme and https-scheme URIs used for entityID values MUST contain a
host part whose value is a DNS domain.

### 5.3 Scope Format

For Identity Provider entities, scopes MUST be expressed in lowercase and
rooted in a valid DNS domain name space. Multiple scopes are allowed.

Regular expressions representing multiple scopes MAY be used, but all DNS
domains covered by the expression SHALL be included in checks by the
Federation Operator for the member's right to use those domains. For these
checks to be achievable by the Federation Operator, the set of DNS domains
covered by the regular expression MUST end with a domain under a public
suffix - that is, a literal '.', followed by at least two DNS labels
separated by literal '.'s (representing a domain to be validated as "owned"
by the entity owner), and ending with a '$' anchor (e.g.
`(foo|bar)\.example\.com$`).

### 5.4 Entity Validation

On entity registration, the Federation Operator SHALL carry out entity
validation checks.
These checks include:

* Ensuring all required information is present in the metadata;
* Ensuring metadata is correctly formatted;
* Ensuring protocol endpoints are properly protected with TLS / SSL.
* Ensuring the software providing Identity or Service provider
functionalities is properly configured, secured and fully operational.

For Identity Providers the validation process will also check the following
requirements:
* Information on the enrollment and vetting processes has been provided.
* A URL with the Identity Provider privacy policy is published.

For Service Providers the validation process will also check the following
requirements:
* Declaration to fulfill the General Data Protection Regulation.
* A URL with the Service Provider privacy policy listing all the attributes
necessary to use the service and their respective treatment.

## 6. Entity Management

Once a Federation Participant has joined the IDEM Federation new entities
MAY be added, modified or removed by the organisation with the approval of
the Federation Operator.

### 6.1 Entity Change Requests

Entity changes requests are communicated by the Registered Representative of
the Federation Participant via the IDEM Registry. Entity changes will be
approved or refused by the Federation Operator according to the results of
the evaluation process.

### 6.2 Entity Addition and Removal Requests

Federation participants SHALL request addition or removal of entities to
the Federation Operator via email writing to the IDEM Federation help desk:
<idem-help@garr.it>. 

### 6.3 Unsolicited Entity changes

The Federation Operator may amend or modify the federation metadata at any
time in order to:

* Ensure the security and integrity of the metadata;
* Comply with inter-federation agreements;
* Improve interoperability;
* Add value to the metadata.

Changes will be communicated to Registered Representatives for the entity.

### 6.4 Entity Suspension and ex-officio Removal

The Federation Operator may suspend or remove the entity metadata from the
Federation in order to:

* Comply with the IDEM Regulation [IDEM-Reg] and the IDEM Rules of
Participation [IDEM-Part-Rules].
* Protect the Federation Members in case of verified security breaches.
* Remove orphaned entities.

### 6.5 Additional specifications

The IDEM Federation supports the following additional specifications and the
corresponding SAML representation:
* The REFEDS Research and Scholarship Entity Category version 1.3
[REFEDS-R&S]
* The GEANT Data Protection Code of Conduct version 1.0 [GEANT-DP-CoC]
* The Security Incident Response Trust Framework for Federated Identity
version 1.0 [REFEDS-Sirtfi]

Federation Participants MAY request that their entity is decorated with the
corresponding metadata elements via the IDEM Registry. In case of positive
evaluation the entity will be decorated with the corresponding metadata
elements and published.

## References

* [RFC2119] Bradner, S., "Key words for use in RFCs to Indicate Requirement
 Levels", BCP 14, RFC 2119, March 1997.
* [SAML-Metadata-RPI-V1.0]  SAML V2.0 Metadata Extensions for Registration
and Publication Information Version 1.0. 03 April 2012. OASIS Committee
Specification 01. http://docs.oasis-open.org/security/saml/Post2.0/saml-metadata-rpi/v1.0/cs01/saml-metadata-rpi-v1.0-cs01.html.
* [SAML-Metadata-OS] OASIS Metadata for the OASIS Security Assertion Markup
Language (SAML) V2.0: http://docs.oasis-open.org/security/saml/v2.0/saml-metadata-2.0-os.pdf.
* [REFEDS-R&S] http://refeds.org/category/research-and-scholarship
* [GEANT-DP-CoC-v1] https://www.geant.org/uri/Documents/GEANT_DP_CoC_ver1.0.pdf 
* [REFEDS-Sirtfi] https://refeds.org/wp-content/uploads/2016/01/Sirtfi-1.0.pdf
* [IDEM-Reg] https://www.idem.garr.it/documenti/regolamento 
* [IDEM-Part-Rules] https://www.idem.garr.it/documenti/normepartecipazione

[REFEDS Metadata Registration Practice Statement template]: https://github.com/REFEDS/MRPS/
[logo]: https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/by.svg "CC-BY"
[idem-garr-logo]: idem-garr-logo.png
