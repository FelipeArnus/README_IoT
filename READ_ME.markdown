# README - Solução IoT com Ubuntu, Docker e Fiware



Este README descreve uma solução de Internet das Coisas (IoT) baseada em uma máquina virtual Ubuntu, utilizando Docker e Fiware. A solução proposta envolve a criação de uma infraestrutura que permite a comunicação e o processamento de dados entre dispositivos IoT, um backend e um frontend para visualização e controle dos dados.

## Arquitetura Proposta

A arquitetura da solução IoT consiste em três componentes principais: dispositivos IoT, backend e frontend.

### Dispositivos IoT
Os dispositivos IoT são sensores ou atuadores que coletam dados do ambiente ou controlam dispositivos físicos. Eles podem ser sensores de temperatura, umidade, câmeras, ou qualquer outro dispositivo conectado à Internet. Esses dispositivos enviam dados para o backend.

### Backend
O backend é responsável por receber, armazenar e processar os dados dos dispositivos IoT. Ele utiliza a plataforma Fiware, que oferece suporte para gerenciamento de dados em tempo real. O Fiware inclui componentes como o Orion Context Broker para armazenamento e gerenciamento de dados, e o MongoDB para armazenamento persistente.

### Frontend
O frontend é a interface de usuário que permite aos usuários visualizar e controlar os dispositivos IoT e os dados coletados. Ele pode ser uma aplicação web ou móvel que se conecta ao backend para exibir informações em tempo real e permitir a interação com os dispositivos.

## Recursos Necessários

Para implementar esta solução IoT, você precisará dos seguintes recursos:

### Hardware:
- A máquina em que esse tutorial foi gravado era um processador i5, HD-1tb, 8gb, GTX 750 ti

### Software:
- Docker: Para criar e gerenciar containers.
- Git: Para clonar o repositório do Fiware Descomplicado.
- Fiware Descomplicado: Um repositório contendo os containers e configurações necessárias para a plataforma Fiware.

## Instruções de Uso

Siga os passos abaixo para configurar e executar a solução IoT com Ubuntu, Docker e Fiware em adição:

1. **Instalar o ifconfig para identificar o IP da máquina virtual:**
- sudo apt-get install net-tools

2. **Comando para ler o IP da VM (Virtual Machine):**
 - ifconfig

3. **Instalar o git**
- sudo apt install git

4. **Instale o docker(apenas o primeiro do site | ilustrado do 5. até 11.)**
- (https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)

5. **Primeiro, atualize sua lista existente de pacotes:**
- sudo apt update 

6. **Pacotes de pré-requisitos que permitem aptusar pacotes via HTTPS:**
- sudo apt install apt-transport-https ca-certificates curl software-properties-common 

7. **Adicionar a chave GPG do repositório oficial do Docker ao seu sistema:**
- curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

8. **Adicionar o repositório Docker às fontes APT:**
- sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

9. **Certifique-se de instalar a partir do repositório Docker em vez do repositório padrão do Ubuntu:**
- apt-cache policy docker-ce

10. **Instale o Docker**
- sudo apt install docker-ce

11. **Verificação se o docker esta ativo**
- sudo systemctl status docker

12. **Copiar os arquivos do repositório de Fiware Descomplicado**
- git clone https://github.com/fabiocabrini/fiware

13. **Entrar na pasta do Fiware[Colocar Codigo]**
- cd fiware

14. **Rodar os containers[Colocar Codigo]**
- sudo docker compose up -d

15. **status dos containers[Colocar Codigo]**
- sudo docker stats

16. **faça o download desse arquivo**
- (github.com/fabiocabrini/fiware/blob/main/FIWARE.postman_collection.json)

17. **Entrar em myWorkspace**
- importe o arquivo do passo 16.

18. **Clique em Health Check e reabra o terminal[Colocar Codigo]**
- ifconfig
- encontre a linha inet xxx.xxx.x.xx(copie esse numero(os 'x'))

19. **Substitua( {{url}} ) do get em Health Check pelo copiado**
- Repita em IOT Agent MQTT, Orion Context Broker e STH-Comet
