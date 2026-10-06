<!-- regenerate: on (set to off if you edit this file) -->

# YANG deVELopment PrOCEss and maintenance (VELOCE)

This is the working area for the individual Internet-Draft, "YANG deVELopment PrOCEss and maintenance (VELOCE)".

* [Editor's Copy](https://ietf-opsawg-wg.github.io/veloce/#go.draft-ietf-opsawg-veloce-yang.html)
* [Datatracker Page](https://datatracker.ietf.org/doc/draft-ietf-opsawg-veloce-yang)
* [Working Group Draft](https://datatracker.ietf.org/doc/html/draft-ietf-opsawg-veloce-yang)
* [Compare Editor's Copy to WG Draft](https://author-tools.ietf.org/api/iddiff?doc_1=draft-ietf-opsawg-veloce-yang&url_2=https://ietf-opsawg-wg.github.io/veloce/draft-ietf-opsawg-veloce-yang.txt)

## Working method

### Proposing a change

Open an issue describing the problem or suggestion. If you're ready to
propose text at the same time, you can open a PR directly instead --
neither is required before the other.

All listed authors are considered editors of this draft: any author may
pick up an open issue and propose text for it in a PR, not just the
original filer.

### Branches

Work directly against `main`; there is no longer a per-version branch to
target. Use GitHub's "Create a branch" link from the issue page (in the
issue's sidebar) to create your working branch -- this gives it a
name tied to the issue automatically, so there's no fixed branch-naming
convention to follow.

Link your PR to the issue it addresses using the Development panel on
the PR page, or by including `Closes #<issue>` in the PR description, so
the issue closes automatically when the PR merges.

### Review and merge

Two approvals are required before a PR can be merged (enforced by branch
protection). Issues and PRs can be discussed on GitHub at any time, and/or
on the biweekly VELOCE call (see the mailing list for the schedule) --
reaching 2 approvals does not require waiting for the next call.

### YANG module changes

Changes to the YANG module itself (as opposed to the narrative text) may
also require an entry in the IANA File/Module References registry -- see
the IANA Considerations section of the draft, and the registration
template there, for that process.

### Building the draft

See "Command Line Usage" below.

## Contributing

See the
[guidelines for contributions](https://github.com/ietf-opsawg-wg/veloce/blob/main/CONTRIBUTING.md).

The contributing file also has tips on how to make contributions, if you
don't already know how to do that.

## Command Line Usage

Formatted text and HTML versions of the draft can be built using `make`.

```sh
$ make
```

Command line usage requires that you have the necessary software installed.  See
[the instructions](https://github.com/martinthomson/i-d-template/blob/main/doc/SETUP.md).

