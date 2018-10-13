---
layout: post
date: 2018-10-13
title: Firmware update 2.19.01 in next week and new versioning schedule
whereis: Reading post
---

Hello!
I have to announce a bad news for you, mates. The firmware update 2.19.01 will be released next week, not this one. I don't have much time to do it now because of lessons and other mandatory stuff which can't be skipped, also I'm getting some problems with editing localization strings. I'm just sorry.

But I promise you that I'll release new FW in this week ;) At this moment I can share plan of new functionality into MAG Software Portal v 2.19.01r:
1. Adding new shortcuts into embedded portal:
* **Portals loader**:
  * if there are set any portals into *Servers* -> *Portals*, boots menu where you can choose portal;
  * if there is set DHCP portal (*Servers* -> *More*), this portal will be booted even if there are set any "normal" portals;
  * if there isn't set any external portal, the embedded portal will be restarted.
* **Favorites** - direct shortcut to Favorites list (*Home Media* -> *Favorites*). After exiting it the Home Media full list will be shown.
* **Firmware info** - it will boot specially prepared version of this blog (i can't promise this functionality as i'm not sure it).
2. Adding first release of recovery file system with choosing option to remote execute on STB:
  * reboot STB;
  * start embedded portal, application or URL that you put.
3. Embedding patch 1 into image not to flash it again from SSH.
4. Adding new splash screens into portal loader and system settings.

And since this version I'll use new versioning schedule. The three categories of versioning are used:
* **Release** - the main build of firmware, now it is 219. When making major changes it will be upper.
* **Version** - it is full marking of firmware description, example is *2.19.01-release*. The first part (in left from dash) means particular version and the right one means describing tag which you can find below.
* **Base** - it is basing from Infomir, the latest official firmware which components MAG Software Portal uses.

The release is used as equivalent of major tag in Git schedule. The first two parts of the version (like 2.19 in 2.19.00) are always the same as release, they both are major tag. Major marking is intended to catch the largest changes into firmware, the milestones in development and things which completely change usage of firmware (e.g. embedding Linux-based GUI for using STB with keyboard and mouse like computer). The third part (like 01 in 2.19.01) is used as minor tag, which will take the smaller changes, but not as small as the patches and revs. The middle size updates will be registered here as first release. Here we will use "release" word in two meanings, as 3-digit major tag and update to minor tag without any revisions. This stuff will be described below.

The describing tags for images are:
| The ending mark (channel name) |         Short marking         | Example on version with short and long marking |                                                                                                                                 Describe of tag                                                                                                                                 |
|:------------------------------:|:-----------------------------:|:----------------------------------------------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| release                        | r                             | 2.19.01-release / 2.19.01r                     | The release mark means the full version of image, without any SSH updates. Don't mistake it with "release" as 3-digit major number.                                                                                                                                             |
| revision                       | rn (where n is number of rev) | 2.19.01-revision2 / 2.19.01r                   | The revision mark means small update which changes something, it can be full imageupdate or SSH upgrade. First release of particular revision is always first revision, for example after 2.19.01-release won't be 2.19.01-revision1, but 2 because this release means also r1. |
| patch                          | pn (n is number)              | 2.19.01-patch2 / 2.19.01p2                     | The patch is a small change that fast fixes some bug into image. Patches are done quickly since image releasing and mostly are released to do upgrade by SSH method.                                                                                                            |
| beta                           | bn (n is number)              | 2.19.01-beta1 / 2.19.01b1                      | The beta tag will be used for firmware updates that may have bugs because of releasing new, not long tested functionality. These versions are developed with intention to catch these bugs and fix into RC or R channel.                                                        |
| alpha                          | an (n is number)              | 2.19.01-alpha1 / 2.19.01a1                     | The alpha tag will be used when there may be too much problems to use it as beta and I would need your help to fix them.                                                                                                                                                        |
| release_candidate              | rcn (n is number)             | 2.19.01-release_candidate1 / 2.19.01rc1        | The release candidate mark is the version which candidates to be full release. If it is good, I'll just change mark to "release", if not then we fix problems.                                                                                                                  |

The tags beta, alpha and rc will be used when releasing bigger changes and I would need to collaborate with you, okay? :) In normal changes just releasing not to make confusing. But as the project grows, we have to predict the future where I'm going to release newer and newer ideas and how to number it.

Thank you for understanding me :)
