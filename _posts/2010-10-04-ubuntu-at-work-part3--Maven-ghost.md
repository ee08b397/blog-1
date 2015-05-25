---           
layout: post
title: "Ubuntu at work part3- Maven ghost"
date: 2010-10-04 12:13:45 UTC
updated: 2010-10-04 12:13:45 UTC
comments: false
categories: ubuntu
---

This Maven ghost is not unique to Ubuntu . He can be seen in windows version of eclipse too.So what does he do? He just makes all maven dependencies disappear from Eclipse !!!. Deadly dangerous right?

After getting back all my plug ins , i was a happy worker. But Eclipse was not happy.So it launched maven ghost against me.One evening i see all the maven dependencies are disappeared from package explorer. The project was building fine which means all dependencies were there.But they just disappeared from the eclipse view.

I restarted Eclipse .No effect. I cleaned it so many times.No effect.I rebooted my system itself . No effect.So started to Googling about it. After one hour of search i found out that two small setting will change everything. I am sharing with you this , may be it will be useful if you come across this ghost.

For every project ,Eclipse maintains a .classpath file. Just add the following line to the .classpath file of the project in which maven dependencies are missing.

classpathentry kind="con" path="org.maven.ide.eclipse.MAVEN2_CLASSPATH_CONTAINER"

This enables the eclipse to show maven dependency folder.

That's not enough. By this setting it only some jars . If you want to see all dependencies
got to .settings folder. Then in org.maven.ide.eclipse.prefs change

includeModules=false

to
includeModules=true

Just restart the Eclipse.

Maven Dependencies are back and ghost is not here. May be he went to your place , just be aware :)
Update : This ghost is unique to Maven plug in 0.10 version. It does not appear in 0.98 version