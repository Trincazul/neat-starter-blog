---
title: Fundamentos sobre Kubernetes e Minikube
description: Kubernetes é um sistema de gerenciamento de contêineres de código
  aberto que foi projetado para automatizar o deploy, o escalonamento e a
  administração de aplicativos em contêineres em larga escala
author: Endriw Villa
date: 2022-12-19T12:15:52.694Z
tags:
  - Tags
---
**Kubernetes** é um sistema de gerenciamento de contêineres de código aberto que foi projetado para automatizar o deploy, o escalonamento e a administração de aplicativos em contêineres em larga escala. Ele foi desenvolvido pelo Google e tornou-se um projeto do Cloud Native Computing Foundation. Kubernetes permite que você execute vários contêineres em uma rede de máquinas e gerencie esses contêineres de maneira eficiente, o que facilita criar e executar aplicativos em contêineres em ambientes distribuídos.

Kubernetes é utilizado principalmente para gerenciar aplicativos em contêineres em larga escala. Ele permite que você facilmente despeje e atualize aplicativos em contêineres em ambientes distribuídos, escalando automaticamente o número de contêineres em execução conforme as necessidades de carga mudam. Isso facilita criar e executar aplicativos de alta disponibilidade e alta escalabilidade. Kubernetes também fornece recursos para monitorar e diagnosticar aplicativos em execução, ajudando a garantir que eles estejam sempre executando corretamente.

## Como começar a utilizar o Kubernetes ?

Para começar a usar o Kubernetes, você precisará ter uma rede de máquinas onde o Kubernetes possa ser executado. Isso pode ser um cluster de máquinas físicas ou um cluster de máquinas virtuais em uma nuvem. Você também precisará instalar o software Kubernetes em cada máquina do cluster. Depois disso, você poderá começar a criar e implantar aplicativos em contêineres no cluster usando os comandos e ferramentas do Kubernetes. Existem vários tutoriais e guias disponíveis online que podem ajudá-lo a começar a usar o Kubernetes. É recomendável começar com exemplos simples e, em seguida, expandir suas habilidades a medida que for adquirindo mais conhecimento e experiência.

## Comandos básicos do Kubernetes

Existem muitos comandos diferentes disponíveis no Kubernetes, mas aqui estão alguns comandos básicos que você pode encontrar úteis:

`kubectl get`: Este comando exibe informações sobre os recursos do Kubernetes em execução, como pods, serviços e configurações de implantação. Por exemplo, você pode usar kubectl get pods para ver uma lista de todos os pods em execução no cluster.

`kubectl describe` : Este comando fornece informações detalhadas sobre um recurso do Kubernetes específico. Por exemplo, você pode usar kubectl describe pod <nome-do-pod> para ver detalhes sobre um pod específico, como sua configuração e seu histórico de estados.

`kubectl create`: Este comando cria um novo recurso do Kubernetes. Por exemplo, você pode usar **kubectl create deployment <nome-do-deployment>** para criar um novo deployment.

`kubectl delete`: Este comando exclui um recurso do Kubernetes. Por exemplo, você pode usar kubectl delete deployment <nome-do-deployment> para excluir um deployment.

`kubectl logs`: Este comando exibe os logs de um pod específico. Isso pode ser útil para diagnosticar problemas com um aplicativo em execução. Por exemplo, você pode usar `kubectl logs <nome-do-pod>` para ver os logs de um pod.

Esses são apenas alguns exemplos de comandos básicos do Kubernetes. Existem muitos outros comandos disponíveis, cada um com suas próprias funcionalidades e usos.

## Resumo sobre o minikube

O Minikube é uma ferramenta que facilita a execução do Kubernetes localmente em sua máquina. Ele permite que você crie e gerencie um cluster Kubernetes com apenas um nó em sua máquina local, o que é útil para desenvolvimento e testes. Dessa forma, você pode experimentar as funcionalidades do Kubernetes sem precisar de um cluster real. O Minikube também inclui várias ferramentas de desenvolvimento que tornam mais fácil criar e implantar aplicativos em contêineres no seu cluster local. É uma ferramenta popular entre desenvolvedores que estão aprendendo o Kubernetes ou precisam de um ambiente de desenvolvimento local para testar aplicativos em contêineres.

## Como iniciar com o minikube ?

Para começar a usar o Minikube, você primeiro precisará instalá-lo em sua máquina. Isso pode ser feito usando o gerenciador de pacotes do seu sistema operacional, como o apt-get no Ubuntu ou o brew no macOS. Depois de instalar o Minikube, você pode usar o comando `minikube start` para iniciar um cluster local com um nó. Isso pode levar algum tempo, dependendo de sua configuração de máquina. Depois de iniciar o cluster, você pode usar o comando `kubectl` para gerenciar o cluster e implantar aplicativos em contêineres nele. É recomendável consultar a documentação do Minikube para obter mais informações sobre como usá-lo e aprender mais sobre suas funcionalidades.

## Comandos basicos do minikube

Aqui estão alguns comandos básicos que você pode encontrar úteis ao usar o **Minikube**:

`minikube start`: Este comando inicia um cluster local do Kubernetes com um único nó. Ele cria um ambiente virtual no qual o Kubernetes pode ser executado e configura o kubectl para se comunicar com o cluster.

`minikube stop`: Este comando para o cluster local do Kubernetes. Isso é útil quando você deseja desligar o cluster quando não estiver usando-o.

`minikube dashboard`: Este comando abre o dashboard do Kubernetes no navegador da Web. O dashboard fornece uma interface visual para gerenciar o cluster e os aplicativos nele implantados.

`minikube addons`: Este comando exibe uma lista de addons do Minikube que podem ser ativados ou desativados. Addons são recursos adicionais que podem ser adicionados ao cluster local do Kubernetes para fornecer funcionalidades adicionais, como o heapster para monitoramento e o ingress para gerenciamento de tráfego de entrada.

`minikube delete`: Este comando exclui o cluster local do Kubernetes. Isso é útil se você deseja limpar o cluster e recriá-lo do zero.

Esses são apenas alguns exemplos de comandos básicos do **Minikube**.

## Conclusão sobre o **kubernetes** e **minikube**

**Kubernetes** é um sistema de gerenciamento de contêineres de código aberto que foi projetado para automatizar o deploy, o escalonamento e a administração de aplicativos em contêineres em larga escala. Ele é amplamente utilizado em ambientes de produção para gerenciar aplicativos em contêineres de maneira eficiente e confiável.

O **Minikube** é uma ferramenta que facilita a execução do Kubernetes localmente em sua máquina. Ele permite que você crie e gerencie um cluster Kubernetes com apenas um nó em sua máquina local, sendo útil para desenvolvimento e testes. Dessa forma, você pode experimentar as funcionalidades do Kubernetes sem precisar de um cluster real.

Ambos são ferramentas úteis para quem trabalha com aplicativos em contêineres e deseja gerenciá-los de maneira eficiente em larga escala. É recomendável consultar a documentação dessas ferramentas para aprender mais sobre suas funcionalidades e como usá-las de maneira eficiente.

## Siginificado de pod em kubernetes

No Kubernetes, um pod é a unidade básica de execução de um aplicativo. É composto por um ou mais contêineres que compartilham o mesmo espaço de endereçamento e recursos do sistema operacional, como rede e armazenamento. Os contêineres em um pod são geralmente aplicativos que fazem parte da mesma lógica de negócios ou que precisam compartilhar os mesmos recursos. Isso permite que os contêineres em um pod comuniquem entre si como se estivessem em uma única máquina virtual, em vez de em máquinas virtuais separadas.

## Significado de containers em kubernetes 

Em Kubernetes, um container é uma unidade de empacotamento de software que inclui o código do aplicativo, suas dependências e as configurações do runtime, tudo empacotado em um formato que pode ser executado em qualquer ambiente de nuvem ou em qualquer máquina que tenha o runtime de containers adequado. Isso permite que os aplicativos sejam executados de forma consistente e confiável em qualquer lugar, independentemente do sistema operacional subjacente. Os containers são uma das principais tecnologias que o Kubernetes gerencia e orquestra.

## Significado de cluster em kubernetes 

Em Kubernetes, um cluster é um conjunto de máquinas virtuais ou físicas trabalhando em conjunto para executar aplicativos em containers. Essas máquinas são geralmente chamadas de nós, e cada uma pode executar um ou mais pods, que são grupos de containers que compartilham recursos do sistema operacional. O Kubernetes gerencia e orquestra os containers em um cluster, permitindo que os aplicativos sejam escalados horizontalmente, monitorados e mantidos de forma automatizada. Isso facilita a implantação e o gerenciamento de aplicativos em larga escala em ambientes de nuvem.

## Significado de nós em Kubernetes

Em Kubernetes, um nó é uma máquina virtual ou física que faz parte de um cluster e que executa os pods, grupos de containers que compartilham recursos do sistema operacional. Cada nó tem um agente do Kubernetes, chamado kubelet, responsável por gerenciar os pods e os containers em seu nó. O kubelet também se comunica com o controlador do Kubernetes, responsável por orquestrar os pods em todo o cluster segundo as políticas de implantação e escalonamento definidas pelo usuário. Isso permite que os aplicativos sejam executados de forma consistente e confiável em todo o cluster.