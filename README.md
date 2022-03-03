joplin
======

This role sets up joplin desktop, cli and a number of plugins on the host.

Requirements
------------

For installing the CLI client, a local working NPM installation must be available.

Role Variables
--------------

For a list of role variables, please see `defaults/main.yml`.

Configuration settings
----------------------


Supported Joplin plugins
------------------------

The followin Joplin plugins are supported and can be installed by setting the plugin variable for the role.

Plugin | Plugin name
--- | ---
Autoamtic backlinks to Note | automatic_backlinks_to_note
Insert Date | insert_date
Link Graph UI | link_graph_ui
Make all links| make_all_links
Markdown Table formatter | table_formatter
Markdown Table sortable| markdown_table_sortable
Note Tabs | note_tabs
Note Variables | notevariables
Outline | outline
Templates | templates

Example
"""""""

```yaml
---
joplin_plugins:
  - notevariables
  - automatic_backlinks_to_note
```

Dependencies
------------

This roles requires the role `appimage` in order to be able to install the appimage for the joplin desktop application.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  roles:
     - { role: username.rolename, x: 42 }
```

License
-------

BSD

TODO
----

* The synchronisation intervalls are limited to 5,10,30,60,12h,24h. Add a requirements file to verify this setting, otherwise joplin sets it to 'disabled'

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
