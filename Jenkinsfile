#!groovy

@Library('jenkins-mobile-pipeline-shared-libraries') _

pipelineOptions{
    maxNumberBuildsToKeep = 10
}

synchronizeBuildNumbers{
    platformName = 'android'
    projectName = 'mobile_shared_library'
}

checkoutScm {
    nodeLabel = 'centos_7'
}

androidStaticAnalysis {
    nodeLabel = 'centos_7'
    gradleTasksDebug = 'compileDebugSources findBugs'
}

androidBetaUpload {
    nodeLabel = 'centos_7'
    gradleTasksDebug = 'assembleDebug'
}

androidUnitTests {
    nodeLabel = 'centos_7'
    gradleTasksDebug = 'testDebugUnitTest'
}

androidUITests {
    nodeLabel = 'android_emulator'
    emulatorName = 'jenkins_emulator_26'
    gradleTasksDebug = 'connectedDebugAndroidTest'
}

androidBuild {
    nodeLabel = 'centos_7'
    gradleTasksDebug = 'assembleDebug'
}

androidMonkeyTests {
    nodeLabel = 'android_emulator'
    emulatorName = 'jenkins_emulator_27'
    apkNameDebug = 'app-debug.apk'
    packageName = 'io.jenkins.mobilepipelinesampleproject.sampleprojectformobilesharedlibraryci'
    eventCount = '10'
    seedValue = '1'
    throttleValue = '0'
}

androidAddTrustCaToApk {
    nodeLabel = 'centos_7'
    apkName = 'app-debug.apk'
}
