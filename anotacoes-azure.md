# Anotações sobre o Microsoft Azure

Este arquivo contém anotações gerais sobre os conceitos e serviços do Microsoft Azure explorados durante a criação da máquina virtual.

## Conceitos Fundamentais

* **Regiões:** Localizações geográficas ao redor do mundo onde a Microsoft possui data centers. A escolha da região impacta na latência, custos e disponibilidade dos serviços.
* **Grupos de Recursos:** Contêineres lógicos para agrupar recursos relacionados do Azure. Facilitam o gerenciamento, controle de acesso e ciclo de vida dos recursos.
* **Redes Virtuais (VNet):** Permitem criar redes privadas isoladas dentro do Azure, fornecendo conectividade para os recursos.
* **Sub-redes:** Segmentações dentro de uma VNet para organizar e isolar recursos.
* **Endereços IP Públicos:** Permitem que os recursos do Azure se comuniquem com a internet. Podem ser dinâmicos ou estáticos.
* **Grupos de Segurança de Rede (NSG):** Firewalls virtuais que controlam o tráfego de entrada e saída dos recursos dentro de uma VNet.
* **Máquinas Virtuais (VM):** Emulações de hardware físico que executam sistemas operacionais e aplicativos na nuvem.
* **Imagens:** Templates pré-configurados de sistemas operacionais e software que podem ser usados para criar VMs.
* **Tamanhos de VM:** Diferentes configurações de CPU, memória, disco e rede disponíveis para as VMs, otimizadas para diferentes tipos de cargas de trabalho.
* **Discos Gerenciados:** Volumes de armazenamento persistentes anexados às VMs, gerenciados pelo Azure.
* **SSH (Secure Shell):** Protocolo seguro para acesso remoto a servidores Linux. A autenticação por chave pública oferece mais segurança do que a autenticação por senha.

## Observações sobre a Criação da VM

* A escolha da região "South America East (São Paulo)" foi estratégica para reduzir a latência para meu acesso local.
* A utilização de um grupo de recursos (`rg-laboratorio-dio`) facilitou a organização e o gerenciamento de todos os recursos criados para este laboratório.
* A autenticação por chave pública SSH é uma prática recomendada para segurança no acesso a servidores Linux. A necessidade de armazenar a chave privada de forma segura é crucial.
* O Azure simplifica a criação da rede virtual e do grupo de segurança de rede durante o processo de criação da VM, com configurações padrão que podem ser personalizadas posteriormente.

## Próximos Passos de Aprendizagem

* Explorar diferentes tamanhos de máquinas virtuais e seus casos de uso.
* Aprofundar o conhecimento sobre as configurações avançadas de rede e segurança no Azure.
* Experimentar outros serviços do Azure, como Azure App Service, Azure Functions e bancos de dados gerenciados.
