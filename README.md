# Basic Guidelines for Submitting to Cloudify Examples Org

## Documentation

Each repo's root directory should contain a README.md with the following sections:
  * Prerequisites
  * Tested Version (Most recent Cloudify version must be among them.)
  * Complete Install and Uninstall Instructions

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
