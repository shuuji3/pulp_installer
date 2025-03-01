Pulp 3 RPM plugin prerequisites
===============================

This role installs prerequisite python packages and prerequisite linux distribution packages
for the pulp-rpm plugin.

It runs by default when `pulp-rpm` is part of `pulp_install_plugins` variable. It is called by the
`pulp_common` role.

Requirements
------------

Each currently supported operating system has a matching file in the "vars"
directory.

Example Playbook
----------------

Here's an example playbook for using pulp_rpm_prerequisites as part of pulp_installer.

    ---
    - hosts: all
      force_handlers: True
      vars:
        pulp_default_admin_password: << YOUR PASSWORD HERE >>
        pulp_settings:
          secret_key: << YOUR SECRET HERE >>
          content_origin: "https://{{ ansible_facts.fqdn }}"
        pulp_install_plugins:
          pulp-rpm: # no need to set subvar prereq_role for pulp_rpm specifically
      roles:
        - pulp_all_services
      environment:
        DJANGO_SETTINGS_MODULE: pulpcore.app.settings

License
-------

GPLv2+

Author Information
------------------

Pulp Team
