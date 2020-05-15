Failing test command

mvn -Dtest=FailingApplicationTests test

Passing test command

mvn -Dtest=WorkingApplicationTests test


Jenkins Pipeline Setup Test

1) Trigger pipeline on push to git repo: https://github.com/anatesan-stream/jenkins-build-test-repo.git
2) On Trigger:
        git clone repo
3) 2 branches in pipeline:
    3a) Passing Test branch
        3a1)Run passing test
        3a2) Check error code.  On success, zip git repo.   create new PassingDir with timestamp and copy
    3b) Failing Test branch
        3b1) Run failing test
        3b2) Check return code & Output error message