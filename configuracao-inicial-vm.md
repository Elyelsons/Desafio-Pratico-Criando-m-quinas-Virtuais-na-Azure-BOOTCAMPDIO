# Configuração Inicial da Máquina Virtual Ubuntu Server

Este documento descreve as configurações iniciais realizadas na máquina virtual Ubuntu Server após a sua criação no Azure.

## 1. Atualização dos Pacotes do Sistema

* Após conectar à VM via SSH, a primeira etapa é atualizar a lista de pacotes e os pacotes instalados para garantir que o sistema esteja com as versões mais recentes e correções de segurança:
    ```bash
    sudo apt update
    sudo apt upgrade -y
    ```

## 2. Instalação de Ferramentas Essenciais (Opcional)

* Dependendo das necessidades futuras, algumas ferramentas podem ser úteis. Por exemplo, para transferência de arquivos:
    ```bash
    sudo apt install -y wget curl vim
    ```

## 3. Criação de um Novo Usuário (Recomendado)

* Por questões de segurança, é recomendável criar um novo usuário com privilégios de `sudo` e desabilitar o login direto com o usuário `azureuser` (opcional, mas uma boa prática).
    ```bash
    sudo adduser <novo-usuario>
    sudo usermod -aG sudo <novo-usuario>
    ```
    * Substitua `<novo-usuario>` pelo nome desejado para o novo usuário. Siga as instruções para definir a senha.

## 4. Configuração do Firewall (UFW - Uncomplicated Firewall)

* O Ubuntu Server vem com o UFW como firewall padrão. É importante configurá-lo para permitir apenas o tráfego necessário.
    * Habilitar o firewall:
        ```bash
        sudo ufw enable
        ```
    * Permitir tráfego SSH (porta 22):
        ```bash
        sudo ufw allow ssh
        ```
    * Para verificar o status do firewall:
        ```bash
        sudo ufw status
        ```

## 5. Configuração de Timezone (Opcional)

* Para configurar o timezone para o horário de São Paulo:
    ```bash
    sudo timedatectl set-timezone America/Sao_Paulo
    sudo timedatectl show
    ```

## Conclusão

Estas são as configurações iniciais básicas realizadas na máquina virtual Ubuntu Server. O sistema agora está atualizado e mais seguro para futuras utilizações e experimentações.
