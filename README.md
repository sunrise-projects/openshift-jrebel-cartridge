openshift-jrebel-cartridge
=================================

####This only works on non-scaled applications at the moment
####This cartridge is tested as working with the following cartridges on OpenShift Online 
- jbossews-1.0    (Tomcat 6 (JBoss EWS 1.0))
- jbossews-2.0    (Tomcat 7 (JBoss EWS 2.0))
- jbossas-7       (JBoss Application Server 7)
- jbosseap-6      (JBoss Enterprise Application Platform 6)
- jboss-wildfly-8 (WildFly Application Server 8.2.0.Final)


The following examples will use the jboss-wildfly-8 (WildFly 8) cartridge, but you can use any of the supported cartridges with a slight modification to the directions below.  

Create your application using the WildFly 8 (jboss-wildfly-8) cartridge

	rhc app create wildfly jboss-wildfly-8 

Then install this cartridge

    rhc cartridge-add https://cartreflect-claytondev.rhcloud.com/reflect?github=openshift-cartridges/openshift-jrebel-cartridge -a <appname>

You can also install the openshift-jrebel-cartridge when creating your application with the following command:

	rhc app create wildfly jboss-wildfly-8 https://cartreflect-claytondev.rhcloud.com/reflect?github=openshift-cartridges/openshift-jrebel-cartridge
  
Before you can interact with your application using JRebel, you need to complete the following steps:  
	
- Clone your application to your workstation (using either your IDE or git command line) and add the rebel.xml and rebel-remote.xml files and configure them to point to your application url (http://app-domain.rhcloud.com).  
- You then need to do a "git add", "git commit", and "git push" to get these files onto your gear so that you can use JRebel.  This will also restart the application server and make sure that jrebel is now running.
- Please note:  Application server startup will take a little bit longer than normal, please be patient.
- Now you can use your favorite IDE with the JRebel plugin installed to update your application without having to do a git push  


If you are using IntelliJ, remember that this is a maven based project, so you will have to finagle the Web module settings a little and move some files around. 

- 
    
Please log any issues to the git repository issue tracker

####Additional Resources  
Here are a some resources to help you get going with JRebel Remoting in your favorite IDE: 
http://zeroturnaround.com/software/jrebel/learn/remoting  
http://zeroturnaround.com/software/jrebel/learn/remoting/eclipse/  
http://zeroturnaround.com/software/jrebel/learn/intellij-idea-jrebel-tutorial-formerly-javarebel/ 

