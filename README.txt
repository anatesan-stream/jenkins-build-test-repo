JENKINS Configuration/Scripting Test

Your goal is to build up a CI pipeline that 

1- gets triggered by a push to a Github repository (https://github.com/anatesan-stream/jenkins-build-test-repo.git)
    - Run "mvn clean install -DskipTests" to build the repo (Skip running tests at this point, since some tests will fail by design)

2- Sets up the QA environment by simulating a deployment in a QA-<Timestamp> directory
    - In the QA environment buid step - The command below determines the outcome 
        mvn -Dtest=WorkingApplicationTests test
    - If a designated QA-Env test passes, zip up the gip repo and copy it to that QA directory above
    - If the designated QA-Env test fails,  generate an Error file in the QA directory,  with the name QA-Error.log and content "QA-Test failed on <Timestamp>"

3- Sets up the STAGE environment by simulating a deployment in a STAGE-<Timestamp> directory
    - In the STAGE environment buid step - The command below determines the outcome
         mvn -Dtest=FailingApplicationTests test
    - If a designated STAGE-Env test passes, zip up the gip repo and copy it to that STAGE directory above
    - If the designated STAGE-Env test fails,  generate an Error file in the STAGE directory,  with the name STAGE-Error.log and content "STAGE-Test failed on <Timestamp>"


