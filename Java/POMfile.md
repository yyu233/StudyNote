POM is an acronym for Project Object Model. The pom.xml file contains information of project and configuration information for the maven to build the project such as dependencies, build directory, source directory, test source directory, plugin, goals etc.

Maven reads the pom.xml file, then executes the goal.


|Element	|Description|
|-------|---------|
|project|	It is the root element of pom.xml file.|
|modelVersion|	It is the sub element of project. It specifies the modelVersion. It should be set to 4.0.0.|
|groupId	|It is the sub element of project. It specifies the id for the project group.|
|artifactId	|It is the sub element of project. It specifies the id for the artifact (project). An artifact is something that is either produced or used by a project. Examples of artifacts produced by Maven for a project include: JARs, source and binary distributions, and WARs.|
|version	|It is the sub element of project. It specifies the version of the artifact under given group.|
