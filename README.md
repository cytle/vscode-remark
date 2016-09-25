# vscode-remark

> Beautify markdown code with Remark.

![vscode-remark](https://cloud.githubusercontent.com/assets/7034281/18815111/44d2ffb2-832f-11e6-81dc-e3f62cfa06dc.gif)

## Install

  * Press `F1` and select `Extensions: Install Extensions`.
  * Search for and select `remark`.

See the [extension installation guide](https://code.visualstudio.com/docs/editor/extension-gallery) for details.

## Usage

Press `F1` and run the command named `Remark: Beautify markdown code`.

## Supported languages

  * Markdown

## Supported settings

**remark.format**

  * Type: `Object`
  * Default: `{}`

Plugin configuration.

**remark.format.plugins**

  * Type: `Array`
  * Default: `[]`
  * Example: `["github", "first-heading"]`

A list globally or locally installed plugins that will be used with Remark (without `remark-` prefix).

See [remark/plugins](https://github.com/wooorm/remark/blob/master/doc/plugins.md).

> **About first run with this option**

> When you first run the plugin is looking for an installed plugins. Therefore, the first run may take a long time. Subsequent runs are much faster.

**remark.format.rules**

  * Type: `Object`
  * Default: `{}`
  * Example: `{ "closeAtx": true }`

Remark formatter rules.

See [remark/options](https://github.com/wooorm/remark/tree/master/packages/remark-stringify#options) or use intellisense in VS Code:

![2016-09-25_14-47-36](https://cloud.githubusercontent.com/assets/7034281/18815102/09cc2394-832f-11e6-8b36-639405e4bcb0.gif)

**remark.format.plugin-name-without-prefix**

  * Type: `Object`
  * Default: `null`
  * Example: `"github": { "repository": "https://github.com/mmrlnc/vscode-remark" }`

Configurations for plugins, if they are needed.

## About error handling

Unfortunately, some plugins do not give correct errors. So when you see the following error (see image), then most likely a bug in the wrong settings of any of the plugins.

```json
{
	"remark.format": {
		"plugins": [
			"first-heading"
		],
		"first-heading": {
			"heading": 123
		}
	}
}
```

![image](https://cloud.githubusercontent.com/assets/7034281/18815133/de2f477e-832f-11e6-83cd-55b894d0e4a4.png)

Many plugins correctly give an error. For example:

```json
{
	"remark.format": {
		"plugins": [
			"github"
		]
	}
}
```

![image](https://cloud.githubusercontent.com/assets/7034281/18815141/1c2c81a4-8330-11e6-8b32-69417b24196b.png)

Therefore, if you are experiencing problems with this extension, please create issue on GitHub repository.

> **Tip**
>
> You can see a detailed error report in the Developer Tools (`Help -> Toggle Developer Tools`). Please do not forget to attach it to your issue.

## Keyboard shortcuts

For changes keyboard shortcuts, create a new rule in `File -> Preferences -> Keyboard Shortcuts`:

```json
{
  "key": "ctrl+shift+c",
  "command": "remark.reformat"
}
```

## Changelog

See the [Releases section of our GitHub project](https://github.com/mrmlnc/vscode-remark/releases) for changelogs for each release version.

## License

This software is released under the terms of the MIT license.