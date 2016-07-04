# Code Corps WordPress Trellis (Public)

![Code Corps Public Trellis Logo](https://d3pgew4wbk2vb1.cloudfront.net/images/github/code-corps-trellis-public.png)

The public Trellis contains Ansible playbooks for setting up a LEMP stack for local WordPress development environments with Vagrant.

## What's included

Trellis will configure a server with the following and more:

* Ubuntu 14.04 Trusty LTS
* Nginx (with optional FastCGI micro-caching)
* PHP 7.0
* MariaDB (a drop-in MySQL replacement)
* SSL support (scores an A+ on the [Qualys SSL Labs Test](https://www.ssllabs.com/ssltest/))
* Let's Encrypt integration for free SSL certificates
* HTTP/2 support (requires SSL)
* Composer
* WP-CLI
* sSMTP (mail delivery)
* MailHog
* Memcached
* Fail2ban
* ferm

## Requirements

Make sure all dependencies have been installed before moving on:

* [Ansible](http://docs.ansible.com/ansible/intro_installation.html#latest-releases-via-pip) 2.0.2
* [Virtualbox](https://www.virtualbox.org/wiki/Downloads) >= 4.3.10
* [Vagrant](https://releases.hashicorp.com/vagrant/1.8.1/) 1.8.1
* [vagrant-bindfs](https://github.com/gael-ian/vagrant-bindfs#installation) >= 0.3.1 (Windows users may skip this)
* [vagrant-hostmanager](https://github.com/smdahlen/vagrant-hostmanager#installation)

## Installation

Clone this repository along with the site itself into the following directory structure:

```shell
blog.codecorps.org/      # → Root folder for this project
├── trellis-public/      # → Your clone of this repository
├── trellis/             # → Your clone of the private Trellis repository (acccess limited; private for security)
└── site/                # → Your clone of the site repository, a Bedrock-based WordPress site
    └── web/
        ├── wp/          # → WordPress core (don't touch!)
        └── app/         # → WordPress content directory (themes, plugins, etc.)
            └── web/themes/codecorps  # → Code Corps theme directory (where most blog dev work will happen)
```

1. Create the main project directory (if not already created): `$ mkdir blog.codecorps.org && cd blog.codecorps.org`
2. Clone Trellis: `$ git clone git@github.com:code-corps/blog.codecorps.org-trellis-public.git trellis-public`
3. Clone the site: `$ git clone git@github.com:code-corps/blog.codecorps.org-site.git site`
4. Install the Ansible Galaxy roles: `$ cd trellis && ansible-galaxy install -r requirements.yml`

Windows user? [Read the Trellis Windows docs](https://roots.io/trellis/docs/windows/) for slightly different installation instructions. Please modify them to match these docs. VirtualBox is known to have poor performance in Windows — use VMware or [see some possible solutions](https://discourse.roots.io/t/virtualbox-performance-in-windows/3932).

## Documentation

Trellis documentation is available at [https://roots.io/trellis/docs/](https://roots.io/trellis/docs/).

## Local development setup

1. Configure your WordPress sites in `group_vars/development/wordpress_sites.yml` and in `group_vars/development/vault.yml`
2. Run `vagrant up`

[Read the local development docs](https://roots.io/trellis/docs/local-development-setup/) for more information.

## Contributing

Contributions are welcome from everyone. We have [contributing guidelines](https://github.com/blog.codecorps.org-site/blob/master/CONTRIBUTING.md) to help you get started.

## Community

Join the Code Corps community at [https://codecorps.org/code-corps/code-corps]([https://codecorps.org/code-corps/code-corps])
