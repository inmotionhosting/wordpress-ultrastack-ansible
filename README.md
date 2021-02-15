# Ansible Playbook: WordPress UltraStack
This Ansible playbook deploys WordPress using either an optimized LAMP stack or
the suite of utilities that drive the heavily-optimized InMotion UltraStack.

| File                   | Description |
| ---------------------- | ----------- |
| [ansible.cfg]          | Ansible configuration file.
| [inventory.sample.yml] | Sample Ansible inventory.
| [requirements.txt]     | Required Python dependencies.
| [requirements.yml]     | Required Ansible dependencies.


Usage
==========

Quick Start
----------
1. Install Python dependencies using [virtualenv]:

    ```sh
    $ virtualenv venv
    $ source venv/bin/activate
    (venv) $ pip install -r requirements.txt
    ```

2. Install Ansible dependencies:

    ```sh
    $ ansible-galaxy install -r requirements.yml
    ```

3. Copy [inventory.sample.yml]:

    ```sh
    $ cp inventory{.sample,}.yml
    ```

4. Edit your `inventory.yml`:

    ```sh
    # Feel free to use your preferred editor
    $ vi inventory.yml
    ```

    In the `inventory.yml` file created in the last step, you will need to
    edit the placeholder values.  At minimum, you will need to change the
    reference to `domain.tld:` under `hosts`:

    ```sh
    $ diff inventory.sample.yml inventory.yml
    22c22
    <     domain.tld:
    ---
    >     a-real-domain.tld:
    ```

5. Run the playbook:

    ```sh
    $ ansible-playbook -i inventory.yml site.yml
    ```

Update
----------
To grab the latest copy of the Playbook and update an existing deployment, you
may use the following steps:

1. Pull any changes to the playbook:

    ```sh
    $ git pull origin master
    ```

2. Update the Python dependencies:

    ```sh
    $ pip install -Ur requirements.txt
    ```

3. Update the Playbook dependencies:

    ```sh
    $ ansible-galaxy install -r requirements.yml --force
    ```

4. Run the Playbook:

    ```sh
    $ ansible-playbook -i inventory.yml site.yml
    ```

[ansible.cfg]: https://github.com/inmotionhosting/wordpress-ultrastack-ansible/blob/master/ansible.cfg
[inventory.sample.yml]: https://github.com/inmotionhosting/wordpress-ultrastack-ansible/blob/master/inventory.sample.yml
[requirements.txt]: https://github.com/inmotionhosting/wordpress-ultrastack-ansible/blob/master/python-requirements.txt
[requirements.yml]: https://github.com/inmotionhosting/wordpress-ultrastack-ansible/blob/master/playbook-requirements.yml
[virtualenv]: https://virtualenv.pypa.io/
