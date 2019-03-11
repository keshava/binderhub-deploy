# binderhub-deploy

A set of shell scripts to automatically deploy a [BinderHub](https://binderhub.readthedocs.io/en/latest/index.html) onto [Microsoft Azure](https://azure.microsoft.com/en-gb/).

**List of scripts:**
* [**./setup.sh**](#setup)
* [./deploy.sh](#deploy)

---

<a name="setup"></a>
### ./setup.sh

This script uses [`curl`](https://curl.haxx.se/docs/) to install command line interfaces (CLIs) for Microsoft Azure (`azure-cli`), Kubernetes (`kubectl`) and Helm (`helm`).

Command line install scripts were found in the following documentation:
* [Azure-CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-linux?view=azure-cli-latest#install-or-update)
* [Kubernetes-CLI](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-binary-using-curl) (macOS version)
* [Helm-CLI](https://helm.sh/docs/using_helm/#from-script)

<a name="deploy"></a>
### ./deploy.sh

This script automatically generates a `config.yaml` file and a `secret.yaml` file then installs and deploys both a JupyterHub and BinderHub.
This file requires a `JSON` file containing a password for a DockerHub account.
If no file is provided, it will automatically look for `~/.secret/BinderHub.json`.
