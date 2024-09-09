# Ros2_humble_documentation

-> CONFIGURANDO O WORKSPACE:

1- Para ter acesso aos comandos do Ros2 é necessário rodar esse comando em LINUX:

--> source /opt/ros/humble/setup.bash

OBS: Caso você sempre queira iniciar o seu workspace pronto, esse é o comando: 

--> echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc

2- Para confirmar se as variáveis estão configuradas de forma certa, o comando é este a seguir:

--> printenv | grep -i ROS

OBS: O print que aparece no terminal deve conter essas informações:

ROS_VERSION=2

ROS_PYTHON_VERSION=3

ROS_DISTRO=humble

3- Defina seu ID de domínio dentro do ROS2. (O número usado para o ROS_DOMAIN_ID não tem impacto direto no desempenho ou na funcionalidade interna do ROS 2, mas ele serve para diferenciar grupos de nós ROS 2 na mesma rede.)

--> echo "export ROS_DOMAIN_ID=<your_domain_id>" >> ~/.bashrc

--> exemplo: echo "export ROS_DOMAIN_ID=10" >> ~/.bashrc (se caso o ID escolhido for 10, o comando ficaria assim).

4- Para evitar que outra máquina acesse a sua comunicação com o ROS2, é necessário defiir o acesso apenas para localhost. O comando para isso é:

--> echo "export ROS_LOCALHOST_ONLY=1" >> ~/.bashrc

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

--> COMO FUNCIONAM OS NÓS DO ROS2: (nodes)

1- Para que servem os nós?

--> Os nós dentro do ROS2 executam uma tarefa específica, como por exemplo o controle dos motores do robô.

--> Cada nó pode mandar e receber dados via tópicos, serviços, ações ou paramêtros. (outros componentes do ROS2).

2- Como saber quais nós estão rodando no terminal?

--> ros2 node list

OBS: Com esse comando você sabe que nó está rodando no momento.

3- Como ter informações de um nó?

--> ros2 node info <node_name>

OBS: Isso vai retornar uma lista dos publishers e subscribers que estão rodando no momento.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

--> COMO FUNCIONAM OS TÓPICOS NO ROS2: (topics)

1- O que são os tópicos do ROS2?

--> São os canais de comunicação entre os nós.
--> Os tópicos permitem que os nós publiquem e recebam informações. 

2- Como saber que tópicos estão rodando no terminal?

--> ros2 topic list

OBS: se caso você precise vizualizar o que está sendo publicado utilize:

--> ros2 topic echo <topic_name>

--> ou: ros2 topic info <topic_name>

3- Para publicar direto em um tópico, usar esse comando:

--> ros2 topic pub <topic_name> <msg_type> '<args>'

4- Para saber a taxa de publicação dentro de um tópico, usar esse comando:

--> ros2 topic hz

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

--> COMO FUNCIONAM OS SERVIÇOS EM ROS2: (services)

1- Para que os serviços são utilizados?

--> Para uma comunicação sincrona entre os nós que permite ter um feedback imediato para iniciar ou finalizar algum processo.

2- Para listar os serviços em ação no momento:

--> ros2 service list

3- Para saber o tipo do serviço:

--> ros2 service type <service_name>

4- Para achar um serviço específico:

--> ros2 service find <type_name>

5- Para ativar uma interface:

--> ros2 interface show <type_name>
