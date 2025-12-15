## Importação do fluxo no Node-RED

O fluxo do Node-RED está disponibilizado no arquivo flows.json. Para utilizá-lo no ambiente local, siga o procedimento descrito abaixo:

## Requisitos do ambiente

Node-RED instalado e em execução

Acesso à interface web do Node-RED (padrão: http://<host>:1880)

Permissão para importar fluxos no ambiente

## Procedimento de importação

Acesse a interface web do Node-RED.

No menu principal (ícone ☰), selecione Importar → Selecione um Arquivo para Importar.

Abra o arquivo flows.json fornecido neste repositório.

Copie o conteúdo do arquivo e cole o conteúdo no campo de importação do Node-RED.

Confirme a operação clicando em Importar.

Após a importação, execute Implementar para aplicar o fluxo ao Tempo de Execução.

-------------------------------------------------------------------------------------------

## Nós e Pacotes Extras Utilizados

(1)template

(2)mqtt in

(1)mqtt out

(8)json

(4)gauge

(4)switch

(11)function

(1)notification

(2)text input

Foi adicionado o pacote Dashboard 2.

-------------------------------------------------------------------------------------------

## Tópicos MQTT Utilizados

// Tópico: carrinho/dados

Este tópico é utilizado para publicação de dados do carrinho para o Node-RED.

As mensagens recebidas neste tópico são processadas pelo fluxo e encaminhadas para a Dashboard, permitindo a visualização em tempo real do estado do sistema.


- Informações transportadas:

•Temperatura dos motores

•Estado dos LEDs (ligado / desligado)


- Direção da comunicação:

Dispositivo → Broker MQTT → Node-RED → Dashboard


- Formato do payload:

JSON


// Tópico: carrinho/dash

Este tópico é utilizado para publicação de comandos de controle a partir da Dashboard para o carrinho.

As mensagens enviadas por este tópico são originadas na interface da Dashboard e processadas pelo dispositivo, permitindo controle remoto.

- Funcionalidades associadas:

Comandos para acionamento e desligamento dos LEDs

Envio de informações de autenticação para liberação do controle na Dashboard

- Direção da comunicação:

Dashboard → Node-RED → Broker MQTT → Dispositivo

- Formato do payload:

JSON