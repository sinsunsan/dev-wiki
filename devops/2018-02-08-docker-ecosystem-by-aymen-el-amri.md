---
layout: post
title: 'L''écosystème Docker par Aymen El Amri [Meetups]'
published: true
---

# Docker by aymen el amri

![l&apos;&#xE9;cosyst&#xE8;me Docker / pr&#xE9;sentation de Aymen Amri](https://github.com/sinsunsan/dev-wiki/tree/e91a89337cb472fad5198a7110a0eaa8d63d66f5/images/docker-aymen-amri.jpg)

Meetup sur docker dans les locaux de [Comet](https://www.hellocomet.co). Comet, une startup qui aide les freelances à se connecter à des missions pour des grands groupes, organisent régulièrement des [meetups](https://www.meetup.com/fr-FR/Comet-Meetups-for-Freelancers/) ciblant les développeurs.

Ce soir Aymen, un développeur / depOps connu pour sa connaissance de Docker nous présentent le système de container, Docker et son écosystème.

### Résumé

Aymen nous fait un panorama de systèmes de containers avant Docker depuis les années 80. Puis il nous détaille la mise à l'échelle impressionnante de la communauté open source vite rejoint par les géants du Web comme Google, Amazon...

Enfin il passe en revue des outils de la communauté, qui sont intéressants de tester. Et replace en perspective l'importance de l'orchestration et de Kubernetes devenu presque aussi important que le conteneur lui-même.

Par [Aymen El Amri](http://aymenelamri.com) CEO de eralabs.io / Dev ops Services Twitter [@eon01](https://twitter.com/eon01) Github [@eon01](https://github.com/eon01) Fait parti de la De la communauté de [http://devopslinks.com](http://devopslinks.com)

## Les containeurs existent depuis les années 1980

Docker n'est pas le premier système de conteneurs. Chroot jail le premier système basé sur les conteneurs date de 1979 !

* **Chroot Jail**
* **CGroups**
* **LXC** : Linux container
* **LMCTFY** by Google "Let Me Contain That for You" tourne sur des conteneurs chez Google.
* **Docker** en 2013 : le plus populaire jusqu'à maintenant car plus developer friendly. Plus simple à configurer
* **RKT Rocket** : plus sécurisé et standardisé 

![docker popularity exponential growth](https://github.com/sinsunsan/dev-wiki/tree/e91a89337cb472fad5198a7110a0eaa8d63d66f5/images/docker-hub-pulls.jpg)

## Mais qu'est ce qui fait la force de Docker

Docker permet à des développeurs de manipuler des ressources de Dev ops, sans la complexité.

**Containers vs VMs \(Virtual Machines\)** :

![Containers vs Virtual Machines](https://github.com/sinsunsan/dev-wiki/tree/e91a89337cb472fad5198a7110a0eaa8d63d66f5/images/docker-containers-vs-virtual-machine.jpg)

Docker est beaucoup plus léger car il ne comprend pas l'OS.

### Architecture de Docker

* **Docker entreprise Edition**
* **Docker community Edition**
* **Swarm** : Orchestration 
* **containerd** : Container Runtime

### Docker tools

* **Docker engine**: Le process docker principal
* **Docker compose**: On veut installer LAMP, on créait 3 conteneurs, pour PHP, MYSQL et PHP Docker compose permet de lier les 3 conteneurs qui définisent ces trois conteneurs
* **Docker Machine**: Permet de créer des machines virtuelles auto-executable, générer des images sur Amazon...

### Evolution de Docker

* **LXC** : A la base Docker se basait sur LXC, une technologie de conteneurs 
* **LibContainer** : Puis ils ont développé leur propre système de conteneurs libcontainer. Permet d'accéder aux linux facilities... qui touchent à l'isolation et à la securité.
* **RunC** : En 2015, développement de RunC, le developpement est open source, mais soutenu par des grands groupes, Google... Abstraction entre la communication entre le conteneur et un runtime
* **ContainerD** : en 2016 permet de faire de la supervision des processus 
* Passage d'une architecture monolytique à une architecture par composants
* 2017, les containeurs sont devenus mainstream, Google cloud, Amazon, Aws ...
* **Moby project** : permet de modulariser le développement de Docker.

### Les composants de MOBY

* **ContainerD** : gère le cycle de vie
* **LinuxKit** : permet de créer des distributions linux à partir d'un fichier yaml Permet de créer des machines virtuelles pour des clouds publics comme celui d'Amazon
* **InfraKit** : Déclaratif desired state, on ne décrit pas les actions, mais l'état que l'on veut attendre
* **SwarmKit** : Orchestrer des systèmes distribués

### L'importance de l'orchestration

**Swarm vs Kubernetes.**

![Swarn vs Kubernetes](https://github.com/sinsunsan/dev-wiki/tree/e91a89337cb472fad5198a7110a0eaa8d63d66f5/images/docker-swarn-vs-kubernetes.png)

Kubernetes est inclu nativement comme Swarm on peut choisir son orchestration. Indispensable pour mettre en production.

* [**Docker Swarm**](https://github.com/docker/swarm): simple à utiliser et inclu dans Docker. Bien pour commencer
* [**Kubernetes**](https://github.com/kubernetes/kubernetes): Plus complexe mais leader du marché de l'orchestration. Utilisé par Github, Wikimedia...
* **Mesos**: Utilisé par Netflix, Twitter...

Les services cloud sont en compétition pour offrir une implémentation de Kubernetes la plus aisée possible.

**Service cloud kubernetes :**

* GKE de google
* Amazon ECS \(la version amazon\) et EKS \(Kubernetes\) / Azure ACS 
* Cloud alibaba 
* Cloud Redhat

### Les questions

* **Quel est le meilleur site pour commencer ?**

Le site de docker est bien pour commencer, Docker Academy... jusqu'à Swarm. Pour Kubernetes, il faut passer à autre chose.

* **Je ne suis pas devops mais dev, j'utilise docker compose en prod. Est ce que Swarm est utilisable en prod ?**

Pour une application très simple avec une API en node js et le front sur Angular. Le Docker swarm permet de faire un cluster avec le front et le back. Et donc Swarn suffit pour des architectures simples. Kubernetes est recommmandé pour aller plus loin.

* **Est ce que Docker Swarm a un réel overhead sur les perfs par rapport à une install native**

Un container par machine virtuelle sans orchestration c'est du gaspillage. Avec de l'orchestration, on peut mettre beaucoups de conteneurs sur la même machine. Ils peuvent communiquer à travers un reseau interne, ou si si plusieurs machines, récréer un lien virtuel entre tout ces conteneurs sur plusieurs machines.

* **As-tu testé Traefik ?**

[Traefik](https://github.com/containous/traefik) permet de gérer des micro-services. Les micro-services sont moins en vogue et rejoignent les conteneurs, car ils partagent les mêmes concepts, la découverte...

![Traefik micro-services + Docker](https://github.com/sinsunsan/dev-wiki/tree/e91a89337cb472fad5198a7110a0eaa8d63d66f5/images/docker-traefik-architecture.png)

* **Le futur du conteneur ?**: 

Stateless et Serverless !

* **La base de donnée dans un conteneur ?**

Pas le plus simple, et pas dans la logique stateless. Plus simple d'avoir une base de donnée dans le cloud, le faire avec des conteneurs moins simple. Une intervention d'un développeur: la base de donnée peut être mis dans un container, mais la data elle-même est mis sur le host du container. L'avantage de mettre la base de donnée dans un containeur permet de mettre à jour la version de base de donnée, très simplement....

