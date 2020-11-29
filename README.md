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

3. Then we can use the octoprint dev ´plugin:new´ command to generate a new OctoPrint plugin skeleton for us:
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
plugin_homepage [https://github.com/msandholz/Control-and-Analyse-Plugin]:
plugin_source [https://github.com/msandholz/Control-and-Analyse-Plugin]:
plugin_installurl [https://github.com/msandholz/Control-and-Analyse-Plugind/archive/master.zip]:
(oprint) $ cd OctoPrint-HelloWorld
```



4. This will create a project structure in the OctoPrint-HelloWorld folder we just changed to that looks like this:
```
extras/
    README.txt
    helloworld.md
octoprint_helloworld/
    static/
        css/
            README.txt
        js/
            README.txt
        less/
            README.txt
    templates/
        README.txt
    __init__.py
translations/
    README.txt
.editorconfig
.gitignore
babel.cfg
MANIFEST.in
README.md
requirements.txt
setup.py
```

5. While we’ll need some of those folders later on, we’ll now delete everything that we don’t need right now first, that will make it easier to understand what folder does what later on. Delete the following folders and anything in them:

```
extras
translations
octoprint_helloworld/static
octoprint_helloworld/templates
The final project structure should look like this for now:
```
