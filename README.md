avanov.pyenv
============

[![Build Status](https://travis-ci.org/fingul/ansible-galaxy-pyenv.svg)](https://travis-ci.org/fingul/ansible-galaxy-pyenv)


Ansible Galaxy role for [pyenv](https://github.com/yyuu/pyenv) on Ubuntu.

Install it with the following command:

```bash
$ ansible-galaxy install fingul.pyenv
```

Requirements
------------

None

Role Variables
--------------

Here is the list of all variables and their default values:

* ``pyenv_path: "{{ ansible_env.HOME }}/pyenv"``
* ``pyenv_owner: "{{ ansible_env.USER }}"``
* ``pyenv_runcom: "~/.bashrc"``
* ``pyenv_python_versions: ["3.4.1"]``
* ``pyenv_virtualenvs: [{ venv_name: "latest", py_version: "3.5.1" }]``
* ``pyenv_update_git_install: no``



Dependencies
------------

None

Example Playbook
-------------------------

    - hosts: servers
      roles:
         - role: avanov.pyenv
           pyenv_path: "~{{ ansible_ssh_user }}/.pyenv"
           pyenv_runcom: "~{{ ansible_ssh_user }}/.zshrc"
           pyenv_owner: "{{ ansible_ssh_user }}"
           pyenv_update_git_install: no
           pyenv_python_versions:
             - "3.5.1"
             - "2.7.11"
           pyenv_virtualenvs:
             - venv_name: "latest_v3"
               py_version: "3.5.1"
               
             - venv_name: "latest_v2"
               py_version: "2.7.11"

License
-------

MIT

Author Information
------------------

Fingul (https://github.com/fingul)
