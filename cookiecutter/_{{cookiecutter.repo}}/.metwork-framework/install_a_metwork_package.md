# How to install/upgrade/remove {{cookiecutter.repo}} metwork module (with internet access)

[//]: # (automatically generated from https://github.com/metwork-framework/resources/blob/master/cookiecutter/_%7B%7Bcookiecutter.repo%7D%7D/.metwork-framework/install_a_metwork_package.md)

## Prerequisites

You must:

- have configured the metwork yum repository. Please see [the corresponding document](configure_metwork_repo.md) document to do that.
- have an internet access on this computer

## Install {{cookiecutter.repo}} metwork module

## Full installation

You just have to execute the following command (as `root` user):

```
yum install metwork-{{cookiecutter.repo}}
```

## Minimal installation

If you prefer to start with a minimal installation, you have to execute the following command
(as `root` user):

```
yum install metwork-{{cookiecutter.repo}}-minimal
```

## Optional Addons

### Optional dependencies addons

```
# To install some devtools
yum install metwork-mfext-devtools

# To install some scientific libraries
yum install metwork-mfext-scientific

# To install python2 support
# (including corresponding scientific and devtools addons)
yum install metwork-mfext-python2
```

{% if cookiecutter.repo == "mfserv" %}

### Optional {{cookiecutter.repo}} addons

```
# To install python2 support
# (see above to install full scientific and devtools support)
yum install metwork-mfserv-python2

# To install nodejs support
yum install metwork-mfserv-nodejs
```
{% endif %}
{% if cookiecutter.repo == "mfdata" %}

### Optional {{cookiecutter.repo}} addons

```
# To install python2 support
# (see above to install full scientific and devtools support)
yum install metwork-mfdata-python2
```
{% endif %}

{% if cookiecutter.repo != "mfcom" and cookiecutter.repo != "mfext" %}
## Services

You can start corresponding services with the root command:

```
service metwork start
```

Or you can also reboot your computer (because metwork services are started automatically on boot).
{% endif %}


## Uninstall {{cookiecutter.repo}} metwork module

{% if cookiecutter.repo != "mfcom" and cookiecutter.repo != "mfext" %}
To uninstall {{cookiecutter.repo}} metwork module, please stop corresponding metwork services with the `root` command:

```
service metwork stop {{cookiecutter.repo}}
```

Then, use the following command (still as `root` user):
{% else %}
To uninstall {{cookiecutter.repo}} metwork module, use the following command (still as `root` user):

{% endif %}

```
yum remove "metwork-{{cookiecutter.repo}}*"
```

## Upgrade {{cookiecutter.repo}} metwork module

To upgrade {{cookiecutter.repo}} metwork module, use the following commands (still as `root` user):

{% if cookiecutter.repo != 'mfcom' and cookiecutter.repo != 'mfext' %}
```
# We stop {{cookiecutter.repo}} services
service metwork stop {{cookiecutter.repo}}
```
{% endif %}

```
# We upgrade {{cookiecutter.repo}} metwork module
yum upgrade "metwork-{{cookiecutter.repo}}*"
```

{% if cookiecutter.repo != 'mfcom' and cookiecutter.repo != 'mfext' %}
```
# We start {{cookiecutter.repo}} services
service metwork start {{cookiecutter.repo}}
```
{% endif %}

## Uninstall all metwork modules

To uninstall all metwork modules, use following root commands:

```
# We stop metwork services
service metwork stop

# we remove metwork modules
yum remove "metwork-*"
```

## Upgrade all metwork modules

The same idea applies to upgrade.

For example, to upgrade all metwork modules on a computer, use following root commands:

```
# We stop metwork services
service metwork stop

# We upgrade metwork modules
yum upgrade "metwork-*"

# We start metwork services
service metwork start
```
