---
name: Bug report
about: Create a report to help us improve
title: ''
labels: ''
assignees: ''

---

Please complete the following information, where relevant. Note that reports that are not bugs of Kurento will generally not be accepted.

**Describe the bug**

A clear and concise description of what the bug is.

**To Reproduce**

Steps to reproduce the behavior:

1. Create this pipeline: '...'
2. Use these settings: '...'
3. '...'
4. See error

**Expected behavior**

A clear and concise description of what you expected to happen.

**Kurento Media Server**

- Kurento version: [e.g. 6.12.0, or nightly]
- Server OS: [e.g. Ubuntu 16.04 (Xenial), 18.04 (Bionic)]
- Installation method: [e.g. [apt-get](https://doc-kurento.readthedocs.io/en/latest/user/installation.html#installation-local), [Docker](https://doc-kurento.readthedocs.io/en/latest/user/installation.html#installation-docker), [AWS](https://doc-kurento.readthedocs.io/en/latest/user/installation.html#installation-aws), [build from sources](https://doc-kurento.readthedocs.io/en/latest/dev/dev_guide.html#dev-sources)]


**Application Server**

- Language: [e.g. Java, Node.js, browser JavaScript]
- Client version: [e.g. 6.12.0, or nightly]

**End-user clients**

- Device(s): [e.g. PC, Mac, Android, iPhone]
- OS(es): [e.g. Ubuntu 18.04, Windows 10, iOS8.1]
- Browser(s) [e.g. Firefox, Chrome, Safari]
- Version(s): [e.g. 79.0.3945.79]

**Version details** (please paste output of running these commands **in the machine where KMS is running**)

```
kurento-media-server -v

lsb_release -a

dpkg -l | grep -Pi 'kurento|kms-|gst.*1.5|nice'
```

**Additional context**

Add any other context about the problem here. E.g. where KMS is located, where the clients are, whether you are using STUN/TURN, etc.
