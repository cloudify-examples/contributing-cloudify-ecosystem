# Basic Guidelines for Contributing to Cloudify Ecosystem

## Naming

The plugin repository name should start with the prefix `cloudify-` and end with the suffix `-plugin`, for example, `cloudify-kubernetes-plugin`.

## Documentation

Each repo's root directory should contain a README.md with the following sections:
  * Summary of what the example is about
  * Prerequisites
  * Tested Version (Most recent Cloudify version must be among them.)
  * Complete `install` and `uninstall` instructions
  * Additional workflows, for example any supported `execute_operation` workflows, or custom workflows like `rolling_upgrade`.

## Directory Structure

The plugin directory structure should conform to that of standard Python projects, with the addition of a plugin YAML:

* ./
  * ./setup.py
  * ./my_package
    * ./my_package/__init__.py
    * ./my_package/my_module.py
  * ./plugin.yaml
  * ./README.md
  * ./integration_tests
  * ./integration_tests/__init__.py
  * ./integration_tests/test_my_plugin.py

## Integration Tests

See [cloudify-ecosystem-tests](https://github.com/cloudify-incubator/cloudify-ecosystem-test).

## Examples

The [cloudify-kubernetes-plugin](https://github.com/cloudify-incubator/cloudify-kubernetes-plugin) is an example of a good plugin.

To learn how to write a plugin, see also the read me of this (non-functional) example [requests plugin](https://github.com/EarthmanT/cloudify-requests-plugin).
