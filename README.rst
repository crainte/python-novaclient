Key Differences & New Features   
==================================================

New
---
- Integrated os_networksv2_python_novaclient_ext
- ``resize`` has gained a new flag, ``--disk-config <auto|manual>`` to allow you to change between the two configurations.
- ``compute-list`` lists all instances that a specific compute host manages.
- ``tenant-servers`` uses the os-simple-tenant-usage extension to view full lists of servers for a tenant.
- The new flag ``--display`` will allow you to instruct novaclient which columns to return in the following functions:

  - list
  - compute-list
  - tenant-servers

- ``boot`` has gained the flags ``--no-nic`` and ``--disk-config <auto|manual>``
- More to come.

Fixes/Changes
------
- Fully supports UTF-8 printing.
- Corrected default Nics on ``boot`` eliminating the need for rax_default_network_flags_python_novaclient_ext.
- All printing is width limited to prevent terminal vomit.
- Removed multiple delete functionality.
- Quota commands to not require ``--tenant`` to be specified.
- ``reset-state`` sets to Active by default. It has gained a new flag as well: ``--error``
- All deletes prompt for approval but have a hidden ``--force`` for scripting::

   You are about to perform a harmful action. Are you certain? [YES]:

- ``nova show`` has been cleaned up to collect networking in one location::

    | name                   | Servername                                                 |
    | networks               |                                                            |
    |                        | public   = 50.50.50.50                                     |
    |                        | public   = 2001:2001:2001:2001:2001:2001:2001:2001         |
    |                        | private  = 10.10.10.10                                     |
    |                        |                                                            |
    | progress               | 100                                                        |

- Bandwidth has been moved from a default option of ``nova show`` to a flag ``--bandwidth`` as well as gained sorting.
- More to come.
