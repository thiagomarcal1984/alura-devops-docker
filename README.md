# Hello Docker!
## Entendendo os containers
Diferente de máquinas virtuais, containers não possuem uma camada de hipervisor.

Há diversos namespaces usados para os containers: 
- **PID**: isola processos que rodam no container;
- **NET**: isola as interfaces de rede;
- **IPC**: isola comunicação entre processos e memória compartilhada;
- **MNT**: isola o sistema de arquivos/pontos de montagem;
- **UTS**: isola o kernel, como se o container fosse outro host.

## Para saber mais: namespaces e Cgroups

Uma das características que destacamos no uso de containers é o seu isolamento em diferentes níveis. Podemos compreender o isolamento como um modo de empacotar uma aplicação incluindo todos os recursos necessários para sua execução, garantindo que o software apresente o mesmo comportamento em diferentes ambientes.

Os namespaces possuem um papel fundamental neste sentido, gerando o isolamento de grupos de processos em seu nível lógico. Assim, os processos dentro do container são completamente isolados dos processos que estão em execução no host.

Alguns exemplos fundamentais de namespaces são:

- PID (Process Identifier Namespace): isolamento de processos que estão em execução dentro do container.
- NET (Network Namespace): isolamento dos recursos de rede, como interfaces de rede, endereços IP e tabelas de roteamento.
- IPC (Inter-Process Communication Namespace): isolamento dos mecanismos de comunicação entre processos, como filas de mensagens e memória compartilhada.
- MNT (Mount Namespace): isolamento do sistema de arquivos e pontos de montagem, garantindo que alterações no sistema de arquivos dentro de um container não afetem o sistema de arquivos fora dele.
- UTS (Unix Timesharing System Namespace): isolamento do kernel, permitindo que o container atue como se fosse outro host.

Por sua vez, o gerenciamento dos recursos físicos compartilhados entre os processos fica sob responsabilidade de um recurso conhecido como Cgroups (grupos de controle). Os Cgroups permitem que o Docker aloque recursos como tempo da CPU, memória do sistema, largura de banda de rede ou combinações destes.

## Verificando o Docker
Execute o comando `docker run hello-world` de um shell/terminal. 
> Daria pra usar o shell WSL do Windows para simular Linux, mas no meu Windows 11 isso não funcionou - recomendou o uso do Powershell.

## Para saber mais: virtualização baseada em containers
Assim como o VirtualBox que usamos para criar máquinas virtuais (VMs) com sistemas operacionais específicos (Ubuntu Server, por exemplo) para testes ou análises, o Docker também é um sistema de virtualização. A grande diferença entre eles está no modo de virtualização adotado, já que o Docker está baseado no conceito de containers.

A ideia dos containers surge da necessidade de reduzir divergências entre os diversos ambientes comuns no desenvolvimento de software, tais como desenvolvimento, teste, homologação e produção. O uso do termo “container” para designar o conceito não foi uma escolha ao acaso. Os containers surgiram como uma solução no transporte de cargas para facilitar atividades envolvidas no transporte de mercadorias de seu ambiente de fabricação até consumidores finais (casa, indústria, comércio, dentre outros), passando por diferentes meios de transporte e terminais de carga.

Podemos imaginar o software como um produto que deve ser transportado do ambiente de desenvolvimento para produção. Neste caso, nossa maior preocupação está em garantir que os diferentes ambientes envolvidos neste processo tenham todos os pré-requisitos instalados, de preferência com uma versão do sistema operacional semelhante à adotada no ambiente de desenvolvimento.

O Docker atua justamente nesse sentido. Temos um container com nosso software que pode ser levado de um ambiente para outro sem problemas relacionados aos pré-requisitos necessários no ambiente para sua execução. Assim, conseguimos minimizar eventuais divergências entre ambientes no desenvolvimento de software.
