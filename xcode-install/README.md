Role Name
=========

A brief description of the role goes here.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see [`defaults/main.yml`](defaults/main.yml)):

Version of xcode to be installed to the remote host

    xcode_version: 11.4.1

Location of xip inside files directory or an absolute path in the local host

    xcode_xip_location: "Xcode_{{ xcode_version }}.xip"

Dependencies
------------

None.

## Example Playbook
    - hosts: localhost
      vars:
        xcode_version: 11.4.1
        xcode_xip_location: "Xcode_11.4.1.xip"
      roles:
        - xcode-install

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
------------

MIT

Author Information
------------

This role was created in 2020 by [Theodore Gonzalez][author-website].

[author-website]: https://www.linkedin.com/in/gonzalezted/