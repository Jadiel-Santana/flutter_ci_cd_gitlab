# CI/CD Using GitLab Runner, Fastlane and Firebase App Distribution

## Install FVM
  - brew tap leoafarias/fvm
  - brew install fvm

## Add Java on Environment path
  - export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-1.8.jdk/Contents/Home
  - export PATH=$JAVA_HOME/bin:$PATH

## Add Android SDK on Environment path
  - export ANDROID_HOME=/Users/your-user/Library/Android/sdk
  - export PATH=$PATH:$ANDROID_HOME/tools/bin/
  - export PATH=$PATH:$ANDROID_HOME/platform-tools/

## Add fvm/flutter on Environment path
  - export PATH="$PATH:/Users/your-user/fvm/default/bin"


## Install Gitlab Runner
  - brew install gitlab-runner
  - gitlab-runner register
    - URL:  CI/CD > Variables
    - Token: CI/CD > Variables
    - Name: Flutter Runner
    - Tags (Exemple: flutter, android, ios)
    - Shell
  - brew services start gitlab-runner
  - brew services stop gitlab-runner
  - brew services restart gitlab-runner
  - Run GitLab Runner as services of system


## Install Fastlane
  - brew install fastlane or gem install fastlane
  - cd folder (android or ios)
  - fastlane init (answer the questions)
  - create 'flutter_build.sh' file on 'fastlane' folder
  - chmod +x fastlane/flutter_build.sh (optional, if you need permission)
  - fastlane add_plugin firebase_app_distribution
  - Build your lanes inside the Fastfile file

## Create gitlab-ci.yml file
