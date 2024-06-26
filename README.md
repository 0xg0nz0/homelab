# Chaos Manor Rebooted

This repo contains complete documentation of a new homelab setup.

## Objective

This home setup is meant for software development along with offering a secure environment at home for local file storage and backups, DNS lookup of hosts on the network, and other more basic features. Because some elements are meant to be local versions of decentralized cloud services in the future, there will be a heavy emphasis on use of Docker, Kubernetes and Helm for deploying software in a portable manner, so similar setups can in the future be deployed into decentralized cloud platforms like the [Akash Network](https://akash.network).

## Getting started

This homelab setup is Mac-centric, though a lot of the tools are portable.

### Bootstrap control node

- Install XCode CLI: `xcode-select --install`
- Install Homebrew: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
- Install pipx and the GitHub CLI: `brew install pipx gh`
- Install Ansible: `pipx install ansible`
- Set up work area: `mkdir -p $HOME/dev; cd $HOME/dev`
- Download this repo: `gh repo clone 0xg0nz0/homelab`
- Install Ansible roles: `ansible-galaxy install -r requirements.yml`

Note all of this will be done for you on the _managed nodes_ in the inventory.

## Prepare managed nodes

- Enable remote access: `sudo systemsetup -setremotelogin on`

## Run playbook

To run the playbook using the default `config.yml` in the root directory:

```shell
ansible-playbook main.yml -K -i inventory.ini
```

## What's in a name?

Many years ago [Jerry Pournelle](https://www.jerrypournelle.com) wrote a blog and a column in _Byte_ magazine called "Computing at Chaos Manor" which was an early instance of writing in public about building a homelab. I am in the process of refitting our homelab, and thought this would be a fitting nod to his early work.
