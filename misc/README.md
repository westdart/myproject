
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
or:
```
$ set -o pipefail; tag=$(grep 'project.rel.com' release.properties | awk -F ':' '{print $NF}' | sed 's/=/-/g') && git tag -d $tag && git push --delete origin $tag && mvn release:rollback && git push
```


# Do a release and build of corresponding docker image
```
mvn release:prepare release:perform -P fabric8 fabric8:build
```
