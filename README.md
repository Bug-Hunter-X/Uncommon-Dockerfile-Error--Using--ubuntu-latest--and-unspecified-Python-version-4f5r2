# Dockerfile Bug: Using `ubuntu:latest` and Unspecified Python Versions

This repository demonstrates a common but often overlooked error in Dockerfiles: the use of `ubuntu:latest` as a base image and failure to specify Python and pip versions.

**Problem:**

The original `Dockerfile` uses the unstable `ubuntu:latest` image and doesn't explicitly define the Python and pip versions.  This may lead to build failures, inconsistencies across different environments, and security vulnerabilities in production due to unexpected updates in the base image.

**Solution:**

The corrected `Dockerfile` replaces `ubuntu:latest` with a specific Ubuntu version and specifies Python 3.9 and pip versions to ensure reproducibility and stability.

**How to reproduce the error:**

1. Clone the repository.
2. Try to build the original `Dockerfile` using `docker build -t my-app .`
3. Note the potential build issues or environment inconsistencies if the `ubuntu:latest` version changes.

**How to fix the error:**

1. Use the `Dockerfile-solution` instead of `Dockerfile`.
2. Build and run the corrected image with `docker build -t my-app-solution .`