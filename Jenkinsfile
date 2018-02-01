pipeline {
  agent any
  stages {
    stage('build') {
      agent {
        docker {
          args '''version: "2"
services:
  node:
    image: "node:8"
    user: "node"
    working_dir: /home/node/app
    environment:
      - NODE_ENV=production
    volumes:
      - ./:/home/node/app
    expose:
      - "8081"
    command: "npm start"'''
          image 'node:8'
        }
        
      }
      steps {
        sh '''npm install
npm build'''
      }
    }
  }
}