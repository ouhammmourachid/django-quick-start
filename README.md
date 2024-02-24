## Django Quick start

this is s open source template that is pre-configured and ready to work with in Django
* [version-1.0.x](#get-started-with-version-1.0.x)
* [version-2.0.x](#get-started-with-version-2.0.x)
* [version-3.0.x](#get-started-with-version-3.0.x)
* [version-4.0.x](#get-started-with-version-4.0.x)

## Versions
#### get started with `version-1.0.x`:

1. clone the repo and checkout to the `version-1.0.x` branch.

```bash
git clone https://github.com/ouhammmourachid/django-quick-start.git
git checkout version-1.0.x
```

2. run the initial app.

```bash
make migrations
make migrate
make superuser
make run-server
```

and then access the app on [local host](http://127.0.0.1:8000/)

3. create your app like this.

delete the `welcome` app (optional) `rm -rf core/welcome`.

remove the app from the list of installed apps on `core/project/settings.py`

```python
...
INSTALLED_APPS = [
    ...
    # 'core.welcome.apps.WelcomeConfig',
]
...
```
make a new app using this command.

```bash
make app name=AppName
cp AppName core/
```
change the app configuration in the `core/AppName/apps.py`
```python
...
class AppNameConfig(AppConfig):
    ...
    name = 'core.AppName'
...
```
and make sure to add the configuration to the installed apps list in the `core/project/settings.py`.

```python
...
INSTALLED_APPS = [
    ...
    'core.AppName.apps.AppNameConfig',
]
...
```

#### get started with `version-2.0.x`:
this versioon support split settings to orgnize the settings in deferent files and make it to integrate local setting.

make the templates for the local settings so you can override the default settings.

```bash
make local-settings
```

an easy way to create app

```bash
make app AppName
```
it also uses the django `v5.0.2`.

#### get started with `version-3.0.x`:

in this version we add support fro pre-commit with flake8 and mypy and additional tools

to install pre-commit hocks use

```bash
make install-pre-commit
```
to make lint operation use this

```bash
make lint
```
for additional configuration you can change this files
`.editorconfig`
`.flake8`
`.pre-commit-config.yaml`
`mypy.ini`


#### get started with `version-4.0.x`:

in this version i add support for `Dockerfile` .
to run the app use

```bash
make build-up
```
to shut it down use

```bash
make down
```

## TODO for version 5.0.x:
- [ ] add git hub actions for lint.
- [ ] add git hub actions for testing.
- [ ] add git hub actions for integrating `codecov`.
- [ ] add git hub actions for deploying the image to a repository. (dockerhub, ghr).
- [ ] add `depandaboot` to update automatiquement update `Pypi` packages.
