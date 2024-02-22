# Ansible Collection - fruafr.dnf

Ansible collection for common dnf package activities.

It provides a wrapper around ansible.builtin.dnf and some direct dnf calls.

The target is Red Hat family systems.

Should work on the following distributions and major versions:

| **Distribution** | **7** | **8** | **9** |
|---|---|---|---|
| **Red Hat Enterprise Linux (RHEL)** | Y (no EPEL next release) | Y | Y |
| Oracle Linux (OL) | Y (no EPEL next release) | Y | Y |
| Rocky Linux | N | Y | Y |
| Almalinux | N | Y | Y |
| CentOS Stream [RHEL upstream] | N | Y | Y |
| CentOS [RHEL Downstream] | Y (no EPEL next release) | ? | N |
| Fedora [RHEL Devel] | ? (v19+) | ? (v28+) | v38+ (v34+) |

Roles
-----
The roles contained in this collection are the following:

**Package level**
- install: Install a single package (dnf install -y package)
- install_latest: Install the latest version of a package
- remove: Remove a package
- update_only: Update only if installed
- upgrade: Upgrade a package

**Distribution level**
- autoremove: Remove unused dependencies (dnf autoremove)
- distro_sync: Upgrade the distribution version (dnf distro-sync)
- upgrade_all: Upgrade all packages

**EPEL**
- install_epel: Install the EPEL repository for your distribution and major version
- install_epel_next_release: Install the EPEL next release repository (used by CentOS stream)

**Repositories**:
- add_repo_by_name: Add a repository by its name (assuming you already copied the configuration file to /etc/yumrepos.d)
- disable_repo_by_name: Disable a repository by its name
- enable_repo_by_name: Enable a repository by its name
- install_repo: Install a repository with a rpm package url

License
-------
GNU 3.0 or later


Author Information
------------------
David Heurtevent <david@heurtevent.org>


Note
----
The author is fully aware that the use of Ansible with some imperative calls (similar to Bash) is an anti-pattern.

Changelog
---------
1.0.0 - Initial release (beta)