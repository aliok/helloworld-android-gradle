/**
* Android Jenkinsfile
*/
node('android') {
    stage 'Checkout'
    checkout scm

    stage ('Build'){
         def proc = ["/bin/sh", "-c", "cat /etc/passwd"].execute()
         proc.waitFor()
         println "stdout: ${proc.in.text}"
         println "return code: ${ proc.exitValue()}"
         println "stderr: ${proc.err.text}"
         sh "./gradlew clean assembleDebug"
    }
    stage 'Archive'
    archive 'app/build/outputs/apk/*.apk'
}
