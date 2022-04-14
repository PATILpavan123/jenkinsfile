# jenkinsfile

                pipeline syntax
                
        1. scripted           |            2. declaratibe
                              .
      1st syntax              .             u have predefined structure as mention in syntax file
       groovy engine          .
    
                              .     
   node {                     .         pipeline {                    //must be at top of structure
     // groovy script         .               agent any               // where to execute
   }                          .               
                                              stages {                // where whole work happen
        
                                              stage("build") {         //  bulld is stage name
                                                   steps {
                                                   echo 'building the application'
                                                   // script that execute command on jenkins agent
                                                   // eg. sh 'npm install'
                                                          sh 'npm build'
                                                   }
                                              } 
                              .               stage("test") {              // test stage
                                                   steps {
                                                      echo 'testing the application'
                                                   }
                                              } 
                              .
                              .               stage("test") {               // deploy stage
                              
                                                   steps {
                                                     echo 'deploying the application'
                                                   }
                                              } 
                                            }
                                            post {                           // execute some logic after all stages executed
                                                always {                    // send message anyhow
                                                //
                                                }
                                                failure  {                  // message send to team that build fail
                                                
                                                }
                                                //or
                                                sucsess {                   // message send to team that build sucseed
                                                }
                                         } 
                                          
   #reference  -  https://youtu.be/7KCS70sCoK0
