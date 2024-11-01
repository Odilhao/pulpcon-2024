---
download: true
# try also 'default' to start simple
title: 'State of RPM'
theme: seriph
themeConfig:
  primary: '#5d8392'
#theme: apple-basic
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://unsplash.com/collections/94734566/slidev
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
author: Odilon Sousa
selectable: true
colorSchema: 'dark'
favicon: 'https://pulpproject.org/pulpcore/docs/assets/pulp_logo_big.png'

---

# Pulpcon - 2024

## Packaging Pulp RPMs

---
layout: intro
---

# whoami

- Odilon Sousa
  - Senior Software Engineer at Red Hat
  - Primarily working with RPM packagingr
    - Foreman/Katello/Pulp

---

# This year recap

<div grid="~ cols-2 gap-2" m="-t-2">
<div v-click>

- Automations
  - Dependabot 🤖
  - Auto Packaging after Dependabot Merge
  - Dependecy Resolution in Dependabot PRs
  - Auto Bump of all required libs two times in the week

</div>

<div v-click>

- Packaged Versions
  - Nightly - Based on last supported for Katello
  - 3.49
  - 3.61 - For Weeks
  - 3.63

</div>
</div>

---

# Timeline

<div v-click>

* 2 Active numbered releases and nightly being updated by Dependabot
* At some point next year we plan to add dependabot based workflow to branched releases
* Starting with 3.63 we only build for EL9, until EL10 release 😏

</div>

<div v-click>

```mermaid

%%{init: { 'logLevel': 'debug', 'theme': 'dark', 'darkMode': 'true'} }%%
gantt
    title Version Release Timeline
    dateFormat YYYY-MM-DD
    axisFormat %b %Y

    section Nightly
    Nightly :active, n1, 2023-10-01, 900d

    section Branches
    3.39 : active, a1, 2023-11-08, 355d
    3.49 : active, a1, 2024-03-26, 365d
    3.61 : active, a1, 2024-09-20, 11d
    3.63 : active, a1, 2024-10-01, 365d


```

</div>

---

# Building Information

<div grid="~ cols-2 gap-2" m="-t-2">
<div>

- Which Build Systems are support?
  - Setuptools
  - Poetry
  - Maturin
  - Flit
  - Hatch

</div>

<div>

* Only Python 3.11 is supported now
  * Until EL10 - Rebuild for 3.12

* We have bi-weekly builds of libs
  * Catching breakeages ealier in the process
  * Changing from setup.py/cfg to PEP-517? 
    * We catch that weekly now



</div>
</div>

---

# How fast can we go?

<div grid="~ cols-2 gap-2" m="-t-2">
<div>


* New Pulp bits being released in hours
  * Pulpcore 3.63.1 Release
    * Upstream Pulp - [Released](https://github.com/pulp/pulpcore/commit/570950de0aa6c262e99b33792913a706a671fc5c) Wed Oct 30 15:46:51 2024
    * Dependabot - [Released](https://github.com/theforeman/pulpcore-packaging/commit/231f789dfd3490b84bb52a91f70aadeabe058889) Wed Oct 30 17:18:12 2024
    * Packaging - [Released](https://github.com/theforeman/pulpcore-packaging/pull/1419) Wed Oct 30 17:24:06 2024
    * Released on Nightly - [Released](https://copr.fedorainfracloud.org/coprs/g/theforeman/pulpcore-nightly-staging/build/8191052/) Wed Oct 30 17:44 2024

</div>

<div>

![Relampago Marquinhos](https://media1.tenor.com/m/l6CJxGWdYAoAAAAd/speed-i-am-speed.gif)

</div>

</div>
---

---
layout: center
---

# Questions?