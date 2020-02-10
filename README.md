# quarkus-test-result-reporting


When running a (suite) of tests in a test directory and NOT using quarkus
per-test stats are printed to the console.  This information is not provided 
when quarkus is used.  Only a summary of test results is printed.  This
makes it impossible to know what tests passed and what failed.  Tests have
to be run individually by hand. 
    

Typical non-quarkus console output.
    [INFO] Running org.jboss.resteasy.test.Expect100Test
    [INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.833 s - in org.jboss.resteasy.test.Expect100Test
    [INFO] Running org.jboss.resteasy.test.HeaderTooLongTest
    [INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.057 s - in org.jboss.resteasy.test.HeaderTooLongTest
    [INFO] Running org.jboss.resteasy.test.JaxrsAsyncTest
    [INFO] Tests run: 10, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 2.236 s - in org.jboss.resteasy.test.JaxrsAsyncTest
    [INFO] Running org.jboss.resteasy.test.Netty4ApplicationPathTest
    [INFO] Tests run: 3, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.125 s - in org.jboss.resteasy.test.Netty4ApplicationPathTest
    [INFO] Running org.jboss.resteasy.test.NettyTest
    [INFO] Tests run: 11, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 1.135 s - in org.jboss.resteasy.test.NettyTest
    [INFO] Running org.jboss.resteasy.test.PortAssigningTest
    [INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.005 s - in org.jboss.resteasy.test.PortAssigningTest


Quarkus test output.
    [INFO] Tests run: 9, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 10.608 s - in TestSuite
    [INFO] 
    [INFO] Results:
    [INFO] 
    [INFO] Tests run: 9, Failures: 0, Errors: 0, Skipped: 0


File xTest-console-output.txt contains the console output of the suite of
test run by this project.

Before running the test install this archive in your local repo.
Here is the cmd to do it.

mvn install:install-file \
   -Dfile=___FIX_THIS___/lib/utils-arquillian-utils-4.5.0-SNAPSHOT.jar \
   -DgroupId=org.jboss.resteasy \
   -DartifactId=utils-arquillian-utils \
   -Dversion=4.5.0-SNAPSHOT \
   -Dpackaging=jar 

Execution env.
    jdk 11.0.2
    mvn 3.6.0
    quarkus 1.3.0.Alpha1
    
  The pom.xml file contains the minimum archives required to compile and run the tests.
  See lines 268-278 for the set of tests being run.
  
  
  Compile project:
    mvn clean test -DskipTests=true
  
  Run tests
    mvn test
  
  