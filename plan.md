# Python virtual environment

```
python3 -m venv ~/venv/ansible-demo --prompt yeah
pip install --upgrade pip
pip install wheel
pip install ansible-base
```

/opt/scripts/pyenv.sh
. ~/venv/ansible-demo/bin/activate

# Git

Git clone repository

/opt/scripts/clone.sh

# YAML?

Human readable. *Spaces are important!*. Tabs will ruin your day.

## Key/Value

`key: value`

## Lists

```
key:
  - list1
  - list2
```

Or:

```
key: [list1, list2]
```

## Nested dictionaries

```
vrfs:
  brian:
    description: My awesome vrf
  john:
    description: Another awesome vrf
```

# Inventories

Can be YAML, INI-style and so on.. For static inventories, I prefer YAML.

```
$ ansible-inventory -i foo/bar.yml --graph
$ ansible-inventory -i foo/bar.yml --host rt01.demo.local
```

Variables can be defined a number of different levels. 
See https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html#ansible-variable-precedence

## Simple

Simple inventory - with no variables

## Simple with variables inline

Simple one-file inventory with variables stored directly in the inventory

## With groups

Put hosts into different groups to target specific hosts.

## With groups and vars

Variables are sources from group_vars and hosts_vars 
# Modules

Ansible Galaxy

## Builtin

### Template

Template modules takes a template and generates a file. Templates can also be used
as source for other modules - ie `cisco.nxos.nxos_config`

#### Jinja2

Templating language.

Look out for `{{ foo }}` - anything enclosed in double curly brackets is a variable

Loops
```
{% for foo in bar}
{{ foo }}
{% endfor %}
```

Conditionals
```
{% if name == 'John' %}
It really is John
{% else %}
It's someone else
{% endif %}
```

Whitespace!

## Collections

FQCN - Fully Qualified Collection Name

```
$ ansible-Galaxy collection install <name>
```

### cisco.nxos

### cisco.iosxr
