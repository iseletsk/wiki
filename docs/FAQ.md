---
title: 'FAQ'
---
###### last updated: 2023-10-02

# Frequently asked questions

### What is AlmaLinux?

AlmaLinux OS is a community-owned and driven, stable and secure *Linux®* distribution that is compatible with *RHEL*.

### Can I do X, Y, or Z with AlmaLinux?

Sure! AlmaLinux OS, much like RHEL and CentOS Stream, is a general purpose operating system. If it works with RHEL, then it should work exactly the same on AlmaLinux. We are not 1:1 with CentOS Stream, as Stream may at points track well ahead of our releases. 

### What does ABI/binary compatible with RHEL mean?

In July of 2023, [we announced](https://almalinux.org/blog/future-of-almalinux/) that we were shifting our goal from being a downstream rebuild of RHEL to maintaining ABI compatibility with RHEL. For the AlmaLinux team that means that everything from software applications to kernel modules that work on RHEL will work on AlmaLinux, and if they don't we would consider that a bug.

### Is AlmaLinux OS FIPS-140 compliant??

AlmaLinux OS 9.2 is FIPS-140 compliant. Read more in this blog post: [FIPS Validation for AlmaLinux OS](https://almalinux.org/blog/2023-09-19-fips-validation-for-almalinux/)

### Where did the name "AlmaLinux" come from?

We chose the name AlmaLinux in homage to the open source community around the world. Alma means soul in Spanish and other Latin languages. A vital part of Open Source is the passionate, diverse developer community, helping support the work of projects like the Linux kernel and really all open and free software. We believe that community is the soul of Linux, and Linux distribution users are indebted to the community's efforts.

### How is the community protected from future course changes?

The AlmaLinux OS Foundation is a 501(c)(6) that was founded in March of 2021 to own and manage the AlmaLinux OS project. We have been involving the community since the beginning, and the governing board is chosen by members of the foundation. At all times, AlmaLinux OS will be free and open.

### Why use AlmaLinux?

AlmaLinux OS is a community-owned and driven, stable, and secure Linux distribution. AlmaLinux is an opportunity for us to provide a Linux distribution that serves the broader community and which powers the computing needs of a wide range of users. Whether you are running a particle accelerator unlocking the mysteries of the universe, a Top500 HPC cluster, an enterprise running your database workloads, or a developer working on open source projects, AlmaLinux is for you.

AlmaLinux puts out new releases--fast. We typically release with a day or two of upstream RHEL releases. Updates are generally within 24 hours. 

Our governance is under a 501(c)(6) non-profit organization to facilitate our objectives of being open, transparent and participatory. Community members who apply for membership in the foundation (for free) and are able to vote on the governing board of the AlmaLinux project and on critical decisions. There is no "ownership," and no controlling shareholders or interests. The foundation is by the members, for the members. All board meeting minutes are published and shared, including financial positions.

### What architectures and platforms do you support?

AlmaLinux currently supports four architectures - x86_64, aarch64, ppc64le, and s390x - providing full parity with upstream. In addition, we provide a wide range of other images and repositories: traditional ISOs, cloud and container images, live media, WSL - Windows Subsystem for Linux, and Raspberry Pi. 

### Is AlmaLinux secure?

AlmaLinux provides a commitment to security updates and bug fixes for a period of 10 years for each major version. Moreover, AlmaLinux provides [Errata](/documentation/errata.md), [public OVAL streams](/documentation/oval-streams.md), [OpenSCAP](/documentation/openscap-guide.md) and SCAP Workbench packages, including the availability of the official [CIS Benchmark for AlmaLinux](https://www.cisecurity.org/benchmark/almalinuxos_linux). AlmaLinux has [SBOM](/documentation/sbom-guide.md) integrated into our build pipeline, facilitating software supply chain security.


### Where does AlmaLinux get package sources? How AlmaLinux is built?

The process in general looks like this:
* We clone the upstream sources from the CentOS git repositories. These are the same source that Red Hat uses to build their packages.
* De-branding: any trademarks are replaced at this point, and the `.alma` postfix is added to the end of the modified packages' "Release" field to distinguish our packages from upstream ones. You can also check the [Modified packages](/development/Modified-packages.md) page for more details.
  :::tip
  Note: Most RPMs are rebuilt directly from the sources. The rebranding is required when any of the text/visual displays says Red Hat or RHN license manager enforcements.
  :::
* Our build system [Builds](https://build.almalinux.org/) packages with notarization (SBOM). 
* Our testing system runs automated package [Tests](https://github.com/AlmaLinux/alts) & we fix issues.
* Release!

### How do I migrate a single host from CentOS to AlmaLinux?

AlmaLinux developed a [migration tool](https://github.com/AlmaLinux/almalinux-deploy) to make it simple to migrate to AlmaLinux from other Linux distributions including CentOS and CentOS Stream. 

You can read more details and find guide steps on the [Migration](/documentation/migration-guide.md) wiki page. 

### How do I migrate an entire fleet of servers from CentOS to AlmaLinux?

Since AlmaLinux is compatible with RHEL®, your applications and services should be completely interoperable. You can rapidly migrate any number of servers using [AlmaLinux-deploy](https://github.com/AlmaLinux/almalinux-deploy).

### How do I migrate from CentOS 7 to AlmaLinux 8?

The AlmaLinux community has developed the ELevate project as an initiative to support migrations between a major version of RHEL-derivatives. It uses the [Leapp utility](https://leapp.readthedocs.io/) and a few [patches](https://github.com/AlmaLinux/leapp-repository/commits/almalinux) to support migration from CentOS are used to perform the upgrade. 

Check the [ELevate page](/elevate/README.md) for the list of the available migration directions and for the [Quickstart Guide](/elevate/ELevate-quickstart-guide.md).


### How long will AlmaLinux be supported?

The AlmaLinux OS Foundation is committed to supporting AlmaLinux including stable and thoroughly tested updates and security patches until: 
| Release | End-of-Life |
|---|---|
|AlmaLinux 8.x | 2029 |
|AlmaLinux 9.x | 2032 |


### How to Report Bugs

#### I found a bug in RHEL; can I contribute the bug fix to AlmaLinux?

Since AlmaLinux is binary compatible with RHEL, most of the bugs users might encounter would be part of of RHEL. When a bug is encountered, it should be confirmed in CentOS Stream or (if possible) RHEL. If bugs are confirmed to be part of the upstream, AlmaLinux recommends following an "upstream first" approach to fix these bugs by submitting them to [CentOS Stream](https://centos.org/centos-stream/).  This is the contribution path to get the bug fix into RHEL, which will in turn be rebuilt into AlmaLinux.

#### Bug Tracker 

You can file AlmaLinux specific bugs on the [bugs.almalinux.org](https://bugs.almalinux.org) providing all the necessary information about an issue and reproducing steps.

### How can I request a package be added to AlmaLinux?

Since AlmaLinux attempts to be as close to RHEL as possible, it does not add packages to the distribution unless they are added to RHEL. In general, the best place for additional packages is the [Extra Packages for Enterprise Linux (EPEL)](https://docs.fedoraproject.org/en-US/epel/) repository. Any Fedora package that is not in RHEL can be [requested](https://docs.fedoraproject.org/en-US/epel/epel-package-request/).

#### Trademark notices

Red Hat, Red Hat Enterprise Linux are trademarks or registered trademarks of Red Hat, Inc. or its subsidiaries in the United States and other countries.
    
Linux® is the registered trademark of Linus Torvalds in the U.S. and other countries. 
