## Jenkins Plugin Development

#### Jenkins Infrastructure

- what is RunAction2 ? 
- @Extension what does it mean ? 
- what is RootAction ?
  - What is an Action ? It's basically like Android Actions, add a new page on the index page. And RootAction is something appears at root home page.
- what is pre-defined extension points 
  - the ideas on JENKINS issue wait for developers to make a plugin to do that
- Where should I use @Extension, what class should be registered and why the first action wasn't registered?
- Jenkins use Jelly to organize its UI
- Where is hello world builder ? 
- where did the url go ? 
- Descriptor ? What is Describable object ?
  - A descriptor contains meta information of a component in Jenkins, and has a function of factory. It contains many aspects of Jenkins, from describing the process of a build, the UI layout, the UI components on home page, or a Jenkins-defined intermediate struct.
- what is fill dropdown items
  - a UI design pattern, only show the choices when you click on that an will rearrange the layout.
- @DataBoundConstructor ? What is this again ? 
- what is a Builder ?  Why no in this plugin ?  Hello world builder ? 
  - its the actual step in Buildsteps that does the work (others may do something like setting up environment or poll source code)
- what is a perform method ? listener ? Launcher ? Build ? 
  - perform is the method inside a builder, also we can define other builders. Listener is for console output, launcher is another component which is not that important 
- How to use hpi to get a new plugin demo ? 
  - you can follow 
- Build step descriptor ? 
  - 
- what is view ? 
  - it is how a user can manipulate or control the projects through jenkins UI control. 
- what is ant ? 
  - its full name is Apache Ant, a Java library and command line tool whose mission is to drive processes described in build files as targets and extension points dependent upon each other. Its main use is the build of java applications.
- what is pipeline ?  what are the plugins for jenkins pipeline?  This is something really interesting in Jenkins if you want to know a more about jenkins. So read them when you are free.
- how does jenkins define a node?
- what is model object and Action ? 
- what is fingerprintFacet ? 
- what is steps especially the ones  in steps/
- what is  AbstractDescribibleImpl ?
- And you still have to know how to write the test !
- NEXT PHASE : WHAT TO DO

#### Jenkins Tutorialpoint Guide

- what is pipeline and does it relate to our workspace ? (or where will the EXWS plugin be used ? what kind of jenkins project ?) 
- how to define the build steps and other useful informations ? 

#### Jenkins Pipleline guide

- what is the difference between declarative and script ?
- where can I define the workspace and use EXWS pluign
- what is sectors and directives of a pipeline ? 
- is it only defined as a pipeline plugin ? 
- what is agent directive ? 
- what is runselector
- what is the build step
- other plugins for downstream and upstream ? 
- will it create the dir if it does not exist ?
- what will happen if no such disk name ? Or it is plugged out  ?
- do i need to read the disk info ? 
- why that is triggering () using a bracket ? 
- what is the External Workspace Templates?
- why it has something to do with NFS ? 
- what is the things under nodes/ dir ? 
- know more about a descriptor ?
- stepContextParameter ? Why use transient ? 
- why the run() in a step execution is declared protected ? 
- disk pool. disk pools id
- why getDiskPools is defined in a descriptor? Shouldn't it be a global config ? 



#### Jenkins plugin develop notice 

- read all the Plugin Develop tutorial and things like that.

- Tutorial Addresses : 

  [Plugin tutorial Videos](https://jenkins.io/blog/2017/08/07/intro-to-plugin-development/)

  [Github Contribution Page](https://github.com/jenkinsci/jenkins/blob/master/CONTRIBUTING.md)

  [Jenkins Tutorial](https://www.tutorialspoint.com/jenkins/)

  [Plugin Tutorial](https://jenkins.io/doc/developer/tutorial/)

  [Javadoc of Run](https://javadoc.jenkins-ci.org/hudson/model/Run.html)

  [External Workspace Mainpage](https://wiki.jenkins.io/display/JENKINS/External+Workspace+Manager+Plugin)

#### Jenkins Plugin Java Full Comprehension !

##### Annotations

- class NoExternalUse
- @Nonnull
- @Restricted
- @CheckforNull

##### related packages

##### Interfaces

- what is model object used for ?

##### Java questions

- QUES: is it the @Nonnull only checks the explicit null value rather than implicitly null value ? Or is @Nonnull annotation offer only compile-time security ? 
- QUES: what will happen is the @DataBoundConstructor  annotation isnot added ?  What is the underlying mechanism ? 
- does String declare a reference to String object ? 
- why use checkforNull when it is not necessary ? 
- How to use @Extension and since we 
- how does annotations work ? 
- what is the pom parent ?
- Java life cycles? Where were Descriptor stored ? 
- what is a class loader ?
- what is git cherry-pick
- what is a build wrapper ? 
- what is stapler ? 
- what does the bindJSON do ?
- what is the method or variable in a Descriptor and out of the Descriptor ?
- who can access the attributes in a Descriptor except for Global Configuration .
  - It is like the Descriptor attributes are managed by the Global and is shared among all Describable objects. The @DataBoundConstructor  attribute is something different within different Describable instances. It might need to a full understanding how the exws really works and help you understand the design pattern.
- What is @Inject and How to use transient and under what circumstances
- How to comprehend Java serialization ? 
- stream and exception and IO

#### Configuration as code Pull Request 

- how to add a new plugin support ? 

#### Plugin Test Code comprehension

- what is Mockito
- is there any dynamic class in Java  (classes created by program, or a class generator)
- what is @Rule and @ClassRule
- what is testCase as a RootAction
- what does throw do after a function 
- what is a nested type ?
- what is a configurationContext
- what is describe () used for ?

#### Jenkins CI manipulation

- TODO : how to get the .xml file in a blueOcean UI interface ? where to get the logs ? 
- 

#### NFS Java basics

- how to call the API?
- what  class should I use in Hudson ? 
- how to install the nfs-common on each machine/docker?
- how to auto configure the firewall settings ?  how does settings work ? 

#### Build Discard Plugin

- why bd cannot delete exws runs.
- why a build can be triggered by multiple upstream builds
- how to write run selector exws in a pipeline jenkins file using both selector and filter
- Things to discuss.
  - run.delete() ,then the run
  - getRootDir()
- QUESTIOn : inject, and the getContext, @Inject, and how does this work
- why 'Workspace of Multi Branch Pipeline are not deleted by Build Discarder'
- job1 : monday   job2: job1 execution job3: job2
- seed job :  running script ,  define test file1.java, file2.java , create multiple jenkins jobs.
- file1_test file2_test file3_test
- node1 : environment step . "setting environment"      node2 : "running computation"


#### Front End Jelly Tutorial

#### Git Commands




#### Questions

- what is Cloudbee ? 

  - IaaS Paas and SaaS model :  infrastructure as a service, Platform as service 
  - Cloudbee is a java Paas company

- what is Kafka

  - Apache Kafka : community distributed streaming platform capable : real time data pipelines and streaming apps, a message system, a technique used for distributed systems.

- what is hadoop ? 

  - a distributed system framework.(Hadoop Distributed File Systems) Map Reduce

- what is a Javadoc

  - you should ask more about how to write java doc. From now on every line of code I write must obey Alibaba Java Development Manual.

- what does 101 means in most cases ?  Something basic of a certain topic

- what is code coverage

  - Used to judge whether a test is good or bad ! 

- what is maven?

  - A build tool in Java, and can put build result on repositories as well. It is a software project management tool

- review the definition of POM , Project Object Model 

  - very much like gradle builds in Android development, define the structure of the app, and maven can help build the project according to pom.xml

- what is the hpi in maven : a jenkins plugin to build and package Jenkins plugins.

- what is hudson ? 

  - is also a CI tool writtten in java

- what is .jelly file and what language is it ?

  - Apache jelly is a Java and XML based scripting and processing engine for turning XML to executable code.
  - I will need this in the future.

- what does transient in Java mean

  - I have to know what is serialization and deserialization in Java

- what is run in jenkins ? 

- what is spring framework

  - a Java application framework ! 

- what is serialization and deserialization in Java? After this explain transient keyword

- NEXT

- what is scm ? by the way ?

  - software configuration management !! 

- what is Samba ? 

- what is Sonar ? Code unit test ?

  - it's a platform for code quality test

- can I use unit test instead of main function to do the leetcode ?

- what is config.jelly and global.jelly ? 

  - config.jelly is the UI for a exposed Desciptor, global is its UI in the global config page

- how to define an immutable class?

- what is the difference between an model and a describable ?

- know what is a node config and other stuffs ? 

- any thing that can be config 

- why descriptors can hold some methods ?   Why must put the methods in a descriptor rather than a 

  - what does the method in a descriptor mean ? Is it an interface ? Why not define in other places ? 

- distinguish the metadata and data

- what is steps

- what is save() used for ?

- what does the configure() do ?


[exws demo using Run Selector](https://docs.google.com/presentation/d/15GcQWoGtwGg7QUJRggTOrC4yn3nFBWLWCWmT_tzwjQM/edit) go to page 17.   

Four core implementations : 4 file under ```steps/``` folder, ExwsAllocateStep.java ExwsAllocateExecution.java ExwsStep.java ExwsAllocateExecution.java


