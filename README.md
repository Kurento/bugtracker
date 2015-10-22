[![][KurentoImage]][Kurento]

Copyright © 2013-2016 [Kurento]. Licensed under [LGPL v2.1 License].

bugtracker
==========

Reporting bugs
--------------

Ok, you’ve run into something unexpected. Some kind of weird error that makes
everything crumble. How should you proceed? This document represents the
guidelines for reporting bugs found in Kurento Media Server, its libraries or
any of the projects related and owned by [Kurento], and hosted in the [official
github repository].

If you're new to reporting bugs, you may want to try getting help from the more
experienced contributor. You can also ask for support on how to report in our
[Kurento Public Mailing list], or in our IRC channel (*#kurento*).

We would like all users to please observe these reporting guidelines, as they
will help us all save time, and acquire the clarity needed to diagnose the
problem quickly.

TL;DR
-----

* Be precise: don’t wander around and go straight to the point, describing as
  precisely as possible what’s happening

* Be clear: explain how to reproduce the problem, step by step, so others can
  reproduce the bug

* Be economic: provide the minimum amount of information needed to understand
  what’s happening

* Be clean: report only one problem per issue so we can track individual
  issues

* Be curious: has it been asked before? is it really a bug? Google is your
  friend!

How to report a bug
-------------------

### Is it really a bug?

The first thing before reporting a bug, is to really make sure it is a bug. Many
of the messages from the list are not bugs: coding issues, configuration
problems... In order to make sure there is indeed a bug, you can follow this
checklist:

* Read the documentation: If the answer is in the documentation, the answer
  will be “Read the documentation”... one mail round wasted
* Webrtc is working in your target browser? use the [WebRTC test page]
* Is it working on a different browser

* If you are using TURN/STUN, make sure it is working using this [STUN/TURN testing] page

* Is there a tutorial that does exactly what you are trying to do? Check out
  the code from github, run it in your machine and see what happens. Those
  tutorials are tested in our CI environment, so you can be quite certain they
  are in good shape

* Check your pipeline. Make a drawing if you need to, but make sure everything
  is connected the way it should

* Check the configuration loaded in your KMS is what it should be. This can be
  seen in the first 100 lines of your KMS logs. If it’s not, change it and see
  if the problem is solved

* Read the logs, they are normally quite interesting. Sometimes building tools
  are just not configured correctly or others have reported the same error.
  Client logs, server logs, build tool logs… For all of those, Google is your
  friend!

* Check that you are running the same version of client libraries and KMS.
  While minor versions are compatible, different major versions aren’t

### Ok, it’s a bug. What now?

First of all, don’t panic! There is still a small work to be done before reporting
the bug.

* If it’s an installation issue, don’t touch anything! Normally when this
  happens, we tend to do random things that could only make things worse

* Choose a bug header that fits the problem

  * Bad: “I can’t see video. Help!”

  * Bettter: “KMS 6.1.1-dev is not showing loopback video in magic-mirror
    tutorial -FF40”

  * Best: “KMS 6.1.1-dev, magic-mirror-tutorial 6.1.1-SNAPSHOT, Mac OS X
    FF40 -- Can’t see loopback video”

* Provide a good description of the problem, with the minimum relevant amount of
  information to reproduce and diagnose the bug

  * What steps will reproduce the problem?

  * What is the expected output?

  * What happens instead?

  * What are the specific versions of

    * KMS

      * kurento-media-server -v

      * dpkg -l | egrep -i "kurento|gstreamer|nice"

      * Service configuration in /etc/default/kurento-media-server

      * Config file in /etc/kurento/kurento.conf.json

    * Client libraries. Stating the flavour (NodeJS, JavaScript, Java or
      homebrewed) it’s a plus, so we don’t have to ask that later

    * Operating system where the client is running

    * Browser (type and version). If Chrome:

      * chrome://webrtc-internals both of sender and receiver as PDF

      * setLocalDescription

      * setRemoteDescription

      * Stats graphs for bweforvideo

      * Stats graphs for ssrc_*

  * How is the system deployed? Are KMS and client in the same network? Are
    you using TURN/STUN?

  * What does your pipeline look like?

* If you can provide a test application, please do so. A pointer to a github
  repo is very welcome, as it will put us both in the same path. This doesn’t
  mean that we are going to debug your code, as there are many thing in there
  that are business-logic of your application

* Provide the logs if they are relevant (i.e. 99% of the time)


For some specific type of bugs, there is some more information that you can provide

* If the bug was recently introduced, finding a regression window can help
  identify the cause of the bug.

* If the bug involves a media server crash, providing core dumps will be of
  great help

* If you are reporting slowness or high resource consumption, please provide a
  profile of the system, along with the specs of the machine KMS and clients
  are running. It’s not the same having 20 clients in one Chrome instance, than
  having them in different instances on different machines.

* If you are reporting a WebRTC bug, please provide WebRTC internals stats

	* Chrome: chrome://webrtc-internals

	* Firefox: about:webrtc

### So, how should a bug report look like?

* Summary: How would you describe the bug in less than 60 characters?

* Version: select the earliest Version with what the problem can be reproduced

* OS: On which operating system (OS) did you find it?

* Description: The details of your problem report, including:

	* Overview

	* Build Id

* Steps to Reproduce

* Actual Results

* Expected Results

Kurento
=======

What is Kurento
---------------

Kurento is an open source software project providing a platform suitable
for creating modular applications with advanced real-time communication
capabilities. For knowing more about Kurento, please visit the Kurento
project website: http://www.kurento.org.

Kurento is part of [FIWARE]. For further information on the relationship of
FIWARE and Kurento check the [Kurento FIWARE Catalog Entry]

Kurento is part of the [NUBOMEDIA] research initiative.

Documentation
-------------

The Kurento project provides detailed [documentation] including tutorials,
installation and development guides. A simplified version of the documentation
can be found on [readthedocs.org]. The [Open API specification] a.k.a. Kurento
Protocol is also available on [apiary.io].

Source
------

Code for other Kurento projects can be found in the [GitHub Kurento Group].

News and Website
----------------

Check the [Kurento blog]
Follow us on Twitter @[kurentoms].

Issue tracker
-------------

Issues and bug reports should be posted to the [GitHub Kurento bugtracker]

Licensing and distribution
--------------------------

Software associated to Kurento is provided as open source under GNU Library or
"Lesser" General Public License, version 2.1 (LGPL-2.1). Please check the
specific terms and conditions linked to this open source license at
http://opensource.org/licenses/LGPL-2.1. Please note that software derived as a
result of modifying the source code of Kurento software in order to fix a bug
or incorporate enhancements is considered a derivative work of the product.
Software that merely uses or aggregates (i.e. links to) an otherwise unmodified
version of existing software is not considered a derivative work.

Contribution policy
-------------------

You can contribute to the Kurento community through bug-reports, bug-fixes, new
code or new documentation. For contributing to the Kurento community, drop a
post to the [Kurento Public Mailing List] providing full information about your
contribution and its value. In your contributions, you must comply with the
following guidelines

* You must specify the specific contents of your contribution either through a
  detailed bug description, through a pull-request or through a patch.
* You must specify the licensing restrictions of the code you contribute.
* For newly created code to be incorporated in the Kurento code-base, you must
  accept Kurento to own the code copyright, so that its open source nature is
  guaranteed.
* You must justify appropriately the need and value of your contribution. The
  Kurento project has no obligations in relation to accepting contributions
  from third parties.
* The Kurento project leaders have the right of asking for further
  explanations, tests or validations of any code contributed to the community
  before it being incorporated into the Kurento code-base. You must be ready to
  addressing all these kind of concerns before having your code approved.

Support
-------

The Kurento project provides community support through the  [Kurento Public
Mailing List] and through [StackOverflow] using the tags *kurento* and
*fiware-kurento*.

Before asking for support, please read first the [Kurento Netiquette Guidelines]

[WebRTC test page]: https://test.webrtc.org/
[STUN/TURN testing]: https://webrtc.github.io/samples/src/content/peerconnection/trickle-ice/
[documentation]: http://www.kurento.org/documentation
[FIWARE]: http://www.fiware.org
[GitHub Kurento bugtracker]: https://github.com/Kurento/bugtracker/issues
[GitHub Kurento Group]: https://github.com/kurento
[kurentoms]: http://twitter.com/kurentoms
[Kurento]: http://kurento.org
[Kurento Blog]: http://www.kurento.org/blog
[Kurento FIWARE Catalog Entry]: http://catalogue.fiware.org/enablers/stream-oriented-kurento
[Kurento Netiquette Guidelines]: http://www.kurento.org/blog/kurento-netiquette-guidelines
[Kurento Public Mailing list]: https://groups.google.com/forum/#!forum/kurento
[KurentoImage]: https://secure.gravatar.com/avatar/21a2a12c56b2a91c8918d5779f1778bf?s=120
[LGPL v2.1 License]: http://www.gnu.org/licenses/lgpl-2.1.html
[NUBOMEDIA]: http://www.nubomedia.eu
[StackOverflow]: http://stackoverflow.com/search?q=kurento
[Read-the-docs]: http://read-the-docs.readthedocs.org/
[readthedocs.org]: http://kurento.readthedocs.org/
[Open API specification]: http://kurento.github.io/doc-kurento/
[apiary.io]: http://docs.streamoriented.apiary.io/
[official github repository]: https://github.com/Kurento/
