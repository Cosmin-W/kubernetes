# Table of Contents
1. [Install microk8s (on ubuntu)](#install_microk8s)
2. [Install microk8s addons](#microk8s_addon)
3. [Start stop microk8s service](#microk8s_start_stop)
4. [Cluster setup](#microk8s_cluster)


## 1. Install microk8s (on ubuntu) <a name="install_microk8s"></a>

 
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

6. [Optional] Enable microk8s addons that you will problebly need

   `$ microk8s enable dns dashboard ingress`
  

## 2. Install microk8s addons <a name="microk8s_addon"></a>

* Display addons list

   `$ microk8s status`

* Enable any addons form that list

   `$ microk8s enable  <ADDON_NAME>`

## 3. Start stop microk8s service  <a name='microk8s_start_stop'></a>

Microk8s will automatically restart after a reboot. 

* To start 

   `$ microk8s start`

* To stop 

   `$ microk8s stop`

## 4. Cluster setup <a name='microk8s_cluster'></a>

1. Install microk8s on all the nodes as shown above
2. On the node that you want to be the `Master Node` run  the following command

   `$ microk8s add-node`

It will print a joining key. 

4. Run the key command in an worker node terminal
5. To add more more workers repeat from step 2 for each worker node
6. To remove node from cluster
  - run `microk8s leave` on the departing node
    `$ microk8s leave`
    
  - To complete the node removal, call `microk8s remove-node` from the remaining nodes to indicate that the departing.
    `$ microk8s remove-node 10.22.254.79`




