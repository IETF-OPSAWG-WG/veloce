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
 - next generation
 - unicorn
 - sparkling distributed ledger
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

This document describes a YANG deVELpment PrOCEss and
maintenance (VELOCE) that is more suitable for the development
of YANG modules or YANG modules update within the IETF.

Discussion Venues

   This note is to be removed before publishing as an RFC.

   Source for this draft and an issue tracker can be found at
   https://github.com/mjethanandani/veloce.

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

Guidance for writing YANG modules is discussed in {{?RFC9907}}.
Guidelines related to code components (section3.2 of {{?RFC9907}})
or citations to references listed in the YANG module do not apply to VELOCE.

# Conventions and Definitions

{::boilerplate bcp14-tagged}


# Security Considerations

TODO Security


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
