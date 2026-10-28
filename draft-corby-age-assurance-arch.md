---
v: 3
title: "Age Assurance Architecture"
abbrev: "Age Assurance Architecture"
docname: draft-corby-age-assurance-arch-latest
category: info
submissiontype: IETF
ipr: trust200902
stand_alone: yes
venue:
  mail: architecture-discuss@ietf.org
  arch: https://mailarchive.ietf.org/arch/browse/architecture-discuss/
  github: The-AVPA/draft-corby-age-assurance-arch
  latest: https://the-avpa.github.io/draft-corby-age-assurance-arch/draft-corby-age-assurance-arch.html
keyword:
  - age assurance
  - age verification
  - age estimation
  - privacy
  - unlinkability

author:
  - fullname: Iain Corby
    organization: Age Verification Providers Association
    city: London
    country: United Kingdom
    email: iain@avpassociation.com

normative:

informative:
  RFC9576:
  RFC9578:
  RFC9901:
  RFC9998:
  I-D.ietf-oauth-sd-jwt-vc:
  I-D.knodel-age-arch:
    title: "Age Verification Architecture"
    author:
      - ins: M. Knodel
        name: Mallory Knodel
      - ins: G. A. Scalone
      - ins: T. Newton
      - ins: A. Hingle
    date: 2026-07
    seriesinfo:
      Internet-Draft: draft-knodel-age-arch-01
    target: https://datatracker.ietf.org/doc/draft-knodel-age-arch/
  AU-AATT:
    title: "Age Assurance Technology Trial: Final Report"
    author:
      - org: Department of Infrastructure, Transport, Regional Development, Communications, Sport and the Arts (Australia)
    date: 2025-08-31
    target: https://www.infrastructure.gov.au/department/media/publications/age-assurance-technology-trial-final-report
    annotation: Conducted by the Age Check Certification Scheme.
  CEN-TS-18099:
    title: "Biometric data injection attack detection"
    author:
      - org: CEN
    date: 2024
    seriesinfo:
      CEN/TS: "18099:2024"
  Discord-AA:
    title: "Age Assurance on Discord: Vendors, Methods, and Your Data"
    author:
      - org: Discord
    date: false
    target: https://discord.com/safety/age-assurance-on-discord-vendors-methods-and-your-data
  EC-Art28:
    title: "Guidelines on measures to ensure a high level of privacy, safety and security for minors online, pursuant to Article 28 of Regulation (EU) 2022/2065"
    author:
      - org: European Commission
    date: 2025
  eSafety-SMMA-3M:
    title: "Early days, early insights: Understanding experiences of social media age restrictions at the three-month follow-up"
    author:
      - org: eSafety Commissioner (Australia)
    date: 2026-07-31
    target: https://www.esafety.gov.au/research/social-media-age-restrictions-evaluation/early-days-early-insights-three-months-report
  EU-AV-Blueprint:
    title: "EU age verification"
    author:
      - org: European Commission
    date: 2025-07-14
    target: https://digital-strategy.ec.europa.eu/en/policies/eu-age-verification
    annotation: "Age verification blueprint, first published 14 July 2025. Specifications at https://ageverification.dev/."
  euCONSENT:
    title: "euCONSENT"
    author:
      - org: euCONSENT ASBL
    date: false
    target: https://euconsent.eu
  IAB-Statement-2026:
    title: "IAB Statement on Age-Based Restrictions and Online Safety"
    author:
      - org: Internet Architecture Board
    date: 2026-08-24
    target: https://datatracker.ietf.org/doc/statement-iab-statement-on-age-based-restrictions-and-online-safety/
  IEEE-2089.1:
    title: "IEEE Standard for Online Age Verification"
    author:
      - org: IEEE
    date: 2024
    seriesinfo:
      IEEE Std: 2089.1-2024
  IEEE-P2089.3:
    title: "Standard for Online Parental Consent"
    author:
      - org: IEEE
    date: false
    seriesinfo:
      IEEE: P2089.3
    annotation: Work in progress.
  ISO-18013-5:
    title: "Personal identification: ISO-compliant driving licence, Part 5: Mobile driving licence (mDL) application"
    author:
      - org: ISO/IEC
    date: 2021
    seriesinfo:
      ISO/IEC: "18013-5:2021"
  ISO-27566-1:
    title: "Information security, cybersecurity and privacy protection: Age assurance systems, Part 1: Framework"
    author:
      - org: ISO/IEC
    date: 2025-12
    seriesinfo:
      ISO/IEC: "27566-1:2025"
    target: https://www.iso.org/standard/88143.html
  ISO-27566-4:
    title: "Age assurance systems, Part 4: Interoperability"
    author:
      - org: ISO/IEC
    date: false
    annotation: Proposed work item, not yet published.
  ISO-30107-3:
    title: "Information technology: Biometric presentation attack detection, Part 3: Testing and reporting"
    author:
      - org: ISO/IEC
    date: 2023
    seriesinfo:
      ISO/IEC: "30107-3:2023"
  NIST-FATE-AEV:
    title: "Face Analysis Technology Evaluation (FATE): Age Estimation and Verification"
    author:
      - org: NIST
    date: false
    annotation: Ongoing evaluation.
  NIST-IR-8525:
    title: "Face Analysis Technology Evaluation: Age Estimation and Verification"
    author:
      - ins: K. Hanaoka
      - ins: M. Ngan
      - ins: J. Yang
      - ins: G. W. Quinn
      - ins: A. Hom
      - ins: P. Grother
    date: 2024-05
    seriesinfo:
      NIST IR: "8525"
  Ofcom-HEAA:
    title: "Guidance on highly effective age assurance"
    author:
      - org: Ofcom
    date: 2025-01
  OpenID4VP:
    title: "OpenID for Verifiable Presentations 1.0"
    author:
      - org: OpenID Foundation
    date: 2025-07-09
    annotation: Final Specification.
  W3C-DC-API:
    title: "Digital Credentials"
    author:
      - org: W3C
    date: 2026-09-04
    annotation: W3C Working Draft.

--- abstract

This document describes a technology-neutral architecture for age assurance on the Internet, drawing on the framework established by ISO/IEC 27566-1 and the levels of assurance defined in IEEE 2089.1. It sets out the methods of age assurance (verification, estimation and inference), how their performance is measured and assured, the roles and trust relationships involved, and how results can be reused across services without creating persistent identifiers. Its main contribution is a model for communicating trustworthy, privacy-preserving age assertions between independently governed systems. It treats assurance, privacy, interoperability, resistance to circumvention and inclusion as measurable properties of complete age assurance systems, and distinguishes the capabilities of existing technical components from the additional safeguards necessary for secure and privacy-preserving deployment. It is neutral on whether age restrictions should exist, at what ages and for which services, which are policy questions outside its scope; it is not neutral about how safely and privately such restrictions are implemented where they do exist.

--- middle

# Introduction

Age assurance is increasingly a regulatory requirement. Services in the UK, the EU, Australia, many US states and elsewhere are now required to establish the age or age range of users before giving access to some content, features or goods. In most of these regimes the regulated service (the relying party) remains responsible for achieving the required outcome, even when it relies on a third party to perform the check.

The IAB/W3C Workshop on Age-Based Restrictions on Content Access {{RFC9998}} called for a shared vocabulary, a clear account of the roles involved and a neutral mapping of risks against architectures. RFC 9998 is an IAB workshop report: it records the views of participants and is not an IETF consensus document. It notes that participants pointed to ISO/IEC 27566-1 {{ISO-27566-1}} as a source of common terminology. This document takes up that call. It uses the framework established by ISO/IEC 27566-1 and the levels of assurance in IEEE 2089.1 {{IEEE-2089.1}} as its conceptual foundation. Where this document groups, classifies or combines those concepts into architectural mechanisms, that synthesis is its own and should not be read as the normative structure of either standard, so that Internet protocols and architectures can be discussed in the same terms already used by regulators, certification bodies and the age assurance industry.

The IAB has since published a statement on age-based restrictions and online safety {{IAB-Statement-2026}}. This document shares the requirements that statement sets out: disclose no more than a minimal, purpose-specific age signal; do not report users' activity; do not produce signals that can be linked across sites; do not reveal visited sites to the party that verified age; avoid centralised stores of sensitive data; and use open, interoperable interfaces. It also agrees that mandates should specify outcomes rather than technologies. It differs in emphasis on two points. First, it treats on-device processing as a property that any provider can offer, not only device and operating system vendors, so that device-level privacy need not concentrate control in a few platforms. Second, it argues that conformity assessment can and should establish confidence in claims about system-level properties such as privacy, unlinkability and resilience, which the IAB statement notes are often missed when vendors are certified against regulatory criteria.

The goal is to describe how age assurance can be done well where it is required. That means a service can obtain assurance proportionate to the risk, users have a choice of accessible and privacy-preserving methods, and trustworthy results can be reused without creating either a universal identity system or a new means of tracking people across the Internet.

## Related Work {#related}

Several documents address the same problem. {{RFC9998}} records the IAB/W3C workshop discussion, {{IAB-Statement-2026}} sets out the IAB's position, and {{I-D.knodel-age-arch}} analyses age gating methods along two dimensions, efficacy and privacy cost, organised by trust anchor. This document is offered as an alternative architecture to the last. It differs mainly in using terminology consistent with ISO/IEC 27566-1 throughout, in treating assurance as a measurable and multidimensional property of implemented systems, in distinguishing privacy properties enforced by design from those that rely on policy, and in focusing on how age assertions are communicated and trusted between independently governed systems. {{comparison}} compares the two documents on specific points.

## Terminology {#terminology}

Terms follow ISO/IEC 27566-1 and IEEE 2089.1 where those documents define them. The definitions below are paraphrased for an Internet audience; the referenced standards are authoritative. Some terms, including the forms of binding and triple-blind, are introduced by this document and are not defined in either standard.

Age assurance:
: The umbrella term for processes that establish, with a stated level of confidence, that a person is of a certain age, over or under an age threshold, or within an age range. It includes age verification, age estimation and age inference.

Age verification:
: Age assurance that relies on authoritative evidence of date of birth, such as a government-issued document, a digital credential or a trusted record, checked for authenticity and bound to the person presenting it.

Age estimation:
: Age assurance that derives an estimate of age from physical or behavioural characteristics of the person, such as facial or voice features, typically using machine learning models.

Age inference:
: Age assurance that draws a conclusion about age from other verified facts about the person, such as holding a payment card, a mortgage or a long-standing account, or from a combination of signals.

Self-declaration:
: A user's unverified statement of age. It provides no independent evidence and is not age assurance in the sense used here, though it may be a useful first step in a waterfall of methods.

Age threshold:
: The age that a relying party needs to know a user is above or below, for example 13, 16 or 18.

Over NN:
: At least NN years of age (for example, a person who has reached their 18th birthday is "over 18"). In protocols it should be expressed as the inclusive test age >= NN, with the semantics defined explicitly.

Relying party:
: The service that uses the result of age assurance to decide what access or experience to provide. It is the "enforcer" in the roles of {{RFC9998}}.

Age assurance provider:
: The party that performs age assurance and asserts the result. It may be an independent provider, the relying party itself, a credential issuer, a wallet, an operating system, app store or another intermediary. It is the "verifier" in {{RFC9998}}.

Age assertion:
: The result of age assurance as conveyed to a relying party, for example "over 18", together with information about its level of assurance, provenance and validity.

Level of assurance:
: A standardised measure of the confidence that can be placed in an age assertion, reflecting accuracy, binding, resistance to attack and other factors. IEEE 2089.1 defines levels from Asserted through Basic, Standard and Enhanced to Strict. A level summarises confidence in the result; it does not describe every characteristic relevant to a particular relying party ({{levels}}).

Binding:
: Measures that link an age result to a person. This document treats three related but different problems separately: initial binding (at the original check, the evidence or characteristics assessed belong to the person being checked), holder binding (the assertion or credential is tied to its legitimate holder, typically through a key whose control the presenter can prove) and contemporaneous person binding (the person presenting at the point of reliance is that legitimate holder). Device possession and successful local authentication establish holder binding, not contemporaneous person binding. Only contemporaneous person binding directly addresses sharing and collusion.

False acceptance / false rejection:
: Accepting a person who is in fact below the threshold, or rejecting a person who is in fact above it.

Buffer (or challenge age):
: A margin above the legal threshold that an age estimate must exceed, set from measured performance so that the false acceptance rate meets the requirement.

Reusable age assurance:
: An age assertion established once and presented again to the same or another relying party, without repeating the original check.

Interoperability network:
: An arrangement under which relying parties accept age assertions from providers they do not contract with directly, under common rules on assurance and liability.

Upstream age signal:
: An age assertion or age range supplied by an operating system, app store, browser, network or device setting, rather than by the relying party's own check.

Triple-blind:
: A property of an age assurance flow in which the relying party receives no identifying information beyond the minimum age-related assertion necessary for its purpose, the provider or issuer cannot learn which relying parties the user visits, and any operating system or other platform technically involved cannot learn which relying parties the user visits either. Relying parties should also be unable to link presentations by the same user. {{triple-blind}} distinguishes where each property is cryptographically enforced and where it rests on operational or legal controls.

Age gating:
: Restricting access to content, features or goods on the basis of an age assertion.

# Methods of Age Assurance {#methods}

No single method works for every person or every use case. Each method below can deliver a range of levels of assurance depending on how it is implemented, and {{measuring}} describes how that level is measured. In deciding whether a result is reliable enough for a given context, the measured assurance characteristics of an implementation matter more than the category of method. Methods still differ in their privacy, inclusion and attack characteristics at the same level, and a relying party or user may legitimately weigh those separately.

## Age Verification {#verification}

Age verification checks authoritative evidence of date of birth. Sources include passports, identity cards and driving licences, whether physical or digital; government and other authoritative databases; and verifiable digital credentials such as ISO/IEC 18013-5 mobile driving licences {{ISO-18013-5}}, SD-JWT VC {{I-D.ietf-oauth-sd-jwt-vc}} or W3C Verifiable Credentials issued by a state or other trusted issuer.

To reach a high level of assurance, verification needs two things. First, the authenticity of the evidence must be established, for example by validating the issuer's signature on a credential or the security features of a document. Second, the evidence must be bound to the person presenting it, for example by a liveness-checked comparison with the document photo. Where a credential is held on a device, device-bound keys and local authentication show that the presenter controls the device, but not necessarily that they are the person originally verified: a parent could hand over an unlocked device or authorise a presentation on a child's behalf. Where sharing is a significant risk, higher levels of assurance may call for contemporaneous person binding, such as a fresh face match against the credential's portrait, or for other controls in proportion to the risk.

Verification can also be performed entirely on the user's device. For example, an app can read the chip in an electronic passport or identity card over NFC, validate the issuing state's signature and compare the chip photo with a live selfie, so that personal data never leaves the user's hand and only the age result is shared.

A common assumption is that age verification requires the relying party to receive a copy of an identity document. It does not. In well-designed systems the provider inspects the evidence and returns only the age assertion, and selective disclosure credentials can prove "over 18" without revealing a date of birth to the relying party. Systems that copy documents to relying parties reflect poor practice, not a property of the method.

Verification is necessary where a specific date of birth must be established. It excludes people who lack accepted documents, so it should normally be offered alongside other methods rather than as the only route.

## Age Estimation {#estimation}

Age estimation infers age from characteristics of the person, most commonly a facial image or short video, and sometimes voice or hand movement. It does not establish identity, and a well-designed implementation retains no image once the estimate is made.

Estimation can likewise run entirely on the user's device, so the image is never transmitted and only the estimated age or threshold result is passed on. Discord, for example, offers facial age estimation processed entirely on the user's device and deleted immediately afterwards, while its document checks are sent to a provider {{Discord-AA}}. On-device processing removes the risk of a central breach of images, but the result must still be protected against tampering on the device, for example by attesting the integrity of the software that produced it. The example illustrates data minimisation only; it does not by itself demonstrate resistance to presentation, injection or other attacks.

Older evaluations of facial age estimation, such as NIST IR 7995 from 2014, do not represent current technology. NIST IR 8525 {{NIST-IR-8525}} and the ongoing NIST age estimation evaluation {{NIST-FATE-AEV}} provide more recent measurements of algorithm performance, while the Australian Age Assurance Technology Trial {{AU-AATT}} provides additional evidence from independent evaluation. Performance varies between algorithms, age thresholds, demographic groups and capture environments, and laboratory results neither transfer automatically to a given capture setting nor establish resistance to attack. The appropriate architectural response is therefore to set measurable performance requirements, including false acceptance rates, and to require testing under conditions relevant to the intended deployment.

The relevant question is not whether an estimate can be wrong. It is whether the error at the relevant threshold is measured and managed. Estimation achieves a required false acceptance rate by applying a buffer: a user may need to be estimated at 21 or 25 to pass an 18 check. Users near the threshold who are rejected can be offered another method. This is the "waterfall" approach described in {{Section 3.5 of RFC9998}}, in which lower-friction methods are tried first.

Differential performance across demographic groups is real and must be measured, reported and minimised. It is a reason for independent testing and certification ({{measuring}}), not a reason to exclude the method. It is also a reason to ensure alternative methods are always available so users are not wrongly excluded.

## Age Inference {#inference}

Age inference draws a conclusion about age from other facts that are themselves verified. Examples include a credit card check with the issuing bank, the existence of a mortgage or other adult financial product, mobile network operator records showing an account without adult content restrictions, the age of an email address and its history of use, or a professional licence with a minimum age, such as a commercial airline pilot's licence. Such facts are evidence of age only to the extent that eligibility rules guarantee it, the fact is authentic and the person presenting it is the person to whom it relates. Holding a credit card shows that an account exists, not that the person at the keyboard is its holder. Some forms therefore need more data points, or added binding, than others to reach a given level of assurance.

Inference can be low-friction and privacy-protective when the facts are checked by the party that already holds them and only the result is returned. It can also be intrusive if it relies on profiling users without their knowledge. This document addresses inference performed as a deliberate, transparent age check, not behavioural profiling for other purposes.

Social media platforms have deployed a form of age inference, sometimes called "heuristics", to detect underage users who already hold accounts. Three months after Australia's minimum age law took effect, the share of 10 to 15 year olds holding an account on an age-restricted platform had fallen only from around 52% to 42%, and the eSafety Commissioner concluded that platform implementation remained ineffective {{eSafety-SMMA-3M}}. These findings indicate that the age assurance measures deployed by platforms during the initial implementation period did not reliably prevent under-16s from retaining or creating accounts. They do not, by themselves, establish the accuracy of any particular inference algorithm.

## Parental and Guardian Involvement {#parental}

Some legal requirements concern parental consent or parental controls rather than age restriction alone. These involve establishing that an adult is a parent or guardian of the child, and that the adult has consented or set a control. IEEE P2089.3 {{IEEE-P2089.3}} is developing a standard for online parental consent. Operating system and app store settings chosen by parents can be an effective way to implement such requirements, provided they meet the conditions in {{layered}}.

## Reusable Age Assurance {#reusable}

Once established, an age assertion can be held by the user (for example in a wallet or as a device-bound token) or by a provider, and presented again later. Reuse reduces friction and the number of times personal data, if required at all, is processed. It also introduces new requirements: the assertion must remain bound to the right person, carry its level of assurance and validity and avoid acting as a persistent identifier across relying parties. {{architecture}} describes architectures that meet these requirements.

# Measuring and Assuring Age Assurance {#measuring}

The strength of an age check is a measurable property of an implementation, not a fixed property of a method. Two facial estimation systems, or two document checks, can differ widely in performance. A relying party therefore needs to understand the assurance characteristics of the result it receives that are relevant to its context, which a level of assurance summarises but does not replace, and needs confidence that those characteristics have been independently established.

## Components of Assurance {#components}

Drawing on ISO/IEC 27566-1 and IEEE 2089.1, this document groups the factors that determine confidence in an age assertion as follows. The grouping is this document's own; the normative requirements of each standard are set out in its published text.

* **Accuracy.** For verification, the rate at which forged, altered or invalid evidence is accepted. For estimation, the error in the estimate and its distribution, and in particular the false acceptance and false rejection rates around the relevant threshold. For inference, the strength of the link between the facts checked and age.

* **Binding.** How strongly the result is tied to a person, which involves three distinct questions ({{terminology}}): whether the evidence assessed at the initial check belonged to the person checked; whether a reused assertion or credential is tied to its legitimate holder; and whether that holder is the person actually presenting it at the point of reliance. Live estimation addresses the first and third together, because it assesses the person in front of the camera at that moment. For reused results and evidence from another source, device possession and local authentication establish control of a credential, not that the original subject is the present user: a younger sibling who knows the PIN, or is handed an unlocked device, will pass them. Where sharing and collusion are significant risks, contemporaneous person binding, such as a fresh liveness-checked face match, is one control. Others include short validity periods, limits on reuse and risk signals, and the appropriate combination depends on the use case.

* **Resistance to attack.** Detection of presentation attacks (masks, photos or replayed video shown to the camera), evaluated for example to ISO/IEC 30107-3 {{ISO-30107-3}}. Separately, detection of injection attacks (synthetic or manipulated media inserted into the capture pipeline, bypassing the camera) and assurance of capture integrity, for which CEN/TS 18099 {{CEN-TS-18099}} provides an evaluation method. And controls against collusion and credential sharing.

* **Bias.** Measured differences in performance across groups defined by age, sex, skin tone or other protected characteristics, and steps to minimise them.

* **Privacy and security.** Data minimisation, retention, purpose limitation and the security of any personal data processed.

## Levels of Assurance {#levels}

Standard levels of assurance let a regulator or relying party specify the confidence it needs in an age result without prescribing technology. IEEE 2089.1 defines five levels: Asserted, Basic, Standard, Enhanced and Strict, with requirements set out in that standard. A level of assurance describes confidence that the age result is correct and belongs to the person presenting it. It does not capture everything a relying party or user may care about. Privacy properties and inclusion are separate dimensions, and should be expressed and assessed separately rather than folded into a single level. Assurance is therefore multidimensional, and a nominal level of assurance cannot substitute for understanding the characteristics relevant to a particular relying-party context: two results at the same level may differ, for example, in how they are bound to the person presenting them or in what they reveal. Certification status is not one of these dimensions; it is evidence about whether claimed characteristics have been established ({{certification}}).

This outcome-based approach is converging internationally. Ofcom's "highly effective age assurance" criteria in the UK (technically accurate, robust, reliable and fair) {{Ofcom-HEAA}} and the European Commission's guidelines under Article 28 of the Digital Services Act {{EC-Art28}} both set outcomes rather than mandate methods (although the Article 28 guidelines prefer verification where access is restricted to adults by law).

## Independent Testing and Certification {#certification}

Claims about accuracy, privacy and effectiveness should rest on independently verifiable evidence and comparable testing. Conformity assessment, including certification, is a mechanism for establishing confidence in claims about a system's characteristics; it is not itself one of those characteristics. Certification provides independently established objective evidence that specified requirements have been fulfilled, but it does not make an implementation effective, and its value depends on what those requirements cover. Three forms of evidence are available:

1. **Laboratory evaluation** of algorithms against common datasets, such as the NIST age estimation evaluation {{NIST-FATE-AEV}}. This measures algorithm performance, not a deployed service.

2. **Conformity assessment and certification** of a whole service against the requirements of a certification scheme, such as one based on IEEE 2089.1 or ISO/IEC 27566-1, by a certification body that is itself accredited by a national accreditation body to operate that scheme. A framework standard does not on its own define everything a scheme must test.

3. **Test purchasing**, online and face to face, which shows whether technology and processes work together in real deployments, including against attempts at circumvention.

The Australian Government's Age Assurance Technology Trial {{AU-AATT}}, conducted independently by the Age Check Certification Scheme, combined laboratory evaluation and test purchasing with a review of each provider's practice statement, in the same way that conformity assessment bodies assess solutions.

Where a relying party performs age assurance in-house or relies on an upstream signal, the same kinds of evidence are needed to establish confidence in its claimed level of assurance and other characteristics. Assessment should also cover system-level properties such as privacy, unlinkability and resilience, a gap identified in {{IAB-Statement-2026}}. How regulators might recognise certification is a policy question, discussed in {{policy}}.

## Inclusion {#inclusion}

Because every method fails for some people, inclusion is achieved by offering alternatives at the required level of assurance, not by lowering the level. A person without a passport, credit history, smartphone or suitable biometric characteristics should be able to use another method. Professional vouching, in which a trusted professional attests to the age of someone without documentary evidence, is one possible route, subject to independently established requirements for its reliability and binding. No single method should therefore be the sole route to compliance.

# Reference Architecture {#architecture}

An age assertion should carry enough information for a relying party to trust it, and nothing more. This section describes the roles, the content of an assertion and four reference flows. It does not define a new protocol: each flow can be built from existing work.

## Roles {#roles}

This document uses the roles from {{Section 3.2 of RFC9998}} and describes them in terms consistent with ISO/IEC 27566-1:

* **User**: the person whose age is assured.

* **Age assurance provider**: performs the check and issues the assertion.

* **Credential issuer**: a party, which may be a state, that issues evidence of age used by a provider or held by the user.

* **Holder agent**: software that holds a reusable assertion for the user, such as a wallet, browser or operating system component.

* **Relying party**: uses the assertion to decide access, and remains responsible for compliance.

* **Policy selector and rater**: decide which threshold applies to which content in which jurisdiction. These are usually the relying party, guided by law.

~~~ ascii-art
Source of assertion         Relying party      Privacy safeguard

+--------------------+    +---------------+
| A: direct check    |--->|               |  Provider sees service;
| provider, redirect |    | receives only:|  deletes data after check
+--------------------+    |               |
+--------------------+    | - age         |
| B: user-held       |--->|   threshold   |  Issuer not involved;
| wallet or device-  |    |   result      |  single-use or ZKP proofs
| bound credential   |    | - level of    |
+--------------------+    |   assurance   |
+--------------------+    | - accountable |
| C: interoperable   |--->|   provider    |  Pairwise or blinded
| prior check by     |    | - validity and|  tokens; no network-wide
| another provider   |    |   binding     |  identifier
+--------------------+    |               |
+--------------------+    |               |
| D: upstream signal |--->|               |  Platform ideally cannot
| OS, app store,     |    |               |  see service, else must
| browser, network   |    |               |  not log
+--------------------+    +---------------+
~~~
{: #fig-flows title="Reference Flows A to D"}

Whichever route an assertion takes, the relying party should receive the same minimised set of information, and each route has its own safeguard against tracking.

## Age Assertion Information Model {#info-model}

A binary result is not enough for a relying party that remains responsible for the outcome. This section proposes a conceptual information model for an age assertion. The model describes what must be established, not what must be transmitted: some elements travel in each presentation, while others are established once through a trust framework or independently verifiable scheme rules.

| Element | What it establishes | Typically conveyed |
|---|---|---|
| Age result | The threshold met (age >= NN) or the range established | In each presentation |
| Assurance | The level of assurance and the scheme under which it was assessed | Level and scheme identifier in the presentation; detail in scheme rules |
| Provenance | The issuer or provider and the trust framework it operates under | Trust framework or trust list; the presentation carries only what is needed to find the verification key, as coarse as possible |
| Binding | Which forms of binding were established (initial, holder and contemporaneous person binding), and when | Proof of possession in the presentation; binding policy in scheme rules |
| Validity | Expiry, revocation and status semantics | Validity window in the presentation; status mechanism defined by the scheme |
| Audience and replay | The intended relying party and protection against replay | Nonce and audience in the presentation |
| Privacy properties | Whether presentations are unlinkable, and what the issuer and platform can observe | Scheme rules, so relying parties and users can rely on them without per-transaction disclosure |
| Accountability | Who is responsible for the result | Scheme rules and audit records held by the provider or scheme operator, not sent to relying parties |
{: #tab-info-model title="Age Assertion Information Model"}

Not everything needed for accountability must go to every relying party. Three sets of information should be distinguished: what the relying party needs to evaluate the assurance; what an auditor or scheme operator needs to establish accountability after the event; and what must be transmitted in every presentation. A rare issuer, a precise timestamp or other uncommon metadata can shrink the anonymity set and allow correlation even without a user identifier. Presentations should therefore carry coarse values where the relying party does not need more, for example a scheme or trust-list identifier rather than an individual provider, and a validity window rather than the time of the check.

An assertion should not carry the user's identity, date of birth, the evidence examined or any identifier that is stable across relying parties. Proposed work on ISO/IEC 27566-4 {{ISO-27566-4}} on interoperability and semantics for age assurance, not yet a published standard, would address how independently governed ecosystems can express and understand these characteristics.

## Flow A: Direct Check {#flow-a}

The relying party sends the user to a provider, by redirect or embedded component. The provider performs a check and returns a signed assertion to the relying party. This is the deployment model shown in Figure 1 of {{RFC9998}} and is widely deployed today. It can be made privacy-preserving if the provider deletes personal data once the check is complete and returns only the assertion. Its weakness is that the provider learns which relying party the user is visiting, and the user may need to repeat the check at each service.

## Flow B: User-Held Reusable Assertion {#flow-b}

A provider or issuer issues an assertion to a holder agent controlled by the user, bound to a key on the user's device. When a relying party requests proof of age, the holder agent presents the assertion, disclosing only the threshold result. Presentation can use OpenID for Verifiable Presentations {{OpenID4VP}}, mediated in the browser by the W3C Digital Credentials API {{W3C-DC-API}}, with credentials in ISO mdoc {{ISO-18013-5}} or SD-JWT VC {{I-D.ietf-oauth-sd-jwt-vc}} format. These formats and protocols are building blocks. Selective disclosure and unlinkability are different properties: a credential that reveals only "over 18" can still carry an issuer signature, credential identifier, holder key or other metadata that lets relying parties correlate presentations. Binding to a device key establishes holder binding; it does not establish who is using the device at the point of presentation ({{terminology}}).

Because the issuer is not involved at presentation, it does not learn which relying parties the user visits, provided it does not also operate the wallet or receive status or revocation checks that reveal them. To prevent relying parties from correlating presentations, issuers can issue batches of single-use credentials (as in the EU age verification app blueprint {{EU-AV-Blueprint}}) or use zero-knowledge proofs, so that no signature, key or identifier repeats across presentations. The resulting privacy depends on how issuance, metadata and verifier behaviour are constrained, not on the credential format alone.

## Flow C: Interoperability Network {#flow-c}

A relying party asks its own contracted provider for an assertion. If the user has already been checked by another provider in the same network, the relying party's provider obtains a fresh assertion based on that earlier check rather than checking the user again. Networks need rules on equivalent standards, liability and the communication of levels of assurance, and must avoid a persistent network-wide identifier.

One design that meets this aim routes reuse through the user's browser or holder agent rather than between providers' servers. The relying party's provider asks the user agent for a reusable token. The user agent obtains from the originating provider a fresh, blindly signed, single-use token stating the age result and level of assurance, so the originating provider does not learn which relying party or which provider asked for it. The relying party's provider verifies the token against the originating provider's published key, obtained from the scheme's trust list. Because each token is used once, neither provider can link presentations. Variants in which providers exchange assertions directly between servers are simpler to deploy, but expose the requesting party to the originating provider and depend more on scheme rules.

The euCONSENT project {{euCONSENT}} piloted interoperable age assurance and parental consent between multiple providers across EU member states. It demonstrated that providers can accept each other's checks; it did not by itself demonstrate every privacy property described here.

## Flow D: Upstream Age Signal {#flow-d}

An operating system, app store, browser or network supplies an age range, usually established at account creation or set by a parent or guardian. The relying party queries it through a platform interface. This can be low friction and useful for parental controls. Where a relying party relies on such a signal to meet a legal requirement, the signal must meet the same conditions as any other assertion: a stated level of assurance, independent assessment and a clearly accountable party ({{layered}}).

A platform usually establishes the age of the account holder, not of the person using the device at a given moment. Shared devices and family accounts make that distinction material. A relying party should treat such a signal accordingly unless the platform binds it to the current user, for example through robust multi-user support.

### Comparison of Flows {#flow-comparison}

| Flow | What each party learns | Cryptographic mechanisms available | What rests on organisational trust |
|---|---|---|---|
| A: direct check | Provider: the evidence and which relying party asked. Relying party: the result | Signed assertion; audience-bound nonce | Provider deletes evidence and does not profile requests |
| B: user-held assertion | Issuer: the evidence, at issuance only. Relying party: the result and presentation metadata. Platform: the request, if it mediates | Selective disclosure; single-use credentials or zero-knowledge proofs; device-bound keys | Wallet and platform do not log presentations; issuer does not observe status checks |
| C: interoperable network | Originating provider: that a reuse occurred. Relying party's provider and relying party: the result | Blind or pairwise single-use tokens; signed assertions; trust lists | Scheme rules on liability, equivalence and logging |
| D: upstream signal | Platform: which relying party requested a signal, unless the design prevents it. Relying party: the age range | Platform-signed signal; on-device evaluation | Platform does not log requests; signal reflects the current user |
{: #tab-flows title="Comparison of Flows"}

## Triple-Blind Operation {#triple-blind}

A triple-blind flow aims at three properties: the relying party receives no identifying information beyond the minimum age-related assertion necessary for its purpose; the provider or issuer cannot learn which relying parties the user visits; and the operating system, browser, app store or wallet provider cannot learn this either. Relying parties should also be unable to link presentations by the same user. Each property can be achieved in two quite different ways: by cryptographic or architectural design, so that a party is technically unable to learn the information, or by operational and legal controls, so that a party that can observe it commits not to retain or use it. The second is weaker and should be described as such.

| Protection against | What it should not learn | Enforceable by design through | Otherwise reliant on |
|---|---|---|---|
| Relying party | Identity, date of birth, evidence; links between visits | Selective disclosure; single-use credentials or zero-knowledge proofs; minimal metadata | Verifier policy and data protection law |
| Provider or issuer | Which relying parties the user visits | Issuer absent at presentation (Flow B); blind issuance; privacy-preserving status checks | Deletion and audit commitments (Flow A) |
| Wallet provider | Which relying parties the user visits | Wallet software that keeps presentation records on the device only | Operator commitments, with independent assessment of compliance |
| Platform (OS, browser, app store) | Which relying parties request age | Presentation paths that do not pass through platform mediation | Platform commitments not to log or use requests |
{: #tab-triple-blind title="Triple-Blind Properties"}

The last row matters. Where presentation is mediated by the browser or operating system, for example through the W3C Digital Credentials API, the user agent can inspect the request and the requesting origin by design. A platform's commitment not to retain that information is not equivalent to being unable to observe it.

Browsers and operating systems necessarily process the addresses of sites that users visit, so it is not realistic to require that they never know the destination. The triple-blind requirement concerns something narrower: that the platform cannot observe, or does not record, that an age assurance transaction took place with a given relying party, or its result. A platform that knows a user visited a site, but not that the site asked for proof of age or what was proved, meets the requirement. An age assertion may itself be personal data under data protection law, particularly when combined with other information the relying party holds, which is why the requirement is framed as minimisation rather than as the absence of personal data.

Blind-signature token schemes such as Privacy Pass {{RFC9576}} {{RFC9578}} can be one component of an unlinkable presentation layer, by separating the party that attests age from the party that redeems tokens. They do not themselves establish age, a level of assurance or binding to the person, and the Privacy Pass architecture describes information that can leak depending on the deployment model. They need a separate age attestation mechanism and protection against token transfer. At least one option that is triple-blind by design, not only by policy, should be available in any ecosystem.

## Mapping to Existing Specifications and Work in Progress {#mapping}

| Function | Existing specifications |
|---|---|
| Credential format with selective disclosure | ISO/IEC 18013-5 mdoc; SD-JWT {{RFC9901}} and SD-JWT VC {{I-D.ietf-oauth-sd-jwt-vc}}; W3C Verifiable Credentials |
| Request and presentation protocol | OpenID4VP {{OpenID4VP}}; OpenID Connect claims for direct checks |
| Browser mediation | W3C Digital Credentials API {{W3C-DC-API}} |
| Unlinkable tokens | Privacy Pass {{RFC9576}} {{RFC9578}}; zero-knowledge proof schemes |
| Level of assurance and evaluation | IEEE 2089.1; ISO/IEC 27566-1; ISO/IEC 30107-3 for presentation attack detection |
| Assurance metadata across ecosystems | Proposed ISO/IEC 27566-4 {{ISO-27566-4}} |
{: #tab-mapping title="Mapping to Existing Specifications"}

Each entry is a building block. None of them alone delivers the properties described in {{info-model}} and {{triple-blind}}; those depend on how the components are combined, configured and assessed.

## Trust Model {#trust-model}

Signature verification is necessary but not sufficient. Before acting on an assertion, a relying party needs to establish that:

1. the assertion is authentic: its signature verifies against a key of the stated issuer or provider;

2. the issuer or provider is trusted for this claim, which the relying party learns from a trust framework, scheme operator or trust list rather than from the assertion itself;

3. the level of assurance, and any other assurance characteristics relevant to the use case such as binding or privacy properties, meet the relying party's requirements;

4. the assertion is valid: unexpired, not revoked and intended for this relying party; and

5. the presentation is bound to the person presenting it to the degree the use case requires, recognising that proof of control of a credential (holder binding) does not establish that its legitimate holder is the person present (contemporaneous person binding).

The trust framework supplies verification keys, trust lists and assurance policies to relying parties in advance. It need not be involved in individual transactions, which keeps it from becoming a point of observation. Proposed ISO/IEC 27566-4 work on interoperability is intended to let relying parties make these judgements across independently governed ecosystems.

# Layered Deployment {#layered}

No technology is 100% effective, so age assurance works best as one layer among several. Establishing age lets a service apply age-appropriate protections. It does not replace safer design, moderation, parental controls or law enforcement. Service, device and network layers can each contribute, and every layer relied on for compliance should meet the same standards of assurance and accountability.

## Service Layer {#service-layer}

The relying party is where the decision to grant or restrict access is made, and where legal responsibility usually sits. It determines the assurance characteristics appropriate to its risk, including but not limited to a level of assurance, chooses one or more providers and applies the result. This document treats the service layer as the primary point of decision, informed by assertions that may originate at any layer.

## Operating System and App Store Layer {#os-layer}

Operating system and app store signals can make age assurance easier, particularly where parents have set an age range for a child's device. They are well suited to laws that require parental consent or controls. Three conditions apply where they are used to meet legal obligations:

1. **Equivalent assurance.** The signal carries a stated level of assurance, is independently assessed and has an accountable party, as for any other source of age assertions.

2. **Architectural openness.** The interface between platform and service is an open standard. Relying parties can accept assertions from independent providers through the same interface (provider independence). Assertions are portable between trust frameworks, and no central intermediary is mandatory, so there is no single point of failure.

3. **No tracking.** Where the architecture allows, the platform should be technically unable to learn which relying parties request the signal. Where it can observe requests, it must not retain or use them, and that weaker, policy-based protection should be disclosed ({{triple-blind}}).

{{IAB-Statement-2026}} considers device-based mechanisms the most promising current approach, provided the interface between device and service is an open standard and shared devices have robust multi-user support. This document agrees that on-device processing offers strong privacy. It notes that on-device processing is not limited to operating system vendors: independent providers can run verification and estimation on the user's device ({{methods}}), delivering the privacy benefit without concentrating control in a few platforms.

## Network Layer {#network-layer}

"Network" is often listed among the layers at which age assurance can operate, but there are few examples of it in practice. Operators already apply category-based filtering for subscribers who choose it, and in some jurisdictions by default on mobile connections. Such filtering avoids new personal data collection. The network layer may also have a more constructive role than blocking alone.

A mobile network operator often holds verified information about its account holder, including their age, and knows whether the account holder or a parent or guardian has set controls on a line. In principle, it could express this as a privacy-preserving age-range signal (for example under 13, 13 to 17 or 18+) rather than an enforcement decision. For example, it could indicate to a relying party, at the user's request, that a connection is subject to under-18 controls, without revealing the subscriber's identity. Such a signal could trigger safer defaults on a service, or a stronger check, without the network inspecting content. Because the person using a line may not be the account holder, such a signal describes the controls on the line rather than the age of its user.

Network signals face the same conditions as other upstream signals. They must be user-initiated or user-visible, must not create a persistent identifier observable by services, and must not be a vector for network-level censorship. They complement, rather than replace, checks at the service layer.

## Geolocation {#geolocation}

Age requirements vary by jurisdiction, so relying parties need some assurance of where a user is. Location assurance should be proportionate and privacy-preserving, for example by using coarse location rather than continuous tracking. VPN circumvention is a risk to be addressed in proportion to harm. Any approach to VPNs should respect their legitimate privacy and security benefits for users of all ages. Device-based location checks can return binary responses that confirm only whether a user is within a regulated jurisdiction, not their current location. Privacy-preserving location assurance could also use cryptographic proofs of jurisdictional eligibility, provided the underlying location evidence is trustworthy. Such approaches require an explicit trust model and measures against location spoofing. They should avoid unnecessary disclosure of precise location or persistent identifiers.

# Determining the Appropriate Level {#determining}

The appropriate level of assurance for a use case is a decision for legislators, regulators and services. Neither IEEE 2089.1 nor this document prescribes levels for particular services. A level is only part of the requirement: the binding, privacy and inclusion characteristics a context needs should be specified alongside it. The following considerations bear on that decision:

* **Severity of harm** the restriction is meant to prevent, and whether it is reversible.

* **Whether a specific legal age limit applies**, and whether a date of birth or only a threshold is needed.

* **Incentive and capability to circumvent**, including the likelihood of collusion by adults.

* **Whether the aim is blocking or tailoring**, since age-appropriate design may need only an age band.

* **The population affected**, including people who lack documents or for whom some methods perform less well.

* **Privacy impact** of the methods that could meet a given level, and the availability of methods with lower impact.

* **The size and nature of an existing user base**, which affects the feasibility of checking existing accounts.

* **The consequences of error in both directions**: wrongly admitting someone below the threshold, and wrongly excluding someone above it.

Core Internet infrastructure (connectivity, routing and DNS) should remain neutral, supporting only optional, user-chosen signals.

# Recommendations {#recommendations}

The following are this document's technical recommendations. Proposals that concern regulation rather than Internet architecture are collected in {{policy}}.

1. **Express assurance in standard terms.** Assertions should carry a level of assurance on a standard scale, so that requirements can be stated as outcomes rather than technologies. A level summarises confidence in the result; it does not replace the characteristics in Recommendation 2.

2. **Treat assurance as multidimensional.** Privacy properties, binding characteristics and inclusion should be expressed alongside the level of assurance, not folded into it.

3. **Disclose only what is needed.** Where a relying party needs to know only whether a user is above or below a threshold, it should not ordinarily receive the user's identity, date of birth or the evidence used.

4. **Do not retain or repurpose.** Personal data used for age assurance should not be kept beyond what is needed to provide, improve and audit the service or meet legal obligations, with transparency about any retention.

5. **Offer at least one option that is triple-blind by design.** Every ecosystem should include a route in which neither the relying party, the provider nor the platform can build a record of the age assurance transactions a user makes, enforced technically rather than only by policy.

6. **Make assurance information available along the chain.** Level of assurance, provenance and validity should remain determinable when an assertion is reused or passed between systems, through the presentation or the trust framework, without exposing more metadata than the relying party needs.

7. **Reuse without tracking.** Interoperability must not depend on a persistent identifier that allows relying parties or providers to correlate a user's activity.

8. **Build in architectural openness.** Open interfaces, provider independence, portability of assertions between trust frameworks and no mandatory central intermediary.

9. **Offer alternatives.** No single method should be the only route. Users without documents, credit histories, smartphones or suitable biometric characteristics need another way through.

10. **Treat age as distinct from identity.** Age can be derived from identity, but it can also be established without identity, and some users will prefer that.

11. **Avoid unnecessary checks.** Relying parties should not request age assertions for content or functions with no age-related requirement, and should restrict only the content or features an obligation covers rather than a whole service.

12. **Handle failure explicitly.** Architectures should define fallback methods, routes to challenge and correct a wrong determination, and behaviour when a provider or status service is unavailable ({{failure}}).

13. **Standardise the missing pieces.** The IETF, W3C, OpenID Foundation, ISO and IEEE should coordinate on how a website expresses an age requirement, how assurance metadata is carried and how unlinkable reuse is achieved, building on existing work rather than a separate age assurance stack.

# Security Considerations {#security}

No age assurance system is immune from attack. Mitigations should be proportionate to the risk of the use case and tested independently.

The architecture should be assessed against at least the following adversaries: a user below the threshold seeking access; an adult colluding with that user, for example by completing a check or lending a credential or device; a compromised or malicious wallet or holder agent; a dishonest or compromised issuer or provider; a malicious relying party seeking to identify or track users; and compromised ecosystem infrastructure, such as a trust list or status service. Privacy and assurance claims should state which of these adversaries they address.

* **Presentation attacks.** Masks, printed photos and replayed video presented to a camera. Mitigated by presentation attack detection evaluated to ISO/IEC 30107-3.

* **Injection attacks.** Synthetic or manipulated media injected into the capture pipeline, bypassing the camera. Mitigated by capture integrity checks and injection attack detection, evaluated for example to CEN/TS 18099.

* **Forged or altered evidence.** Mitigated by validating issuer signatures on digital credentials and security features on documents.

* **Credential sharing and collusion.** An adult passing a reusable assertion, or performing a check, on behalf of a minor. Device possession and local authentication do not prevent this on their own: a parent can hand over an unlocked device or its PIN, and a local biometric unlock shows only that an enrolled user is present. Contemporaneous person binding, short validity periods and limits on additional enrolment raise the bar for higher-risk uses.

* **Replay.** Reuse of an assertion at another relying party or another time. Mitigated by audience restriction, nonces and expiry.

* **Malicious relying parties.** Collecting excess metadata or linking presentations. Mitigated by minimal, coarse metadata and single-use or zero-knowledge presentations.

* **Compromised trust infrastructure.** A subverted trust list or status service could admit bad issuers or track status checks. Mitigated by distributing trust lists in advance, privacy-preserving status mechanisms and audit of scheme operators.

* **Phishing and normalisation of data requests.** Users who become used to sharing documents with unfamiliar sites are more exposed to fraud, as noted in {{RFC9998}}. Mitigated by architectures that never send documents to relying parties, by recognisable and certified providers, and by user-held credentials presented through trusted browser or wallet interfaces.

* **Breach of provider data.** Mitigated by not retaining personal data after the check, by on-device processing, by separating providers from relying parties and by security controls whose effectiveness is independently assessed. Reported breaches of retained identity documents illustrate why minimisation and non-retention matter.

* **Concentration risk.** Reliance on a single platform or provider creates a single point of failure and attack. A plural, interoperable market reduces it.

## Failure Handling {#failure}

Every method fails for some people, and every service is sometimes unavailable. Architectures should define:

* what happens when a method cannot reach a result, normally by offering another method at the same level rather than a lower one;

* how a person can challenge and correct a wrong determination, including one made by estimation or inference, without disclosing more data than the original check required;

* what a relying party does when a provider, issuer or status service is unavailable, and whether it fails open or closed given the risk; and

* how revocation of a compromised issuer, key or credential reaches relying parties.

# Privacy Considerations {#privacy}

Privacy should be designed into age assurance rather than traded against effectiveness. The architectures in {{architecture}} show that independently measurable effectiveness, strong privacy protections and interoperability can coexist, provided the full system is engineered and assessed to deliver them.

* **Minimisation.** Relying parties receive a threshold result, not identity, date of birth or evidence. Providers process only what the chosen method needs.

* **Retention.** Images, documents and other inputs are deleted once the check is complete, except where retention is needed to audit the service or meet a legal obligation, and that retention is disclosed.

* **Purpose limitation.** Data processed for age assurance is not reused for profiling, advertising or other purposes.

* **Unlinkability.** Neither providers, issuers nor platforms should be able to learn which relying parties a user visits, and relying parties should not be able to correlate one user across services. Batch-issued single-use credentials, zero-knowledge proofs and blind-signature tokens support this.

* **Organisational separation.** Independent providers keep the personal data used in a check separate from the relying party, which may have commercial incentives to collect it. Independent providers are also more easily regulated and audited.

* **Age is not identity.** Methods that establish age without identity, such as estimation, or on-device age verification give users a choice not to disclose identity at all.

* **Location.** Jurisdiction can often be established at a coarse level, avoiding precise or continuous geolocation and disclosing only whether or not a user is within a regulated jurisdiction for a particular use case.

Some privacy costs remain even in well-designed systems, for example where a platform mediates presentation or a provider must briefly process a face or document. The properties above reduce them substantially, and can be specified in standards, tested in certification and enforced by data protection regulators.

# Scope and Policy Neutrality {#scope}

This document does not address whether age restrictions should be imposed, on which content or services, or at what ages. Those are decisions for legislatures, regulators and services, and they engage rights that must be balanced, including children's rights under the UN Convention on the Rights of the Child and the rights to privacy and freedom of expression of users of all ages.

This document is neutral on whether restrictions should exist, but it is not neutral about how safely and privately they should be implemented where they do exist. An architecture that implements a restriction should protect freedom of expression, access to information and association by minimising what is disclosed and by avoiding checks where no requirement applies. It should also provide a route to challenge and correct a wrong determination, since children and adults whose age is incorrectly assessed may otherwise lose access to lawful content or services.

Whether a jurisdiction should impose an age restriction, what age should apply and to which services are not questions the IETF needs to resolve in order to produce useful Internet architecture, and this document expresses no view on them. The same applies to broader policy arguments, such as whether age assurance burdens all users disproportionately. Technical feasibility, by contrast, is within scope: verification, estimation and inference are deployed at scale today under regimes in the UK, the EU, Australia and US states. Deployment shows feasibility; it does not by itself demonstrate effectiveness, privacy or inclusive access, which must be measured ({{measuring}}). The technical community can contribute most by making whatever restrictions are adopted as accurate, private, inclusive and accountable as possible.

The author is Executive Director of the Age Verification Providers Association, a trade body for providers of age assurance technology. The views in this document draw on published positions held in common by its members, and are offered in the author's individual capacity under IETF participation rules.

# IANA Considerations

This document has no IANA actions.

--- back

# Comparison with draft-knodel-age-arch {#comparison}

| Topic | draft-knodel-age-arch-01 | This document |
|---|---|---|
| Terminology | Treats age assurance as an umbrella term (Section 2.3) but states that biometric estimation is not age assurance (Section 2.4) | Uses terminology consistent with ISO/IEC 27566-1 throughout: verification, estimation and inference are all methods of age assurance |
| Facial age estimation | Assesses reliability with reference to NIST IR 7995 (2014) | Cites NIST IR 8525 (2024), the ongoing NIST evaluation and the Australian trial, and requires measured performance under deployment conditions |
| Document checks | Much of the analysis assumes hard-document review, while noting selective disclosure | Treats copying documents to relying parties as poor practice; describes provider-side inspection and selective disclosure |
| Analytical dimensions | Efficacy and privacy cost, organised by trust anchor | Adds assurance, accountability, interoperability and reuse; treats assurance as multidimensional |
| Privacy | Treats privacy cost as inherent in most methods | Distinguishes privacy enforced by design from privacy that rests on policy, and accepts that some costs remain |
| Network layer | Network filtering as a low-privacy-cost baseline | Network signals as one optional layer, subject to the same assurance and tracking conditions |
| Feasibility | Concludes that advanced approaches are currently infeasible or have significant downsides | Deployment at scale shows feasibility; effectiveness, privacy and inclusion must still be measured |
| Policy | Includes some policy conclusions alongside architectural analysis | Neutral on whether, where and at what age to restrict; not neutral on how safely and privately restrictions are implemented |
{: #tab-comparison title="Comparison with draft-knodel-age-arch"}

# Policy Considerations {#policy}

This appendix collects proposals that concern regulation rather than Internet architecture. They are offered for context and are not requirements of this document.

* **Outcome-based mandates.** Requirements should specify the assurance outcomes needed, such as a level of assurance together with any binding or privacy characteristics the context requires, rather than particular technologies, consistent with {{IAB-Statement-2026}}, {{Ofcom-HEAA}} and {{EC-Art28}}.

* **Certification.** Providers, in-house checks and upstream signals relied on for compliance could be certified under schemes that cover system-level properties as well as accuracy, supported by test purchasing.

* **Presumption of compliance.** Regulators could consider a presumption of compliance for relying parties that use a certified provider at the required level. This is not current law in most jurisdictions: Ofcom, for example, does not accredit or approve individual providers, and a service remains responsible for its own compliance.

* **No mandated sole route.** State credentials, wallets and platform signals are valuable sources of age assurance, but should not be mandated as the sole or privileged route for private sector uses. Independent providers should be able to consume them.

* **Enforcement.** Consistent enforcement, including against offshore non-compliant services, avoids penalising compliant services and displacing users to riskier ones.

# Acknowledgments
{:numbered="false"}

The author thanks the authors of draft-knodel-age-arch for setting out the concerns this document responds to, and the participants of the IAB/W3C workshop.
