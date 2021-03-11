## Requirements

* docker
* yq (v4)
* curl

## How to use this

1. Clone this repo. Open `runs.sh` and edit any of the initial values as needed.
2. Run `./run.sh /path/to/your/plugins.yaml 2>/dev/null` (defaults to a `plugin.yaml` file in the pwd)
3. The stdout will be what you need to use for the `plugin-catalog.yaml` in the bundle.

## Notes

* This process caches all resources that it fetches (list below). 
  * `jenkins.war` from the docker image
  * `jenkins-plugin-manager.jar` download from github releases
  * `update-center.json` is cached from the UC download (this can reduce network traffic and delay if wanting to run this subseqently against multiple different `plugins.yaml`s.

* Remove the stderr redirection if you need to see the caching notifications.