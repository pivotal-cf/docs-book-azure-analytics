# docs-book-azure-analytics

This repository contains metadata for the Nozzle for VMware Tanzu for Microsoft Azure Log Analytics documentation. We publish the Nozzle for VMware Tanzu for Microsoft Azure Log Analytics documentation at
https://docs.pivotal.io/azure-log-analytics-nozzle/index.html.

## How To Contribute

Please help us improve the accuracy and completeness of the Nozzle for VMware Tanzu for Microsoft Azure Log Analytics documentation by contributing content, editing,
or expertise.

A common way to contribute is to file a pull request through GitHub.

Every topic in the Nozzle for VMware Tanzu for Microsoft Azure Log Analytics documentation has a corresponding file in the
[https://github.com/pivotal-cf/docs-azure-analytics](https://github.com/pivotal-cf/docs-azure-analytics) content repository in
GitHub. To locate the source file for a topic, navigate to the topic on the Nozzle for VMware Tanzu for Microsoft Azure Log Analytics documentation site and click
"View the source for this page in GitHub" at the bottom of the topic.

## Versions and Branching

| **Branch Name** | **Content** | **Location** |
|-----------------|-------------|--------------|
| `master` | Nozzle for VMware Tanzu for Microsoft Azure Log Analytics | https://docs.pivotal.io/azure-log-analytics-nozzle/index.html |

**master**: The `master` branch is used to publish the live version of the site.
Create pull requests on `master` to contribute or correct technical inaccuracies in the Nozzle for VMware Tanzu for Microsoft Azure Log Analytics documentation.

## How To Use Bookbinder To View Your Documentation

[Bookbinder](https://github.com/pivotal-cf/bookbinder/blob/master/README.md) is a command-line
utility for stitching Markdown documents into a hostable web app. The documentation team uses
Bookbinder to publish our documentation sites, but you can also use Bookbinder to view a live
version of your documentation on your local machine.

Bookbinder draws the content for the site from this repository, the left navigation menu ("subnav")
from [docs-book-azure-analytics](https://github.com/pivotal-cf/docs-book-azure-analytics), and various layout
configuration and assets from [docs-layout-repo](https://github.com/pivotal-cf/docs-layout-repo).

To use Bookbinder to view your documentation, perform the following steps:

1. Clone this repository to the `~/workspace` directory on your local machine.
1. Clone the [docs-azure-analytics](https://github.com/pivotal-cf/docs-azure-analytics) and
[docs-layout-repo](https://github.com/pivotal-cf/docs-layout-repo) repositories to the `~/workspace` directory on your
local machine.
1. Navigate into the `docs-book-azure-analytics` directory.
1. Run `bundle install` to install all of the necessary gems, including Bookbinder.
1. Run `bundle exec bookbinder bind local` to build a Rack web-app of the book. After the bind has completed, navigate
into the `final_app` directory and run `rackup`. Then navigate to `localhost:9292/azure-log-analytics-nozzle/index.html` in a
browser.

## Continuous Integration and Continuous Delivery

We use Concourse pipelines to provide continuous integration and continuous delivery. Any change made to this repository
or the [https://github.com/pivotal-cf/docs-azure-analytics] content repository trigger a "bind" where the disparate parts of
the Nozzle for VMware Tanzu for Microsoft Azure Log Analytics documentation are assembled into a single web app. A successful bind triggers pushing the app to the
staging site,
[https://docs-pcf-staging.cfapps.io/azure-log-analytics-nozzle](http://docs-pcf-staging.cfapps.io/azure-log-analytics-nozzle). After
review, the staging site is manually pushed to the production site,
[https://docs.pivotal.io/azure-log-analytics-nozzle/](https://docs.pivotal.io/azure-log-analytics-nozzle/).

Concourse Pipeline:

* **master**: https://concourse.run.pivotal.io/teams/cf-docs/pipelines/cf-services?group=azure-analytics
