# what is Pipeline ?
In jenkins, a pipeline is a group of events or jobs which are interlinked with one another in a sequence.

Build--->Test---->Deploy--->Release

# how to Set up Build Pipeline in Jenkins

# Step1:-
chain require jobs in sequence add upstream/downstream jobs
# Step2:- 
Install Build pipeline plugins
# Step3:-
Add build pipeline view configure the view step 
# Step4:- 
Run and validateS

# How many ways we can create pipeline

we can create jenkins pipelines in 2 ways

1> using build and delivery pipeline plugins.

2> Using Groovy script on the Fly ( here we can use jenkins file)
# Script
# Declarative 

# Build And Delivery Pipeline plugins

![image](https://github.com/rawatarvind/jenkinspipeline/assets/122955926/34ed70ea-60da-45d3-8c5e-8f49a14c8e2f)


# pipeline job with Scripting 

![image](https://github.com/rawatarvind/jenkinspipeline/assets/122955926/082fd936-96f1-4663-a438-3ea05ad0c915)

# concept of pipeline
# Pipeline
1. A pipeline is a user-defined model of a CD pipeline. A pipeline's code defines your entire build process, which typically includes stages for building an application, testing it and delivering it.

2. Also a pipeline block is a key part of declarative pipeline syntax.
3. node is a machine which is part of the jenkins environment and is capable of executing a pipeline.
4. also a node block is a key part of scripted pipeline syntax.
# Stage:-
A stage block defines a conceptually destinct subset of tasks performed through the entire pipeline (e.g "build" "test" and "Deploy" "stage"), which is used by many plugins to visualize or present jenkins pipeline status/process.

# Step
A single task fundamentally a step tells jenkins what to do at a particular point in time ( or "step" in the process )
for example to execute the shell command make use the sh step: sh make : when a plugin  extends the pipeline DSL, that typically means the plugin has implemented a new step.

# "Scripted Pipeline"
jenkins file (scripted pipeline)
node { 1.
    stage ('Build')  { 2.
       // 3.
       }
       stage ('Test') { 4.
         // 5.
         }
         stage ('Deploy') { 6.
           // 7.
           }
    }

  1. Execute this pipeline or any of its stages on any available agent, defines the "Build" stage.
     Stage blocks are optional in scripted pipeline syntax.however implementing
  2. Stage blocks in a scripted pipeline provides clearer visualization of each stage's subset of tasks steps in the jenkins UI
  3. Perform some steps related to the "build" stage.
  4. Defines the "Test" stage.
  5. Perform some steps related to the "Test" stage.
  6. Defines the "Deploy" stage
  7. Perform some steps related to "Deploy" stage.

# " Declarative Pipeline "
jenkinsfile ( Declarative Pipeline )

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}

