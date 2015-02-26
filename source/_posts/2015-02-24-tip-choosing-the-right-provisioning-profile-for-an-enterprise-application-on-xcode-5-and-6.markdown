---
layout: post
title: "Tip: choosing the right provisioning profile for an enterprise application on Xcode 5 and 6"
date: 2015-02-24 16:24:29 -0300
comments: true
categories: 
---
Since Xcode 5, I’ve been having some issues to use provisioning profiles with the same App Name ID and different bundle identifiers, this happens because Xcode just let you select the first profile that was added. That happens because Xcode identifies the provisioning based on its App Name ID, which can be identical in enterprise development, and I think the provisioning profile should be distinguished based on the bundle identifier.  To handle this situation, you will have to do as follows:  Open the provisioning profile in a text editor and copy the <string> value of the <UUID> node inside the <plist> root dictionary node. Go to Xcode > Code Signing > Provisioning Profile section and choose the Other... item, then paste the UUID here. The correct certificate can be chosen now.