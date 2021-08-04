#!/usr/bin/env groovy
timestamps
{
    timeout(time: 2, unit: 'HOURS')
    {
        stage('Build'){
            node{
                docker.image("centos:7.9.2009").inside
                    {
                        dir('checkout'){
                            retry(3){
                                checkout scm
                            }
                        sh "ls -lrth"
                        deleteDir()
                    }//dir checkout
                }//docker.image.inside
            }//node
        }//stage
    }//timeout
}//timestamps

