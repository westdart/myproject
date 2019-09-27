
# Install and run Artifactory to hold maven releases:
```
$ docker pull docker.bintray.io/jfrog/artifactory-oss
$ docker run --name artifactory -d -p 8081:8081 docker.bintray.io/jfrog/artifactory-oss:latest
$ cp settings.xml ~/.m2/settings.xml
```
# Do the release
```
mvn release:prepare
mvn release:perform
```

# On failure to do a release
Clean up:
```
mvn release:rollback
git tag -d myproject-0.0.1 && git push --delete origin myproject-0.0.1
```
