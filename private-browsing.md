# Private Browsing Mode

## "Private Browsing" and Web Browsers

All popular web browsers include some mode or method for the user to indicate
that they want "additional" privacy, beyond what a typical browsing experience
would provide.  In some cases, the mere use of a particular browser (e.g.
Tor Browser Bundle) may indicate a user preference for heightened privacy.

Browser vendors implement different protections, target different threat
models, and generally forward different aims in their implementations of a
"private browsing" mode.  This document does not aim to prescribe any
particular behavior that browser vendors should follow when in a "private
browsing" mode.  This document only aims to recognize and stand in for
an expressed desire for more privacy by the user, beyond whats provided by
typical browsing. Standards authors can then use this signal to suggest
or instruct different behaviors browser functionality, when users have
signaled this additional privacy desire.


## Aim of this Document

This document aims to solve several related problems.


### Supporting Privacy in Standards

First, web users desire a web with different privacy / functionality trade offs
when performing different browsing actions. It may be desirable for standards
to describe functionality when the user has requested heightened privacy.
Examples of this include different resolutions in geolocation, different
resolutions in timing information, different cookie and storage policies, etc.
There is currently, no way for standard documents to describe
additional-privacy, but still in-standard, functionality, beyond ad-hoc methods.

This document hopes to give standards authors a commonly understood signal
to key off.


### Supporting Web-Compatibility

Second, the lack of a "standards-compliant, privacy-focused" definition creates
web compatibility difficulties for web authors.  Currently, each browser
makes different decisions about how to violate web standards to protect
user privacy. The particulars of these privacy-protecting modifications
differ from vendor to vendor (and sometimes, version to venison), leaving
web authors unclear on what functionality will be available, even in a
"private browsing" mode.

This document hopes to form the basis for an eventual common set of
functionality that web authors can target, without breaking their applications
in "private browsing" modes.


## Further Clarifications of What This Document Is Not

For clarity purposes, here is an incomplete enumeration of explicit non-goals
of this document.

### Defining Vendor's Implementations of Private Browsing Modes

Different browser vendors will implement private browsing modes in a way
that fit the aims of the vendor and the browser's users. This document
does not aim to prescribe any specific functionality (floor or ceiling)
that browser vendors should implement in their respective private browsing
modes. The target of this document is foremost standards authors, followed
by (and indirectly) site authors.

### Comparison of Existing Private Browsing Modes

All major browsers ship some form of a "private browsing" (or, heightened
privacy) mode. While the similarities and differences between these modes,
or the threat models they target, would be valuable, they are better left
to blog authors and vendor documentation, and not standards bodies (or
appendages there of).

### Clarification of the Aims of Private Browsing Modes

Existing research has documented that users have widely varying understandings
and expectations of what private browsing modes do. This is a significant
problem, but not one targeted by this document. This document only recognizes
that there is a frequent desire for privacy beyond whats provided by default
in browsers, when they fully implement existing standards.


### A Request for Good Behavior on the Part of Websites

Existing privacy preserving efforts (e.g. DNT) have shown that asking websites
to respect user privacy is unlikely to be very useful.  No part of this
standard aims to tell websites "the user is requesting additional privacy,
please don't violate their privacy". The aim of this document is to give
standards authors a in-standard way of describing (possibly alternate) browser
functionality that is more privacy protecting, without requiring website
compliance / good behavior.


## Example Use of this Document

This subsection gives a toy example of how this standard might be used
by some future, trivial, standard. The example is meant to be clarifying, but
is intentionally silly to avoid confusion with any existing or proposed
standard.

Assume some proposed standard called the "Real Name API", which would give
web authors the ability to access to "true" name of the current user. The
potential for the usefulness of this feature is plain, as is its potential
for abuse.

Currently the standard would most likely describe the functionality, possibly
with some footnote or *note* saying "vendors may modify this functionality
as desired to protect user privacy." This is sub optimal because it calls into
question the usefulness of "standardization" in general, gives site authors
no guidance in what to expect, and gives vendors no useful suggestions for how
to modify the functionality in the standard to protect privacy.

This standard aims to change this unsatisfactory status quo by allowing
standards authors to write something like the following: "the real name API
end point should return the user's name, unless the user is in private browsing
mode, in which case the api end point should return 'jane doe'."  Such
in-standard definition of privacy preserving behavior, and when to expect it
would meaningfully address each of the above mentioned shortcomings.


## Bless This Mess

Author: Pete Snyder <pes@brave.com>
