# Ansible Role: Dotfiles

[![Build Status](https://travis-ci.org/agmalpartida/ansible-role-dotfiles.svg?branch=master)](https://travis-ci.org/agmalpartida/ansible-role-dotfiles)

Installs a set of dotfiles from a given Git repository.

## Requirements

Requires `git` on the managed machine.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    dotfiles_repo: "https://github.com/agmalpartida/dotfiles.git"
    dotfiles_repo_version: master

The git repository and branch/tag/commit hash to use for retrieving dotfiles. Dotfiles should generally be laid out within the root directory of the repository.

    dotfiles_repo_accept_hostkey: false

Add the hostkey for the repo url if not already added. If ssh_opts contains "-o StrictHostKeyChecking=no", this parameter is ignored.

    dotfiles_repo_local_destination: "~/Git/dotfiles"

The local path where the `dotfiles_repo` will be cloned.

    dotfiles_home: "~"

The home directory where dotfiles will be linked.

    dotfiles_files:
      - .zshrc
      - .vimrc

Which files from the dotfiles repository should be linked to the `dotfiles_home`.

## Dependencies

None

## Example Playbook

    - hosts: localhost
      roles:
        - { role: agmalpartida.dotfiles }

## License

MIT / BSD
