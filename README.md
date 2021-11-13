# Ansible role for installing docker on a host
Features:
- latest docker-ce
- docker python module
- docker-compose
- (optional) performs a docker system prune

# Requirements
- ansible

# How to use this role
### Method 1: Install using ansible-galaxy

The most robust way to install this role is to use ansible-galaxy,
which is installed with ansible by default. ansible-galaxy is effectively
a package manager for ansible. It installs roles from the community,
or from private git repos, into your local machine for use in your
playbooks.

Add this role to an ansible-galaxy dependency file. Typically this
file lives alongside your playbook file and by convention is named `requirements.yml`.

Add the following section:

```
roles:
  - name: creator-docker-ansible
    src: git+git@github.com:creatoreng/creator-docker-ansible.git
    version: main
```

If there is already a `roles` section, simply append this role to
add it as a dependency.

Then, install the role using ansible-galaxy:

`ansible-galaxy install -r requirements.yml -v`

### Method 2: Clone this repository into a `roles` directory

Use this method if you plan to modify this role, or if for some
reason the ansible-galaxy method fails.

*Do not add the code in this repo to another repo* which would
duplicate code and eliminate the benefits of having a modular
role that can be shared across multiple repos and playbooks.
The easiest way to ensure this is to add the `roles` directory
to your `.gitignore`.

Starting from your playbook directory, change into the `roles`
directory and clone:

```
$ ls
 > playbook.yml
 > roles/
$ cd roles/
roles$ git clone git@github.com:creatoreng/creator-docker-ansible.git
```
