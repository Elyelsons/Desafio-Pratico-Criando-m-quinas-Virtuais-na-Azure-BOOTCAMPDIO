# Criação da Máquina Virtual no Microsoft Azure

Este documento detalha o processo de criação de uma máquina virtual (VM) no portal do Microsoft Azure.

## 1. Acesso ao Portal do Azure

* Primeiramente, acessei o [Portal do Azure](https://portal.azure.com/) e realizei o login com minha conta.

## 2. Criação de um Grupo de Recursos

* No menu principal, cliquei em "Grupos de recursos" e, em seguida, em "+ Criar".
* Preenchi os seguintes campos:
    * **Assinatura:** Selecionei a minha assinatura ativa do Azure.
    * **Grupo de recursos:** Nomeei o grupo de recursos como `rg-laboratorio-dio` (uma convenção para identificar recursos relacionados a este laboratório).
    * **Região:** Escolhi a região `South America East (São Paulo)` para minimizar a latência, considerando minha localização em São Luís, Maranhão, Brasil.
* Cliquei em "Revisar + criar" e, posteriormente, em "Criar".

## 3. Criação da Máquina Virtual

* No menu principal do portal, cliquei em "Máquinas virtuais" e, em seguida, em "+ Criar" e "Máquina virtual do Azure".
* Na tela de criação da máquina virtual, configurei os seguintes parâmetros na aba "Básico":
    * **Assinatura:** Selecionei a mesma assinatura do grupo de recursos.
    * **Grupo de recursos:** Selecionei o grupo de recursos criado anteriormente (`rg-laboratorio-dio`).
    * **Nome da máquina virtual:** Nomeei a VM como `vm-dio-lab`.
    * **Região:** Preenchi automaticamente com a região do grupo de recursos (`South America East`).
    * **Opções de disponibilidade:** Deixei como "Nenhuma redundância de infraestrutura" para este laboratório.
    * **Imagem:** Selecionei `Ubuntu Server 22.04 LTS`.
    * **Arquitetura:** Deixei a arquitetura padrão `x64`.
    * **Tamanho:** Escolhi o tamanho `Standard_B1ls` para um bom custo-benefício em cargas de trabalho leves.
    * **Tipo de disco do SO:** Selecionei `SSD Standard`.
    * **Autenticação:** Escolhi "Chave pública SSH".
    * **Nome de usuário:** Defini `azureuser`.
    * **Fonte da chave pública SSH:** Selecionei "Gerar novo par de chaves".
    * **Nome do par de chaves:** Nomeei o par de chaves como `ssh-key-dio-lab` e cliquei em "Criar e baixar chave privada". **Salvei este arquivo `.pem` em um local seguro!**
* Na aba "Disco", mantive as configurações padrão.
* Na aba "Rede", observei a criação automática de uma rede virtual (`vm-dio-lab-vnet`) e uma sub-rede (`subnet-1`). O Azure também propôs a criação de um endereço IP público (`vm-dio-lab-ip`) e um grupo de segurança de rede (`vm-dio-lab-nsg`).
* Na aba "Gerenciamento", mantive as configurações padrão para monitoramento e diagnóstico.
* Nas abas "Avançado", "Marcas" e "Revisar + criar", mantive as configurações padrão ou adicionei informações opcionais.
* Finalmente, cliquei em "Revisar + criar" para validar as configurações e, em seguida, em "Criar" para provisionar a máquina virtual.

## 4. Conexão via SSH

* Após a criação da VM, obtive o endereço IP público na página de visão geral da máquina virtual no portal.
* Utilizei um cliente SSH (como o terminal no Linux/macOS ou PuTTY no Windows) para conectar à VM:
    ```bash
    ssh -i "caminho/para/ssh-key-dio-lab.pem" azureuser@<endereço-ip-público>
    ```
    * **Importante:** Substituí `"caminho/para/ssh-key-dio-lab.pem"` pelo caminho real onde salvei o arquivo da chave privada e `<endereço-ip-público>` pelo endereço IP público da minha VM.

## Conclusão

A máquina virtual Ubuntu Server foi criada com sucesso no Azure, utilizando o portal para configurar os recursos e a autenticação por chave SSH para acesso seguro. O próximo passo é realizar as configurações iniciais no servidor.
