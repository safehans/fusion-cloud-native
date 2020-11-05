Pre-conditions: This simplified documents assume whole bunch of things to keep installation simple

* MacOS
* Brew installed: /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
* Docker intalled: https://desktop.docker.com/mac/stable/Docker.dmg
* Kubernetes on Docker enabled
* Helm installed:  'brew install kubernetes-helm'
* Kubernets config pointed to local kubernetes cluster: 'kubectl config current-context' should print 'docker-desktop'


* Get the Lucidworks fusion code: 'git clone https://github.com/lucidworks/fusion-cloud-native.git'
* 'cd fusion-cloud-native'
* ./customize_fusion_values.sh -c docker-desktop -n fusion-ns --provider docker --num-solr 1
* helm repo add lucidworks https://charts.lucidworks.com
* ./docker_docker-desktop_fusion-ns_upgrade_fusion.sh
* kubectl port-forward svc/proxy 6764:6764
* Visit http://localhost:6764/admin
