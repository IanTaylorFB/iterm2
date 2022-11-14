Ansible Role: Shurroo iTerm2
===============================

Installs `iterm2` on macOS using Homebrew and performs basic configuration. There are no role dependencies but please read the Requirements.

Requirements
------------

* Intel Mac (x86_64) (Apple Silicon, arm64, is not yet supported)
* macOS >= 12.1 (Monterey)
* XCode Command Line Tools (CLT)
* Homebrew
* Ansible >= 2.11

Note that the role is supported for local execution **only**.

Role Variables
--------------

You can enable a log summary to `~/.shurroo/log/` by setting:
```yaml
write_log_file: true
```
The log file is timestamped, so you can differentiate multiple plays, for example `shurroo_role_name-2022-0219-1817.log`. Even though a new file is created on each play, the log write does not add to the `changed` task count.

Dependencies
------------

There are no dependencies on other Ansible Galaxy roles, but you must have Homebrew installed. This role deliberately **does not** install Homebrew, and fails if Homebrew is not installed.

You can install Homebrew using the Shurroo [installer](https://github.com/Shurroo/install), or by following the Homebrew [instructions](https://brew.sh/). Note that either of these methods will install the Command Line Tools if they are needed.

Example Playbook
----------------

```yaml
- hosts: localhost
  connection: local
  roles:
    - role: Shurroo.iterm2
  vars:
    write_log_file: true
```

Source Files
------------

Playing the role using `shurroo play iterm2` will automatically discover and use a custom playbook file if it exists. The playbook file must be on a mounted volume named `Shurroo`, and in a `shurroo_role_name` folder, like this:
```shell
/Volumes/Shurroo/shurroo_role_name/iterm2.yml
```

Project Name
------------

The project was originally inspired from the [Superlumic](https://github.com/superlumic/superlumic) project by [Roderik van der Veer](https://github.com/roderik). When I started on a replacement, I searched for a name with some meaning like "launch", "fire up", "bootstrap" or similar. I eventually settled on Hindi "shurroo" (शुरू). [Google Translate](https://translate.google.com/?sl=en&tl=hi&text=begin&op=translate) tells me "shurroo" means "begin", so this works nicely. Note that the official latin spelling has only one "r", but that name was already taken on GitHub, so I added a second "r". See the parent [Shurroo](https://github.com/Shurroo/shurroo) project for more details.

License
-------

[BSD-3-Clause](https://spdx.org/licenses/BSD-3-Clause.html)

Author Information
------------------

Ian Taylor ([IanTaylorFB](https://github.com/IanTaylorFB)), Co-Founder and CTO at [FlyingBinary Ltd](https://flyingbinary.com).
