Ansible role: InfluxDB
======================

Install and configure InfluxDB.

Role Variables
--------------

```
ENTRY POINT: main - Install and configure InfluxDB

OPTIONS (= is mandatory):

- influxdb_apt_key_fingerprint
        Fingerprint for influxdb apt signing key
        [Default: (null)]
        type: str

- influxdb_root
        Root directory for metadata, data, and wal
        [Default: /var/lib/influxdb]
        type: str

- influxdb_settings
        Configuration for influxdb
        [Default: (null)]
        elements: dict
        type: list

        OPTIONS:

        = option
            Name of the option

            type: str

        = section
            Name of the section (use null to place a setting before
            the first section)

            type: raw

        = value
            Value for the option

            type: str
```

Installation
------------

This role can either be installed manually with the ansible-galaxy CLI tool:

    ansible-galaxy install git+https://github.com/wandansible/influxdb,main,wandansible.influxdb
     
Or, by adding the following to `requirements.yml`:

    - name: wandansible.influxdb
      src: https://github.com/wandansible/influxdb

Roles listed in `requirements.yml` can be installed with the following ansible-galaxy command:

    ansible-galaxy install -r requirements.yml

Example Playbook
----------------

    - hosts: influxdb_hosts
      roles:
         - role: wandansible.influxdb
           become: true
