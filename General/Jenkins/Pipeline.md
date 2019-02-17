
## Pipeline ##

Jenkin Pipeline is a suite of plugins which supports implementing and integrating continuous delivery pipelines into Jenkins.    

**Pipeline as code** Jenkin Pipeline is written in text and put in the project's source repo which can be versioned and reviewed as code.   

Pipeline can pause to wait for human input or approval.  

**Node** a node is a machine which is part of the Jenkins environment and is capable to executing a Pipeline.    

**Stage** a stage block defines a subset of tasks performed throug the entire Pipeline ("Build", "Test" and "Deploy" stages).   

**Step** a step which is a single task telling Jenkins what to do at a particular time.   

Pipeline can be created by one of 3 ways:  

* Blue Ocean 
* Jenkins Classic UI 
* SCM (Source Code Management)


### Recording tests and artifacts ###

Jenkin can record and aggregate test results. 

```
pipeline { 
  agent any 
  stages {
    stage('Test') {
      steps {
        sh './gradlew check'
      }
    }
  }
  post {
    always {
      junit 'build/reports/**/*.xml'
    }
  }
}
```



