---
title: Contribution Example
permalink: Develop/Collaborate/Contribution_Example/
parent: Collaborate
layout: default
nav_order: 100
---

This document describes contribution example how to contribute the code:

For this example, we will consider a hypothetical bug which affects the
Sailfish Browser. The community member "Alice" discovers that for some
content-aggregator sites, the wrong User Agent string seems to be used
when fetching content. She decides to investigate and contribute a fix.
These are the steps she takes:

1\) She files an issue on
<https://github.com/sailfishos/sailfish-browser/issues> with example
issue template from above.

2\) She comments on the issue to say that she will investigate the
issue.

3\) She searches for the upstream code repository, and finds
<https://github.com/sailfishos/sailfish-browser> and notes that it
depends on embedlite-components-qt5. After browsing that source code,
she realises that the user agent override behaviour is defined in code
from the embedlite-components-qt5 package.

4\) She searches for that package on her Sailfish OS device via command
`rpm -qi embedlite-components-qt5 | grep URL` and finds its upstream
repository URL <https://github.com/sailfishos/embedlite-components>

5\) She creates a personal fork of that repository using the web
interface at <https://github.com/sailfishos/embedlite-components>

6\) She clones that personal fork to her local host machine via `git
clone https://github.com/alice/embedlite-components.git
alice-embedlite-components`

7\) She builds the package
```nosh
# cd into her local clone
~ $ cd alice-embedlite-components

# attempt to build the package for her Sailfish OS-4.2.0.21-armv7hl target
~/alice-embedlite-components $ sfdk config target=Sailfish OS-4.2.0.21-armv7hl
~/alice-embedlite-components $ sfdk build
No provider of 'xulrunner-qt5-devel >= 60.9.1' found.
Building target platforms: armv7hl-meego-linux
Building for target armv7hl-meego-linux
error: Failed build dependencies:
    xulrunner-qt5-devel >= 60.9.1 is needed by embedlite-components-qt5-1.0.0-1.armv7hl
    pkgconfig(nspr) is needed by embedlite-components-qt5-1.0.0-1.armv7hl

# she knows that she needs to update her SDK target.
# to find out which ssu repository provides those packages, she now ssh's into her device,
# and runs `zypper info` (can also use `pkcon get-details` or search on OBS).
~/alice-embedlite-components $ ssh defaultuser@device
[defaultuser@XperiaXA2-DualSIM ~]$ devel-su -p pkcon install zypper
## snipped ##
[defaultuser@XperiaXA2-DualSIM ~]$ zypper info xulrunner-qt5-devel
Loading repository data...
Reading installed packages...
Information for package xulrunner-qt5-devel:
--------------------------------------------
Repository: jolla
Name: xulrunner-qt5-devel
Version: 60.9.1+git61-1.11.6.jolla
Arch: armv7hl
Vendor: meego
Installed: No
Status: not installed
Installed Size: 6.1 MiB
Summary: Headers for xulrunner
Description: 
  Development files for xulrunner.

# she now knows that it comes from the "jolla" repository.
# she goes back to her development terminal, and
# enters the build target to update the ssu repositories.
~/alice-embedlite-components $ sfdk tools exec Sailfish OS-4.2.0.21-armv7hl

# might be required to register her SDK depending on her SDK setup.
[Sailfish OS-4.2.0.21-armv7hl] ~ # ssu r

# list the available repos
[Sailfish OS-4.2.0.21-armv7hl] ~ # ssu lr
## snipped ##
Disabled repositories (global, might be overridden by user config):
 - jolla ... https://releases.jolla.com/releases/4.2.0.21/jolla/armv7hl/
## snipped ##

# she enables the repository.
[Sailfish OS-4.2.0.21-armv7hl] ~ # ssu er jolla

# she refreshes the available package list
[Sailfish OS-4.2.0.21-armv7hl] ~ # zypper ref -f

# now she is ready to go back sfdk to build the package again
[Sailfish OS-4.2.0.21-armv7hl] ~ # exit
~/alice-embedlite-components $ sfdk build
# success! The missing package was found now
```

8\) Now that she has successfully built the package locally, she tests
deploying the package.
```nosh
# she registered her device using the "my device" name within the Sailfish IDE before
~/alice-embedlite-components $ sfdk config device="my device"
~/alice-embedlite-components $ sfdk deploy --manual
~/alice-embedlite-components $ sfdk device exec
[defaultuser@XperiaXA2-DualSIM ~]$ devel-su zypper -p RPMS dup --from ~plus-repo-1 --details
# or the forceful way
[defaultuser@XperiaXA2-DualSIM ~]$ devel-su rpm -Uvh --force RPMS/embedlite-components-qt5-1.0.0-1.armv7hl.rpm
```

9\) After rebooting the device and opening browser, she sees that it
works. She is now ready to begin development. She makes changes, adds
debug statements, deploys the package to the device, and retrieves the
logging information from the journal with `devel-su journalctl -af |
grep browser`.

10\) After she has resolved the issue, and commits her fix locally. She
then pushes the commit to her personal fork, and creates a pull request
to the upstream repository. This will look something like
<https://github.com/sailfishos/embedlite-components/pull/14>

11\) She now updates the issue report with her findings, and a link to
her pull request.

12\) After receiving some review comments, she updates her commit with
`git commit --amend`, force pushes it to her personal fork via `git push
origin master:master --force` and comments in the merge request that it
has been updated.

13\) The maintainer merges the patch, tags it, and comments on the
original bug report the tagged version which should be in a future
release.
