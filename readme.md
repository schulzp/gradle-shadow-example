### I like the shade, does it come with sources? ###

A proof of concept project, to find out if shaded jars with sources are possible.

Usually shading works like this: pull in some 3rd party dependencies, bundle them in a single artifact and rename some packages while doing so. This can be done with the great [shadow plugin](https://github.com/johnrengelman/shadow). Once that is done the [maven-publish plugin](http://www.gradle.org/docs/current/userguide/publishing_maven.html) adds some meta information and that's it.

It's all smooth sailin' until you want to debug into the shaded code. The shadow plugin is not capable of shadowing sources, yet. Hence maven-publish cannot attach any sources. And since debugging without sources is not very insightful, this project arose.

**TL;TR** It works! Have a look at the `build.gradle` or simply run `$ gradle -q publish`.

