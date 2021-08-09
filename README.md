Ansible Role: XcodeInstall
=========

This is used to install multiple xcode versions in one machine.

Requirements
------------

- The installer (.xip file) should be in `files` or specify it in `xcode_xip_path`

Role Variables
--------------

Available variables are listed below, along with default values (see [`defaults/main.yml`](defaults/main.yml)):

Name of the installer

    xcode_xip_name: "Xcode_13_beta_4.xip"

Path of the installer in local host

    xcode_xip_path: "~/Downloads/Xcode_13_beta_4.xip"

Path of the installer in local host relative to files directory 

    xcode_xip_path: "Xcode_13_beta_4.xip"


Path of the installed app

    xcode_app_output_path: "/Applications/Xcode-13-beta-4.app"

Dependencies
------------

None.

Example Playbook
----------------


#### install-xcode.yaml

    - hosts: localhost
      vars:
        xcode_xip_name: "Xcode_13.0.xip"
        xcode_xip_path: "~/Downloads/Xcode_13.0.xip"
        xcode_app_output_path: "/Applications/Xcode-13.0.app"
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
        - { 
            role: tedgonzalez.xcodeinstall, 
            xcode_xip_name: "Xcode_13.0.xip"
            xcode_xip_path: "~/Downloads/Xcode_13.0.xip"
            xcode_app_output_path: "/Applications/Xcode-13.0.app" 
        }
        
    - name: Run xcodeinstall role with 11.5.0
      hosts: localhost
      roles:
        - { 
            role: tedgonzalez.xcodeinstall,
            xcode_xip_name: "Xcode_13_beta_4.xip"
            xcode_xip_path: "~/Downloads/Xcode_13_beta_4.xip"
            xcode_app_output_path: "/Applications/Xcode-13.0-beta-4.app"
        }

Usage:
```
ansible-playbook install-multiple-xcodes.yaml -K
```

#### install-xcode-gm-seed.yaml

    - name: Run xcodeinstall role with 11.5_GM_Seed
      hosts: localhost
      roles:
        - { 
            role: tedgonzalez.xcodeinstall,
            xcode_xip_name: "Xcode_11.5_GM_Seed.xip"
            xcode_xip_path: "~/Downloads/Xcode_11.5_GM_Seed.xip"
            xcode_app_output_path: "/Applications/Xcode-11.5-gm-seed.app"
        }
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