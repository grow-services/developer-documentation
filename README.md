# GROW Services developer documentation

This repository contains the source-files of the developer documentation of the GROW Services.

## Chapters

* Introduction
* ...


## Building

### Acquiring the source-files

1) Checkout this repository to your local machine:

    git checkout git@github.com:grow-services/developer-documentation.git

2) Enter the repository:

    cd developer-documentation

### Install dependencies

The build script requires `apache ant` `composer` and `wkhtmltopdf`.

Run `composer install` to pull in the dependencies for `bin/publish`

### Publish

With all dependencies installed, simply run `ant publish` to trigger a full build.

The deliverables will be generated in `build/html/` and `build/pdf/`

### Contributing

Improvements and corrections to this documentation is encouraged in the form of pull-requests.

