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
(oprint) $ octoprint dev plugin:new helloworld
Cloning into 'cookiecutter-octoprint-plugin'...
remote: Counting objects: 101, done.
remote: Total 101 (delta 0), reused 0 (delta 0), pack-reused 101
Receiving objects: 100% (101/101), 53.69 KiB, done.
Resolving deltas: 100% (35/35), done.
plugin_package [octoprint_helloworld]:
plugin_name [OctoPrint-Helloworld]:
repo_name [OctoPrint-Helloworld]:
full_name [You]: Your Name
email [you@example.com]: you@somewhere.net
github_username [you]: yourGithubName
plugin_version [0.1.0]: 1.0.0
plugin_description [TODO]: A quick "Hello World" example plugin for OCtoPrint
plugin_license [AGPLv3]:
plugin_homepage [https://github.com/yourGithubName/OctoPrint-Helloworld]:
plugin_source [https://github.com/yourGithubName/OctoPrint-Helloworld]:
plugin_installurl [https://github.com/yourGithubName/OctoPrint-Helloworld/archive/master.zip]:
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
