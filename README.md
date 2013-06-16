Drools
======

In order to familiarise myself with the Drools language I have spent several weeks working through various examples to understand
* syntax
* functionality
* domain specific languages

This repository contains my full set of working examples.

Using Eclipse
-------------
Eclipse has a good Drools Plugin which can be installed from: 
http://download.jboss.org/drools/release/5.5.0.Final/org.drools.updatesite

In eclipse -> preferences be sure to navigate to 
Drools -> Installed Drools Runtime and navigate to a folder. 
Once you have a project running the plugin will copy the necessary drools jars here.

Using Maven
-----------
I decided to lay out my working environment as a maven project rather than a typical Drools project. This was purely because in the 'real world' we use Drools as part of a larger maven application, so for me it felt more realistic to use maven from the start. use a maven project rather than a typical Drools project. It made loading the files a little harder, as the classpaths had to be taken into account, whereas with a Drools Project the compipler knows exactly where to find the drl files.

    <dependency>
  		<groupId>org.drools</groupId>
			<artifactId>drools-core</artifactId>
			<version>5.5.0.Final</version>
		</dependency>
		<dependency>
			<groupId>org.drools</groupId>
			<artifactId>drools-compiler</artifactId>
			<version>5.5.0.Final</version>
		</dependency>
		<dependency>
			<groupId>org.drools</groupId>
			<artifactId>drools-decisiontables</artifactId>
			<version>5.5.0.Final</version>
		</dependency>
		<dependency>
			<groupId>org.slf4j</groupId>
			<artifactId>slf4j-log4j12</artifactId>
			<version>1.7.2</version>
			<scope>runtime</scope>

If you use a Drools project you dont need a pom as maven is not used. The drools runtime pulls in all the drools dependencies you require. The downside of this is that if you wish to use hamcrest/junit etc you need to manually add those jars to the classpath - old school ;-)

Summary
-------
Drools seems a straighforward domain to learn. It was quick to get running and make progress. 

Its easy to read the logic, the drl files act as documentation. Rather than compound rules, write seperate ones with appropriate names.

Agenda and activation groups provide a nice way to order rules without relying on salience which could be difficult to maintain over time.

Some of the features, particularly those available within Stateful Sessions are very powerful (sauch as modifying the working memory during runtime, obtaining facts from the session and manipulating them.
I found it difficult to think of real life usecases for the templated drools files, although I'm sure there are some good ones out there.

In my opinion if you have a problem or area in your code which a rules engine could solve then drools should definatly be considered.
