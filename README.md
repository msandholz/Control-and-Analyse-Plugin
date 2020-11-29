# Control-and-Analyse-Plugin
An OctoPi plugin to analyse and control the 3D-printer.


## Setup the developing environment on octopi

1. In case of developing your plugin directly on your Raspberry Pi running OctoPi, you’ll only need to activate the oprint virtual environment:
```
$ source ~/oprint/bin/activate
(oprint) $ octoprint --help
Usage: octoprint [OPTIONS] COMMAND [ARGS]...

[...]
```

2. The cookiecutter template for OctoPrint plugins is used here. This should already be installed if you used the plugins extra while installing OctoPrint. However, you may install it with:
```
(oprint) $ pip install "cookiecutter>=1.4,<1.7"
```

3. Then we can use the ´octoprint dev plugin:new´ command to generate a new OctoPrint plugin skeleton for us:
```
(oprint) $ octoprint dev plugin:new CoAn_Plugin
plugin_package [octoprint_CoAn_Plugin]: octoprint_CoAn_Plugin
plugin_name [OctoPrint-CoAn_Plugin]: OctoPrint_CoAn_Plugin
repo_name [OctoPrint-CoAn_Plugin]: OctoPrint-CoAn_Plugin
full_name [You]: Markus Sandholz
email [you@example.com]: markus.sandholz@t-online.de
github_username [you]: msandholz
plugin_version [0.1.0]: 0.1.0
plugin_description [TODO]: An OctoPi plugin to analyse and control the 3D-printer. 
plugin_license [AGPLv3]: AGPLv3
plugin_homepage [https://github.com/msandholz/Control-and-Analyse-Plugin]: https://github.com/msandholz/Control-and-Analyse-Plugin
plugin_source [https://github.com/msandholz/Control-and-Analyse-Plugin]: https://github.com/msandholz/Control-and-Analyse-Plugin
plugin_installurl [https://github.com/msandholz/Control-and-Analyse-Plugind/archive/master.zip]: https://github.com/msandholz/Control-and-Analyse-Plugind/archive/master.zip
(oprint) $ cd OctoPrint_CoAn_Plugin
```

4. This will create a project structure in the `OctoPrint-CoAn_Plugin` folder we just changed to that looks like this:
```
translations/
    README.txt
octoprint_CoAn_Plugin/
    static/
        css/
            CoAn_Plugin.css
        js/
            CoAn_Plugin.js
        less/
            CoAn_Plugin.less
    templates/
        README.txt
    __init__.py
extras/
    README.txt
    CoAn_Plugin.md
.editorconfig
.gitignore
babel.cfg
MANIFEST.in
README.md
requirements.txt
setup.cfg
setup.py
```

5. Insert some code in __init__.py
```
# coding=utf-8
from __future__ import absolute_import

import octoprint.plugin

class Coan_Plugin(octoprint.plugin.StartupPlugin):

	def on_after_startup(self):
		self._logger.info("Control and Analyse Plugin started!")

__plugin_name__ = "Coan_Plugin"
__plugin_version__= "0.1.0"
__plugin_description__ = "An OctoPi Plugin to control and analyse the 3D-printer"
__plugin_pythoncompat__ = ">=2.7,<4"
__plugin_implementation__ = Coan_Plugin()

```

6. Installing the Plugin

The plugin is now ready to be installed via `python setup.py install`. If we are under development it is better to use `python setup.py develop`. Then we don’t have to reinstall it after any changes we will still do. 
We can have the `octoprint dev plugin:install` command do everything for us here, it will ensure to use the python binary belonging to your OctoPrint installation:

```
(oprint) ~/OctoPrint-CoAn_Plugin $ octoprint dev plugin:install
```

7. Restart OctoPi and watch log-file
```
$ less +F ~/.octoprint/logs/octoprint.log

...
2020-11-29 12:01:35,118 - octoprint.plugins.CoAn_Plugin - INFO - Control and Analyse Plugin started!
...

```



