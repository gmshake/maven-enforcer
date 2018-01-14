# Maven Enforcer Plugin

[![Apache License, Version 2.0, January 2004](https://img.shields.io/github/license/apache/maven-enforcer.svg?label=License)][license]
[![Maven Central](https://img.shields.io/maven-central/v/org.apache.maven.plugins/maven-enforcer-plugin.svg?label=Maven%20Central)](https://search.maven.org/#search%7Cga%7C1%7Cg%3A%22org.apache.maven.plugins%22%20a%3A%22maven-enforcer-plugin%22)
[![Jenkins Status](https://img.shields.io/jenkins/s/https/builds.apache.org/view/M-R/view/Maven/job/maven-box/job/maven-enforcer/job/master.svg?style=flat-square)][build]
[![Jenkins tests](https://img.shields.io/jenkins/t/https/builds.apache.org/view/M-R/view/Maven/job/maven-box/job/maven-enforcer/job/master.svg?style=flat-square)][test-results]

## Overview

The [Maven Enforcer Plugin][home] ....



# Home


Test


## Deploying web site

You can use the `deploySite.sh` or `deploySite.bat` script
without any profile, the site will be deployed to `https://maven.apache.org/enforcer-archives/enforcer-${project.version}`

```
sh ./deploySite.sh -Preporting
```

To deploy main version https://maven.apache.org/enforcer, use
```
sh ./deploySite.sh -Preporting -Psite-release
```

Note you can add arguments to the script to pass your svn credentials:
```
-Dusername=
-Dpassword=
```

## Workflow for site when releasing

Once release staged, you can publish a staged site.
```
cd target/checkout
sh ./deploySite.sh -Preporting
```
content will be in `https://maven.apache.org/enforcer-archives/enforcer-${project.version}`

Once vote passed, redeploy main site:

```
cd target/checkout (or use the version tag)
sh ./deploySite.sh -Preporting -Psite-release
```


License
-------
[Apache License, Version 2.0, January 2004][license]



[home]: http://maven.apache.org/enforcer/maven-enforcer-plugin
[license]: https://www.apache.org/licenses/LICENSE-2.0.html
[build]: https://builds.apache.org/view/M-R/view/Maven/job/maven-box/job/maven-enforcer/job/master/
[test-results]: https://builds.apache.org/view/M-R/view/Maven/job/maven-box/job/maven-enforcer/job/master/lastCompletedBuild/testReport/
[build-status]: https://img.shields.io/jenkins/s/https/builds.apache.org/view/M-R/view/Maven/job/maven-box/job/maven-enforcer/job/master.svg?style=flat-square
[build-tests]: https://img.shields.io/jenkins/t/https/builds.apache.org/view/M-R/view/Maven/job/maven-box/job/maven-enforcer/job/master.svg?style=flat-square
