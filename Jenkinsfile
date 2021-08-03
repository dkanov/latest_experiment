#!/usr/bin/env groovy

timestamps
{
    timeout(time: 2, unit: 'HOURS')
    {
        stage('Build'){
            node('dind'){
                docker.image("centos:7.9.2009").inside('--network host --entrypoint=""')
                    {
                        dir('checkout'){
                            retry(3){
                                checkout scm
                            }

                            deleteDir()
                    }//dir checkout
                }//docker.image.inside
            }//node
        }//stage
    }//timeout
}//timestamps

