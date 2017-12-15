OMD
===
Install OMD Labs and manage one site.

This roles installs OMD Labs edition with default configuration (`Naemon` + `Thruk`). Other components can be chosen by setting options in `omd_config`. If Grafana is activated, this role will also adjust `check_mk` templates to produce the right action urls.

MKPs can also be installing by listing them in `omd_mkps`.

Requirements
------------
See `meta/main.yml`.

Role Variables
--------------
See `defaults/main.yml` for all options.

Dependencies
------------
EPEL repositories need to be available, ie using role `geerlingguy.repo-epel`. RHEL servers might need subscribe to the `optional` channel/repo, ie `rhel-x86_64-server-optional-7`.

Example Playbook
----------------
Example:
```
- hosts: servers
  roles:
    - omd
```

TODO
----
- Install a specific version, ie `1.30`.
- Support multiple sites.
- Check if nagios can send notifications.
- Revert to pnp4nagios graphing if requested, once grafana has been configured.
- Activate grafana action urls by inheriting from host-perf/srv-perf instead of changing url.
- Remove installation of python-pillow. OMD should take care of this.

Licence
-------
Released under the [MIT license](https://opensource.org/licenses/MIT).

Author Information
------------------
Luis Gracia while at [The Rockefeller University](https://www.rockefeller.edu):
- lgracia [at] rockefeller.edu
- GitHub at [luisico](https://github.com/luisico)
- Galaxy at [luisico](https://galaxy.ansible.com/luisico)
