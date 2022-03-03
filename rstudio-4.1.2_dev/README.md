# rstudio-4.1.2_dev

## Overview

This docker file extends [gcr.io/ris-registry-shared/rstudio:4.1.2](gcr.io/ris-registry-shared/rstudio:4.1.2) to include a few developmental libraries.

## Prerequisites

### .Rprofile

Add the following to your `~/.Rprofile` to set your library location to use storage:

```
vals <- paste('/storage1/fs1/<your_wustl_key>/Active/R_libraries/', paste(R.version$major, R.version$minor, sep="."), sep="")
for(devlib in vals) {
    if (!file.exists(devlib))
    dir.create(devlib)
x <- .libPaths()
x <- .libPaths(c(devlib, x))
}
rm(x, vals)
```

### rJava

If you try to install `rJava`, it may fail because .so files have been moved in OpenJDK11. Per this [StackOverflow](https://stackoverflow.com/questions/58607146/unable-to-run-a-simple-jni-program-error-message-when-installing-rjava-on-r-3) add the following to your `~/.bashrc`:

```
export LD_LIBRARY_PATH=/usr/lib/jvm/java-1.11.0-openjdk-amd64/lib/server:$LD_LIBRARY_PATH
```

## Example Job Submission

```
export PASSWORD=<your_novnc_password>
export LSF_DOCKER_PORTS='8080:8080'
export LSF_DOCKER_VOLUMES="/storage1/fs1/<your_wustl_key>/Active:/storage1/fs1/<your_wustl_key>/Active"
bsub -Is -R 'select[port8080=1]' -q general-interactive -a 'docker(<your_dockerhub_username/<image_name>:<tag>)' supervisord -c /app/supervisord.conf
```

See also an [example_submission_script.sh](example_submission_script.sh).
