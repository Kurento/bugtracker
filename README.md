[![License badge](https://img.shields.io/badge/license-Apache2-orange.svg)](http://www.apache.org/licenses/LICENSE-2.0)
[![Documentation badge](https://readthedocs.org/projects/fiware-orion/badge/?version=latest)](https://doc-kurento.readthedocs.io)
[![Docker badge](https://img.shields.io/docker/pulls/fiware/orion.svg)](https://hub.docker.com/r/fiware/stream-oriented-kurento/)
[![Support badge]( https://img.shields.io/badge/support-sof-yellowgreen.svg)](https://stackoverflow.com/questions/tagged/kurento)

[![][KurentoImage]][Kurento]

Copyright 2018 [Kurento]. Licensed under [Apache 2.0 License].

[Kurento]: https://kurento.org
[KurentoImage]: https://secure.gravatar.com/avatar/21a2a12c56b2a91c8918d5779f1778bf?s=120
[Apache 2.0 License]: http://www.apache.org/licenses/LICENSE-2.0



Kurento Bug Tracker
===================

Reporting Issues
----------------

When reporting a bug, please include as much information as possible, this will help us solve the problem. Also, try to follow these guidelines as closely as possible, because they make it easier for people to work on the issue, and that means more chances that the issue gets fixed:

- **Be proactive**. If you are working with an old version of Kurento, please check with newer versions, specially with the [latest pre-release version](https://doc-kurento.readthedocs.io/en/stable/user/installation_dev.html). We can't emphasize this enough: *it's the first thing that we are going to ask*.

- **Be curious**. Has it been asked before? Is it really a bug? Everybody hates duplicated reports. The Search tool is your friend!

- **Be precise**. Don't wander around your situation and go straight to the point, unless the context around it is technically required to understand what is going on. Describe as precisely as possible what you are doing and what is happening but you think that shouldn't happen.

- **Be specific**. Explain how to reproduce the problem, being very systematic about it: step by step, so others can reproduce the bug. Also, report *only one problem per opened issue*.



How to report a bug
-------------------

### Is it really a bug?

The first thing before reporting a bug, is to really make sure it is a bug. Many of the messages from the list are not bugs: coding issues, configuration problems... In order to make sure there is indeed a bug, you can follow this checklist:

* Read the documentation: If the answer is in the documentation, the answer will be "Read the documentation!"... one mail round wasted.

* Check the documentation to test with the [latest pre-release version](https://doc-kurento.readthedocs.io/en/stable/user/installation_dev.html). Note: You might have to run `sudo apt-get install dist-upgrade` in some cases, if you see the message `The following packages have been kept back ...`

* Is WebRTC working in your target browser? use the [WebRTC test page] to check it out.

* Is it working on a different browser?

* If you are using TURN/STUN, make sure it is working using this [STUN/TURN testing] page.

* Is there a tutorial that does exactly what you are trying to do? Check out the code from GitHub, run it in your machine and see what happens. Those tutorials are tested in our CI environment, so you can be quite certain they are in good shape.

* Check your pipeline. Make a drawing if you need to, but make sure everything is connected the way it should.

* Check the configuration loaded in your KMS is what it should be. This can be seen in the first 100 lines of your KMS logs. If it's not, change it and see if the problem is solved.

* Read the logs, they are normally quite interesting. Sometimes building tools are just not configured correctly or others have reported the same error. Client logs, server logs, build tool logs... For all of those, use Google!

* Check that you are running the same version of client libraries and KMS. While minor versions are compatible, different major versions aren't.

[WebRTC test page]: https://test.webrtc.org/
[STUN/TURN testing]: https://webrtc.github.io/samples/src/content/peerconnection/trickle-ice/



### Ok, it's a bug. What now?

First of all, don't panic! There is still a small work to be done before reporting the bug:

* If it's an installation issue, don't touch anything! Normally when this happens, we tend to do random things that could only make things worse.

* Choose a bug header that fits the problem:

  * Bad: "I can't see video. Help!"

  * Bettter: "KMS 6.7.1-dev not showing loopback video, FF40"

  * Best: "KMS 6.7.1-dev, magic-mirror 6.7.1-SNAPSHOT, Mac OSX, FF40: Can't see loopback video"

* Provide a good description of the problem, with the minimum relevant amount of information to reproduce and diagnose the bug

  * What steps will reproduce the problem?

  * What is the expected output?

  * What happens instead?

  * What are the specific versions of...

    * KMS

      * `kurento-media-server -v`

      * `printf '```\n%s\n```' "$(dpkg -l | egrep -i "kurento|gstreamer|nice")"` 🠘 **Including the backticks!**

      * Service configuration in `/etc/default/kurento-media-server`

      * Config file in `/etc/kurento/kurento.conf.json`

    * Client libraries. Stating the flavour (NodeJS, JavaScript, Java or homebrewed) is a plus, so we don't have to ask that later. Make sure they match the Major and Minor versions of your KMS modules.

    * Operating System where the client is running.

    * Browser (type and version). If Chrome:

      * `chrome://webrtc-internals` of both sender and receiver, as PDF.

      * `setLocalDescription` line.

      * `setRemoteDescription` line.

      * Stats graphs for `bweforvideo`.

      * Stats graphs for `ssrc_*`.

  * How is the system deployed? Are KMS and client in the same network? Are you using TURN/STUN?

  * What does your pipeline look like?

  * Have you checked the development version?

* If you can provide a test application, please do so. A pointer to a GitHub repo is very welcome, as it will put us both in the same path. This doesn't mean that we are going to debug your code, as there are many thing in there that are business-logic specific to your application.

* Provide the logs if they are relevant (i.e. 99% of the time).

For some specific type of bugs, there is some more information that you can provide:

* If the bug was recently introduced, finding a regression window can help identify the cause of the bug.

* If the bug involves a media server crash, providing core dumps will be of great help

* If you are reporting slowness or high resource consumption, please provide a profile of the system, along with the specs of the machine KMS and clients are running. It's not the same having 20 clients in one Chrome instance, than having them in different instances on different machines.

* If you are reporting a WebRTC bug, please provide WebRTC internal stats.

  * Chrome: `chrome://webrtc-internals`.

  * Firefox: `about:webrtc`.



### So, how should a bug report look like?

* Summary: How would you describe the bug in less than 60 characters?

* Version: Select the earliest Version with what the problem can be reproduced.

* OS: On which operating system (OS) did you find it?

* Description: The details of your problem report, including:

  * Overview.

  * Build Id.

* Steps to reproduce.

* Actual results.

* Expected results.



About Kurento
=============

Kurento is an open source software project providing a platform suitable for creating modular applications with advanced real-time communication capabilities. For knowing more about Kurento, please visit the Kurento project website: https://www.kurento.org.

Kurento is part of [FIWARE]. For further information on the relationship of FIWARE and Kurento check the [Kurento FIWARE Catalog Entry]. Kurento is also part of the [NUBOMEDIA] research initiative.

[FIWARE]: http://www.fiware.org
[Kurento FIWARE Catalog Entry]: http://catalogue.fiware.org/enablers/stream-oriented-kurento
[NUBOMEDIA]: http://www.nubomedia.eu



Documentation
-------------

The Kurento project provides detailed [documentation] including tutorials, installation and development guides. The [Open API specification], also known as *Kurento Protocol*, is available on [apiary.io].

[documentation]: https://www.kurento.org/documentation
[Open API specification]: http://kurento.github.io/doc-kurento/
[apiary.io]: http://docs.streamoriented.apiary.io/



Useful Links
------------

Usage:

* [Installation Guide](http://doc-kurento.readthedocs.io/en/stable/user/installation.html)
* [Compilation Guide](http://doc-kurento.readthedocs.io/en/stable/dev/dev_guide.html#developing-kms)
* [Contribution Guide](http://doc-kurento.readthedocs.io/en/stable/project/contribute.html)

Issues:

* [Bug Tracker](https://github.com/Kurento/bugtracker/issues)
* [Support](http://doc-kurento.readthedocs.io/en/stable/user/support.html)

News:

* [Kurento Blog](https://www.kurento.org/blog)
* [Google Groups](https://groups.google.com/forum/#!forum/kurento)



Source
------

All source code belonging to the Kurento project can be found in the [Kurento GitHub organization page].

[Kurento GitHub organization page]: https://github.com/Kurento



Licensing and distribution
--------------------------

Copyright 2018 Kurento

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
