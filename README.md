

# Rollback:
```
$ tag=$(grep 'project.rel.com' release.properties | awk -F ':' '{print $NF}' | sed 's/=/-/g') && git tag -d $tag && git push --delete origin $tag && mvn release:rollback
```
