## Install microk8s (on ubuntu)
More info about microk8s install: https://microk8s.io/docs/getting-started

1. Install microk8s on ubuntu machine

`$ sudo snap install microk8s --classic`

2. Join the group 

`$ sudo usermod -a -G microk8s $USER`

`$ sudo chown -f -R $USER ~/.kube`

3. Reconect to shell

4. Check microk8s status

`$ microk8s status --wait-ready`

5. [Optional] Change `microk8s kubectl` command to `kubectl`

`$ alias kubectl='microk8s kubectl'`

## Install microk8s addons

* Display addons list

`$ microk8s status`

* Enable any addons form that list

`$ microk8s enable  <ADDON_NAME>`

## Start stop microk8s 

Microk8s will automatically restart after a reboot. 

* To start 

`$ microk8s start`

* To stop 

`$ microk8s stop`




