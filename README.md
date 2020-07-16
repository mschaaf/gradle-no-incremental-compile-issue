# gradle-no-incremental-compile-issue

1. run at least two times `./gradlew compileTestJava -i`
1. open file `src/test/java/com/example/demo/DemoApplicationTests.java`
1. remove one System.out line
1. re-run `./gradlew compileTestJava -i` and you get `Full recompilation is required because the chosen compiler did not support incremental annotation processing`
1. open the test file again
1. add a line e.g. 3 times the system.out line
1. re-run `./gradlew compileTestJava -i` and you get `Created classpath snapshot for incremental compilation in 0.001 secs. 1 duplicate classes found in classpath (see all with --debug). Class dependency analysis for incremental compilation took 0.0 secs.`
1. and not the message that a full recompilation is required
