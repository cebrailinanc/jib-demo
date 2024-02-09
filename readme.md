docker pull openjdk:21-slim



### This command is successful
``` 
jib command: ./gradlew jibDockerBuild --image=poc-jib:latest  -Djib.from.image=openjdk:21-slim -Djib.extraDirectories.paths='extra'
```
### This command is failed
```
./gradlew jibDockerBuild --image=poc-jib:latest  -Djib.from.image=openjdk:21-slim -Djib.extraDirectories.paths='extra, /var/temp' --stacktrace
``` 
fail log
``` 
* What went wrong:
| Execution failed for task ':jibDockerBuild'.
| > extraDirectories.paths contain "from" directory that doesn't exist locally:  /var/temp
``` 


`docker run --rm -it --entrypoint bash poc-jib`
