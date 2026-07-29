# Hello Docker!
## Entendendo os containers
Diferente de máquinas virtuais, containers não possuem uma camada de hipervisor.

Há diversos namespaces usados para os containers: 
- **PID**: isola processos que rodam no container;
- **NET**: isola as interfaces de rede;
- **IPC**: isola comunicação entre processos e memória compartilhada;
- **MNT**: isola o sistema de arquivos/pontos de montagem;
- **UTS**: isola o kernel, como se o container fosse outro host.
