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
