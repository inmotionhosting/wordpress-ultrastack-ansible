# wordpress-ultrastack-ansible

This Ansible playbook deploys WordPress using either an optimized LAMP
stack or the suite of utilities that drive the heavily-optimized
InMotion UltraStack.

Usage
=============================

## Quick Start
1. Install Python dependencies:

    ```sh
    $ pip install -r python-requirements.txt
    ```

	Optionally consider managing your Python dependencies using
    [virtualenv]:

    ```sh
    $ virtualenv venv
    $ source venv/bin/activate
    (venv) $ pip install -r python-requirements.txt
    ```

2. Install Ansible dependencies:

    ```sh
    $ ansible-galaxy install -r playbook-requirements.yml
    ```

3. Copy [inventory.sample.yml]:

    ```sh
    $ cp inventory{.sample,}.yml
    ```

    The available settings are documented within this file, and
    explain how to use the playbook.

4. Run the playbook:

    ```sh
    $ ansible-playbook -i inventory.yml site.deploy.yml
    ```

## Update
1. Pull any changes to the playbook:

    ```sh
    $ git pull origin master
    ```

2. Update the playbook dependencies:

    ```sh
    $ ansible-galaxy install -r playbook-requirements.yml
    ```

4. Run the playbook:

    ```sh
    $ ansible-playbook -i inventory.yml site.deploy.yml
    ```

Files
=============================

| File | Description |
| ---- | ----------- |
| [ansible.cfg] | The Ansible configuration defined for this playbook.
| [inventory.sample.yml] | The inventory used by this playbook.
| [python-requirements.yml] | The Python dependencies required by this Playbook
| [playbook-requirements.yml] | The Playbook dependencies required by this Playbook

[ansible.cfg]: https://github.com/inmotionhosting/wordpress-ultrastack-ansible/blob/master/ansible.cfg
[inventory.sample.yml]: https://github.com/inmotionhosting/wordpress-ultrastack-ansible/blob/master//inventory.sample.yml
[python-requirements.yml]: https://github.com/inmotionhosting/wordpress-ultrastack-ansible/blob/master//python-requirements.yml
[playbook-requirements.yml]: https://github.com/inmotionhosting/wordpress-ultrastack-ansible/blob/master/playbook-requirements.yml
[virtualenv]: https://virtualenv.pypa.io/
