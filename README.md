<!---
 Licensed to the Apache Software Foundation (ASF) under one or more
 contributor license agreements.  See the NOTICE file distributed with
 this work for additional information regarding copyright ownership.
 The ASF licenses this file to You under the Apache License, Version 2.0
 (the "License"); you may not use this file except in compliance with
 the License.  You may obtain a copy of the License at

      http://www.apache.org/licenses/LICENSE-2.0

 Unless required by applicable law or agreed to in writing, software
 distributed under the License is distributed on an "AS IS" BASIS,
 WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 See the License for the specific language governing permissions and
 limitations under the License.
-->
Maven Enforcer Plugin - The Loving Iron Fist of Maven™
======================================================

[![Apache License, Version 2.0, January 2004](https://img.shields.io/github/license/apache/maven-enforcer.svg?label=License)][license]
[![Maven Central](https://img.shields.io/maven-central/v/org.apache.maven.plugins/maven-enforcer-plugin.svg?label=Maven%20Central)](https://search.maven.org/#search%7Cga%7C1%7Cg%3A%22org.apache.maven.plugins%22%20a%3A%22maven-enforcer-plugin%22)
[![Jenkins Status](https://img.shields.io/jenkins/s/https/builds.apache.org/view/M-R/view/Maven/job/maven-box/job/maven-enforcer/job/master.svg?style=flat-square)][build]
[![Jenkins tests](https://img.shields.io/jenkins/t/https/builds.apache.org/view/M-R/view/Maven/job/maven-box/job/maven-enforcer/job/master.svg?style=flat-square)][test-results]

The Enforcer plugin provides goals to control certain environmental constraints
such as Maven version, JDK version and OS family along with many more built-in
rules and user created rules.

Documentation
-------------

More information can be found on [Apache Maven Enforcer Plugin Homepage][enforcer-home].
Question related to the usage of the Maven Enforcer Plugin should be posted on
the [Maven User List][users-list].


Where can I get the latest release?
-----------------------------------
You can download source and binaries from our [download page][enforcer-download]

You can get the Maven Enforcer plugin via the following coordinates from central:

```xml
<plugin>
  <groupId>org.apache.maven.plugins</groupId>
  <artifactId>maven-enforcer-plugin</artifactId>
  <version>3.0.0-M1</version>
</plugin>
```


Deploying web site
------------------

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

Workflow for site when releasing
--------------------------------

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

[enforcer-home]: https://maven.apache.org/enforcer/maven-enforcer-plugin/
[enforcer-download]: https://maven.apache.org/enforcer/download.cgi
[users-list]: http://maven.apache.org/mail-lists.html
