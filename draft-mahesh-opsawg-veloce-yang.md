---
title: "YANG deVELopment PrOCEss and maintenance (VELOCE)"
abbrev: "VELOCE"
category: info

docname: draft-mahesh-opsawg-veloce-yang-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus: true
v: 3
area: "Operations and Management"
workgroup: "Operations and Management Area Working Group"
keyword:
 - yang
 - development process
 - maintenance
venue:
  group: "Operations and Management Area Working Group"
  type: "Working Group"
  mail: "opsawg@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/opsawg/"
  github: "mjethanandani/veloce"
  latest: "https://mjethanandani.github.io/veloce/draft-mahesh-opsawg-veloce-yang.html"

author:

 -
   fullname: "Mahesh Jethanandani"
   organization: Arrcus
   email: "mjethanandani@gmail.com"

 -
   fullname: "Qin Wu"
   organization: Huawei
   email: "bill.wu@huawei.com"

normative:

informative:

...

--- abstract

This document describes a YANG deVELopment PrOCEss and
maintenance (VELOCE) that is more suitable for the development
of YANG modules or YANG modules update within the IETF.

Discussion Venues

   This note is to be removed before publishing as an RFC.

   Source for this draft and an issue tracker can be found at
   https://github.com/mjethanandani/veloce/tree/main.

--- middle

# Introduction

IETF has used RFCs to publish its documents. However, RFCs,
which are text documents, are not well-suited for iterative
development of YANG modules that come in the form of source
code.

This document proposes a new approach for documenting and
publishing IETF YANG modules.  While this document mainly
focuses on the IETF modules, IANA modules that are included in
drafts, and removed ultimately on publication, can follow a
similar process during the development of the IANA module.

This document proposes that the publishing of a YANG module
should be split into two parts: the text portion, hereby
referred to as the prose, and the YANG module. The prose
SHOULD continue to be used for describing the model, defining
IANA Considerations, defining the Security Considerations,
describing any Operational Considerations, capturing the
Normative and the Informative References, etc. The YANG module,
along with any related files such as YANG SID files,
should be developed and maintained in a separate Source Code
Mechanism (SCM) repository such as GitHub. The SCM SHOULD
provide a stable link to the YANG module, which should then be
included as a reference in the document.

There are several reasons to develop the YANG module in an
SCM. SCM provides version control and improves traceability of
changes. Modern SCM provides the ability for Continuous
Integration/Continuous Development (CI/CD). YANG modules can
be fully validated before they are published. Changes to the
module can be submitted by providing changes to the affected
portions of the source code instead of the entire
module. Reviews and comments can be gathered on the changes
being proposed. This iterative approach lends itself to faster
development and fixing of issues in YANG modules.

Guidance for writing YANG modules is discussed in {{!RFC9907}}.
Guidelines related to code components (section3.2 of {{!RFC9907}})
or citations to references listed in the YANG module do not apply to VELOCE.

# Conventions and Definitions

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and
"OPTIONAL" in this document are to be interpreted as described in
BCP 14 {{!RFC2119}} {{!RFC8174}} when, and only when, they appear in all
capitals, as shown here.

# VELOCE Procedure {#sec-procedure}

The following practices should provide the necessary guidance
on how a WG develops a new YANG module or updates an existing
YANG module:

It is RECOMMENDED that IETF-hosted repositories
be used. See section 1.3 of Working Group GitHub Usage
Guidance {{!RFC8874}}. Integration using third-party hosted
repositories MAY be used for experimentation purposes.

A new repository MUST be created by the WG
Chairs following the procedure in section 3.2 of Working Group
GitHub Usage Guidance {{!RFC8874}} for to develop or maintain a YANG
Module. For a new module, this SHOULD happen when
the module is adopted as a WG item. It MAY happen for
individual drafts, and that is left to the discretion of the
chairs. However, once the document is adopted as a WG item,
the repository SHOULD reside under the auspecies
of IETF controlled repository and managed by the WG. The
name of the repository SHOULD reflect the name
of the draft. In addition, the chairs MAY make
sure that an appropriate CI/CD YANG validation is in place.  It
is RECOMMENDED that a containerized build
environment be provided in the repository to enable local
validation of YANG modules (e.g., via yanglint) independently of
the CI/CD pipeline, and to ensure a consistent development
environment across all contributors.

The procedure for managing WG documents (e.g., assign editors)
applies for managing YANG modules (section 6.1 of IETF Working
Group Guidelines and Procedures {{!RFC2418}}. For considerations
related to granting editors write and administrators' right refer to
section 3.3 of Working Group GitHub Usage Guidance {{!RFC8874}}.

Other administrative policies as they relate to migration,
personal change or the WG closing is defined in the Working
Group GitHub Administration {{!RFC8875}}.

A release tagging mechanism should be defined to track the
intermediate versions referenced by WG I-Ds and by the RFC,
once published. This can come in the form of a 'git tag' or by
having a branch that corresponds to the version of the draft.

Contribution methods for the YANG module are similar to those
defined in section 4 of Working Group GitHub Usage
Guidance {{!RFC8874}}. This includes the use of Issues to track open
issues regarding the module. They, along with corresponding
links to the Pull Request (PR), are a useful way to record
decisions made by the WG.

PR allow for a user to request a change to the repository. A
user does not need to have write access to the repository. A
fork of the repository allows the user to make changes,
validate them, and post the changes as a PR against the WG
repository. Editors of the YANG module are encouraged not to
accept changes into the "main" or "master" branch of the
repository. Instead, they should be directed to a branch
that is used for development. This allows the editors to review
the changes and make sure that they are in line with the WG
consensus before they are merged into the main branch.
This also allows the editors to make sure that the changes are properly
validated before they are merged into the main branch.

A procedure for assessing consensus is discussed in section 7 of Working
Group GitHub Usage Guidance {{!RFC8874}} and SHOULD be
followed when accepting changes to the module.

The YANG module MUST NOT be inserted in the
document; instead, a link to the above repository
MUST be included in the document.  The link
MUST point to a specific tagged version of the
YANG module (e.g., a git tag or commit hash), not to the HEAD of
a branch, so that the module's contents at RFC publication time
are permanently retrievable and verifiable.

YANG SID files {{!RFC9595}}, when applicable (e.g.,
for YANG/CBOR encoding), SHOULD reside in the
SCM repository rather than in the document.  The use of RFC 8792
folding for SID files in Internet-Drafts is discouraged, as it
is not compatible with current YANG Doctor tooling.

A bis version of the initial RFC MAY be
considered if a major change needs to be added in the
document. Such a decision is left to the WG. WG may
decide to update an adopted YANG module in the IETF
repository and only update the RFC to change the reference
to the YANG module.

# Experimental Plan {#sec-experiment}

Much like other experimental documents, this document tries to
answer the following four questions as they relate to
experimental documents.

## What is the goal {#sec-goal}

The goal of the experiment is to determine how YANG modules
can be developed outside of an RFC, while making sure that
all IETF processes are followed, including WG involvement in
the development of the module, and rough consensus of the WG
and the IETF as a whole, before it is "published".

A key objective is to balance speed, quality, and community
contribution.  The experiment should demonstrate a faster
path to delivering well-formed YANG modules, while not
sacrificing the quality and the community involvement that
the IETF process requires.  In particular, the experiment
aims to address the pain point of the -bis revision process,
where re-publishing a large document just to update a small
portion of the YANG module creates unnecessary delays due to
review comments on otherwise unchanged sections.

## How will the experiment be conducted {#sec-how}

YANG modules developed in the IETF fall broadly into two
categories. They can be new modules, or they can be a "bis"
version of the module. The experiment will consist of two or
more YANG modules, such that at least one of them is a new
YANG module, and the other is a "bis" version of the YANG
module. This is being done to make sure that the experiment
covers all the IETF processes related to the development of
YANG modules.

Participants in the experiment are encouraged to document
their overall experience, including whether the SCM-based
approach genuinely improved participation and velocity, or
whether observed speed gains were attributable to other
factors such as low contention on a specific module.  This
qualitative feedback is as important to the experiment as
the publication outcome itself.

## How will success be determined {#sec-determine}

The primary "exit criteria" for the experiment will be
successful publication of the YANG modules identified as
part of the experiment, within the timelines defined in
{{sec-timeline}}.

Beyond publication, success will also be evaluated based on
whether the process improved community participation in YANG
module development, and whether participants found the SCM-
based workflow reduced friction compared to the traditional
RFC-embedded approach.  A report documenting the overall
experience and outcomes of the experiment SHOULD be produced
at the conclusion of the experiment.

## What is the anticipated timeline {#sec-timeline}

YANG modules have traditionally taken a long time to develop,
sometimes taking over four years. However, for the purpose
of this experiment, and since the idea is to demonstrate a
faster way for a new YANG module to be developed, the
timelines for the experiment are as follows:

A new YANG module should be published within two years
of the start of the experiment.
A "bis" version of an existing YANG module, where the
primary motivation is incremental updates rather than a
ground-up redesign, should be published within one year.

If the experiment takes longer than these timelines, the
experiment should be deemed to have failed.  At that time,
an analysis can be done as to why it failed and determine
if the experiment should be repeated.

If the experiment succeeds, then this document can be
classified as a BCP, and the process be followed for all
YANG modules developed in IETF.

# Operational Considerations {#sec-operational}

The separation of YANG modules from their companion documents has
implications for the YANG review process.  YANG Doctors
SHOULD review the YANG module at the specific
tagged version referenced by the document, using tooling that
can retrieve and validate modules directly from the SCM
repository.

Working Groups adopting VELOCE are encouraged to define
milestone-based development targets for YANG modules.  A phased
approach, where an initial version covering core functionality is
published within a defined timeframe, with subsequent updates
published as needed, is preferable to indefinitely delaying
publication while pursuing completeness.

# Security Considerations

The security considerations discussed in Section 10 of
{{!RFC8874}} apply here.


# IANA Considerations

This document has no IANA actions.

--- back

# Acknowledgments
{:numbered="false"}

This draft is triggered by the discussion in NEMOPS IAB workshop.

Thanks to the participants of OPSAWG for their comments that
have helped shape this draft.  In particular, thanks to
Jeffrey Haas, Joe Clarke, Dhruv Dhody, Per Andersson，Italo Busi,
and Mohamed Boucadair for their feedback during IETF 125.
