# Basic Guidelines for Submitting to Cloudify Examples Org

## Naming

"Publishing" to the Cloudify Examples website is simple. A repository needs its name to end in the type of one of the three categories:
  * -blueprint
  * -plugin
  * -integration

For example, `multicloud-blueprint`, `bigip-plugin`, etc.

If a repository should not be published to getcloudify examples for some reason, e.g. the current repository, which is a guide to publishing, simply do not put one of those words in the title of the repository.


## Documentation

Each repo's root directory should contain a README.md with the following sections:
  * Summary of what the example is about
  * Prerequisites
  * Tested Version (Most recent Cloudify version must be among them.)
  * Complete install and uninstall instructions


## Directory Structure

A blueprint is the file as well as any files that are part of its archive. So that users can easily understand examples, we want to keep strict rules about the structure of the blueprint repository.

* Root Directory Contains
  * README.md
  * blueprint files
  * scripts directory (unless empty)
  * types directory (unless empty)
  * resources directory (unless empty)


### Blueprint filenaming convention

A blueprint should end in the string "-blueprint.yaml".

A repository should include a simple blueprint that does not include any infrastructure code. It should be named "example-application-blueprint.yaml", depending on what the example application is. For example, "tomcat-application-blueprint.yaml" or "lamp-application-blueprint.yaml".

There should also be an IaaS example, preferrably for both Openstack and EC2 Classic, named "openstack-example-blueprint.yaml". So, the same current example would be "openstack-tomcat-application.yaml".


### Types Directory

The types directory should contain any imports in the blueprint that are not imported from an url.

For example, this will map to the types folder:
```
imports:
  - types/my_custom_types.yaml
```


### Scripts Directory

The scripts directory should contain folders for the applications that the scripts install. If you use a tasks.py file for the Fabric plugin, it should just contain the tasks.py file.


### Resources Directory

The resources directory may contain templates, or files that you will use ctx.download_resource against in your blueprints.
