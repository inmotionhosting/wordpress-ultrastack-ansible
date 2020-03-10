# wordpress-ultrastack-ansible

This Ansible playbook deploys WordPress using either an optimized LAMP
stack or the suite of utilities that drive the heavily-optimized
InMotion UltraStack.


Usage
=============================

1. First, install the needed Python dependencies:

    ```sh
    $ pip install -r python-requirements.txt
    ```

	Consider managing your Python dependencies using
    [virtualenv](https://virtualenv.pypa.io/).  The following is an
    example of the steps you _might_ take, based on your preferred way
    of managing Python dependencies:

    ```sh
    # VirtualEnv setup
    $ pip install --user --upgrade virtualenv
    $ virtualenv .venv
    $ source ./venv/bin/activate

    # Install the Python dependencies required by this playbook
    (.venv) $ pip install -r python-requirements.txt
    ```

2. Next, install the dependent Ansible roles:

    ```sh
    $ ansible-galaxy install -r playbook-requirements.yml -p ./roles
    ```

3. Copy the [inventory.sample.yml](./inventory.sample.yml) file:

    You may use any file name you want, though if you do not have a
    preference a common idiom is to copy it to `inventory.yml`.

	Clarification on the existing settings as well as how the variables
	should be modified is provided in-situ.

4. Finally, run the playbook:

    ```sh
    $ ansible-playbook -i inventory.yml site.deploy.yml
    ```


Files
=============================

| File | Description |
| ---- | ----------- |
| [ansible.cfg](./ansible.cfg) | The Ansible configuration defined for this playbook.
| [inventory.sample.yml](./inventory.sample.yml) | The inventory used by this playbook.
| [python-requirements.yml](./python-requirements.yml) | The Python dependencies required by this Playbook
| [playbook-requirements.yml](./playbook-requirements.yml) | The Playbook dependencies required by this Playbook
