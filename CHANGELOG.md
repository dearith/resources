<a name="unreleased"></a>
## [Unreleased]

### Feat
- add 0.5 support for mergify
- add a cookiecutter template
- add a new fnmatch extension and use it for docker-mfxxx-yyy-buildimage_drone.yml
- add exact-level option
- add first drone support
- add metwork_repos.py script
- add mfcom support
- add rename support
- better README
- first version of contributing guide
- generate .drone.yml and run_tests.sh from resource for repositories mf*-integration-tests-runner
- generate README.md file for integration_level >= 5
- introduce mfextaddon
- new templates to execute integration tests directly from modules
- optional auth

### Fix
- directory integration_tests may no exist
- fix bad space
- fix latest commit
- fix renaming feature in subdir
- fix utf8 char
- fix utf8 issues
- publish addons in /pub
- remove doc publish for mfext addons
- some fixes about mfext addon drone conf
- tag condition
- yum install {{MODULE}} before call to {{MODULE}}_wrapper

