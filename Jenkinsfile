pipeline {
agent any

```
environment {
    APP_DIR = "/var/lib/jenkins/workspace/express-cicd-pipeline"
}

stages {

    stage('Clone Repo') {
        steps {
            git branch: 'main',
            url: 'https://github.com/suneelp300/express-app.git'
        }
    }

    stage('Install Dependencies') {
        steps {
            sh '''
            cd $APP_DIR
            npm install
            '''
        }
    }

    stage('Restart Express App') {
        steps {
            sh '''
            cd $APP_DIR

            pm2 restart express-app || \
            pm2 start npm --name express-app -- start

            pm2 save
            '''
        }
    }
}
```

}
