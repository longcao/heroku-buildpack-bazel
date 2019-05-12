# heroku-buildpack-bazel
Heroku buildpack for [Bazel](https://bazel.build/). Currenly, only Java projects are supported.

Bazel is an open-source build tool created by and for the engineers at Google.

## Required files
1. `BUILD`
  See the documentation on top-level [BUILD](https://docs.bazel.build/versions/master/tutorial/java.html#creating-your-own-build-file) files.
2. `WORKSPACE`
  See the documentation on [Bazel `WORKSPACE`s](https://docs.bazel.build/versions/master/tutorial/java.html#set-up-the-workspace).
3. `build_path`
   This file should contain text for the bazel path to the deploy jar for your application.
   For example, if the path to your `java_binary` target is `pkg:server`, this file should contain:
   ```text
   pkg:server_deploy.jar
   ```

## Procfile
You'll need to include a `Procfile` with your application since we default to [noop releases](bin/release).

## Use this buildpack
```shell
heroku buildpacks:set https://github.com/longcao/heroku-buildpack-bazel
```