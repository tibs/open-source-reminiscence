========================================================
Notes for a reminiscence over the history of open source
========================================================

We were having a discussion about Aiven and open source at work, and I did a
short summary of, well, the history as I know it. And colleagues said they'd
listen to me doing a talk on the subject. So here we are.

-------

Aiven: our business is based on open source, and we contribute back.

Briefly explain the OSPO and Josep Prat's concept of  ``#extrospective-ospo``.
Give a link to at least one of his talks on the matter.

Setting the scene - "back in the day"
=====================================

--------

My career stared back when communication was slow (think: no internet as such,
no email for most people, definitely no web pages). To get free software,
you'd copy files off Usenet (think a heavyweight ancestor of Mastodon, with a
lot fewer people, but a curated list of groups that one could chat on),
reassemble them and then build the result, or write a letter to someone and
get a magnetic tape back in the post.

I come from a time when we expected to pay for the operating system, probably
for the compiler (maybe it was bundled with the OS) and maybe an editor, and
indeed quite possibly for other things, too.

It seemed very odd, and rather unfair, to me when companies started to
*assume* that major components that they depended on, in particular the
operating system (Linux) were going to be free. They seemed to develop a
strange sort of entitlement, a resentment of the idea that they might even
need to pay for support. This seems off to me - a wish to have (considerable
commercial) value for no (apparent) cost.

NB: Aiven, OSPO, ``#extrospectiveOSPO``

---------

Where are we going to define "open source" as starting, for the purposes of
this talk?

Given that back in the day there were many incompatible systems, including

* Various mainframes (IBM, ICL, others)
* Various smaller systems (PDP with various operating systems, DEC VMS, Unixes
  of various stripes, eventually Linux, other variants of things)
* Early PC systems, IBM, Microsoft, Apple, BBC Micro and Archimedes, and a
  wide variety of others

(not all at the same time!) it seems sensible to choose:

* source code that could be built on a wide variety of systems with only
  moderate alteration (ref XMakefile, and so on)
* that one did not have to buy, but one might need to pay for the bother of
  the generation of magnetic tapes and their postage

It's not quite that simple, but that's our broad start.

Why not so simple? Well, for some platforms (for instance, some Unices, VMS) there
was a big enough population to make it worth having sytsem-specific free
software. But it would still often be distributed as open source.

--------

Maybe mention the distinctions of

* Free software
* Shareware
* (normal) paid ware

and which areas they were more dominant in (shareware in particular on early
home computers).

---------

Trying to use *copyright* to build open source *licensing*.

Licensing isn't what copyright does.

In retrospect, probably a mistake, but also, there probably wasn't another way
to do it.

Note that we've had very few cases that test the system to see if it's
actually legally binding.

Note that legal systems aren't the same everywhere. Check that it's still true
that Public Domain doesn't work (as wished) in any of the four legal systems
in the UK.

Apache 2 and the "put a notice of the change in the code" clause, which no-one
ever does - check I've got this right. Because if I have, just about no-one
actually follows the license <sad face>. Of course, it predates widespread use
of version control systems.

Patent cover - Apache 2 and FSF licenses good for this, MIT/BSD not so much.

Why UPPER CASE?

Copyright differences: who owns the original copyright? In Germany, for
instance (maybe other EU countries) you can't give up your copyright, it's
always yours. In USA (???) a company can own what you write (and maybe even
what you write outside work! - CHECK both of these statements).

Also in USA, software written for government will be (is this always true?)
public domain, as it was created using public funding, so belongs to the public.

---------

The philosophical difference between the two main branches of open source

The following distinction isn't quite fair - make it better

* MIT/BSD/etc: it's free, it's yours, do as you will
* FSF: it's free, it's yours, but if you change it you must contribute those
  changes back - and limitations to try to enforce that

---------

Licenses companies won't touch

* The problems of believing that GPL licences are "viral" - is this mostly
  over now?
* "Do no evil" in a license - lawyers sigh, as undefinable and thus
  unenforcible
* Humourous or sweary licences - either no use as a license, or (if sweary)
  likely to be avoided because rude

If there's no licnese, then can't use the software, as no way to know what one
is liable for.

Reference problems of Public Domain here again.

--------

Please, when creating a new project, do choose a license, and put some thought
into what you prefer it to be. **Ref** one or two of the "easy introduction to
choosing licenses" web sites.

---------

Remember to respect the choice of a package or library author. If they choose
a license that means you can't use their project (for instance, this may mean
GPL), then that's because they chose it. If you can't use their software, in
the way that you want to, that may be because that was the point of the
licence choice. Respect that, don't try to circumvent it.

On the other hand, it certainly used to be the case that asking an author
nicely would sometimes result in dual-licensing, or some ability to use the
software for a reasonable consideration.

Regardless, be a good citizen, respect the author's wishes.

---------

Founding of the OSI as an attempt to give better terminology and some clarity:

* the invention of the term "Open source" - the FSF didn't like it, because
  "open" didn't mean anything
* but then neither did "free" - at least in english, where we only have one
  word for two concepts, unlike (for instance) French, where one can say
  ``libre`` and be clear.
* What *does* "free as in beer" mean? I've never understood

"free as in puppy" (I think this was Josep?) - that is, a puppy is freely
given, but then needs lots of care and can be quite costly.

The value of SPDF and other such

----------

Current movements to switch to "nearly open" licenses, to try to protect
businesses. For instance, Elasticsearch, MongoDB, Lightbend.

* sort of understandable
* definitely allowed by the original licenses of the projects
* as are the forks of the open original source code

So arguably, this is open source working the way it is meant to.

Given the arguments over the meaning of "open" when OSI was founded, one can
also see there's precedent for them wanting to claim that their new licenses
are also "open" - since OSI gave itself authority, challenging that authority
isn't unexpected. *This* part of the history I don't like, though - I think
the distinction is a valuable one we should retain, even if none of the words
we've ended up with are ideal.

---------

How dependency trees have grown, making it harder to check for legal license
combinations.

The difficulty of hand-checking, the impossibility of automatic checking.

Being "locked in a cupboard" for a fortnight to check the licensing of a linux
distribution.

My "certificate" as FLOSS evaluator <smile>

Licenses can change over software versions! So can't assume that this is a
one-off check for any partiuclar package.

The problem of authors getting the overall licensing of a package wrong when
they're trying to summarise over the licenses of included packages.

Sometimes people delete licenses from code - let's assume because they don't
understand the requirements.

???Floor had a reference to a project trying to assemble public SBOM
registration, which would solve a lot of problems.

------------

Muddle: a system for building systems

* declaring the license of each package in the build description
* checking that the tree of dependencies was legitimate
* yes, we found a problem at least once, so it was worth it

**But** people don't like having to decide on and write down the license of a
package in their build description. So of limited applicability.

(I think Yokto is the nearest widely-used thing to muddle, and I don't think
it has this capability - need to check both of those statements)
