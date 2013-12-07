Build
=====

This plugin is built with Maven. It depends on Gerrit-Plugin-Api and on
hooks-its library.

Compile against released Gerrit version pom.xml must be adjusted to reflect
the Gerrit Api version. For example to compile against Gerrit-Api 2.8 change
the "2.9-SNAPSHOT" to "2.8".

First hooks-its must be installed in the local Maven repository (it is
currently not distributed in public Maven repository):

```
  cd hooks-its
  mvn clean install
```

Now bugzilla-its binaries can be created:

```
  cd hooks-bugzilla
  mvn clean package
```

To skip the unit tests, Java system property -DskipTests=true can be used:

```
  mvn clean package -DskipTests=true
```

The binary artifact can be found in the target directory:

```
  target/hooks-bugzilla-2.8.jar
```

To compile against Gerrit development version Gerrit Plugin API must be
available. How to build the Gerrit Plugin API is described in the [Gerrit
documentation](../../../Documentation/dev-buck.html#_extension_and_plugin_api_jar_files).

