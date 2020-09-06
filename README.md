Ansible Role: XcodeInstall
=========

This is used to install multiple xcode versions in one machine.

Requirements
------------

- The installer (.xip file) should be in `files` or specify it in `xcode_xip_location`

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

Example Playbook
----------------


#### install-xcode.yaml

    - hosts: localhost
      vars:
        xcode_version: 11.4.1
        xcode_xip_location: "Xcode_11.4.1.xip"
      roles:
        - tedgonzalez.xcodeinstall

Usage:
```
ansible-playbook install-xcode.yaml -K
```

#### install-multiple-xcodes.yaml

    - name: Run xcodeinstall role with 11.4.1
      hosts: localhost
      roles:
        - { role: tedgonzalez.xcodeinstall, xcode_version: 11.4.1 }
        
    - name: Run xcodeinstall role with 11.5.0
      hosts: localhost
      roles:
        - { role: tedgonzalez.xcodeinstall, xcode_version: 11.5.0 }

Usage:
```
ansible-playbook install-multiple-xcodes.yaml -K
```

#### install-xcode-gm-seed.yaml

    - name: Run xcodeinstall role with 11.5_GM_Seed
      hosts: localhost
      roles:
        - { role: tedgonzalez.xcodeinstall, xcode_version: 11.5, xcode_xip_location: "Xcode_11.5_GM_Seed.xip" }

Usage:
```
ansible-playbook install-xcode-gm-seed.yaml -K
```

#### install-xcode-from-downloads.yaml

    - name: Run xcodeinstall role with 11.7 from Downloads
      hosts: localhost
      roles:
        - { role: tedgonzalez.xcodeinstall, xcode_version: 11.7, xcode_xip_location: "~/Downloads/Xcode_11.7.xip" }

Usage:
```
ansible-playbook install-xcode-gm-seed.yaml -K
```

License
------------

MIT

Author Information
------------

This role was created in 2020 by [Theodore Gonzalez][author-website].

[author-website]: https://www.linkedin.com/in/gonzalezted/