# joplin

This role sets up joplin desktop, cli and a number of plugins on the host.

## Requirements

For installing the CLI client, a local working NPM installation must be available.

## Role Variables

```yaml
joplin_client_desktop: bool
```

* If set to true, this option will install the joplin desktop client on the host.

```yaml
joplin_desktop_config_settings: dict
```

* Default Changes to the configuration List of configuration settings for Joplin Desktop.

```yaml
joplin_install_tools: bool
```

* If set to true this parameter till install additional tools for joplin onto the host system.

```yaml
joplin_plugins: list
```

* List of plugins to install for Joplin Desktop.

## Other variables

```yaml
joplin_client_cli_package: str
```

* Sets the name of the joplin client package to use.

```yaml
joplin_client_desktop_appimage_url: str
```

* Sets the default appimage url for joplin desktop to install via appimage.

```yaml
joplin_desktop_path_config_file: str
```

* Sets the path to the joplin desktop configuration file.

```yaml
joplin_dir_user_config: str
```

* Sets the path to the user configuration directory for joplin.

```yaml
joplin_plugins_data: dict
```

* Joplin plugin data for reference use in `joplin_plugins`.

```yaml
joplin_user: str
```

* Sets the username of the user that shall use joplin.

## Configuration settings

Set configuration settings by defining them in `joplin_desktop_config_settings`.

```yaml
---
joplin_desktop_config_settings:
  locale: en_US
  spellchecker.languate: en-US
  trackLocation: 'false'
```

## Supported Joplin plugins

The followin Joplin plugins are supported and can be installed by setting the plugin variable for the role.

Plugin | Plugin name
--- | ---
Autoamtic backlinks to Note | automatic_backlinks_to_note
Autolinker | autolinker
Insert Date | insert_date
Link Graph UI | link_graph_ui
Make all links| make_all_links
Markdown Table formatter | table_formatter
Markdown Table sortable| markdown_table_sortable
Note Tabs | note_tabs
Note Variables | notevariables
Outline | outline
Templates | templates

### Example

```yaml
---
joplin_plugins:
  - notevariables
  - automatic_backlinks_to_note
```

## Dependencies

This roles requires the role `appimage` in order to be able to install the appimage for the joplin desktop application.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  roles:
     - { role: username.rolename, x: 42 }
```

## License

MIT

## TODO

* The synchronisation intervalls are limited to 5,10,30,60,12h,24h. Add a requirements file to verify this setting, otherwise joplin sets it to 'disabled'

## Author Information

This Ansible role is maintained by DBV.
