# Processo de Implantação


## Configurando a API

1. Instale o ````virtualenv````
    - ````sudo pip3 install virtualenv````
1. Crie um ambiente virtual chamado ````bobenv````
    - ````virtualenv ~/.bobenv````
1. Inicie o ambiente virtual
    - ````source ~/.bobenv/bin/activate````
1. Clone o repositório da API
    - ````git clone https://github.com/BabyOnBoard/BabyOnBoard-API.git````
1. Dentro da raiz do repositório, instale as dependências
    - ````pip3 install -r requirements.txt````
1. Dentro da pasta ````BabyOnBoard-API/babyonboard```` crie as migrations
    - ````python3 manage.py makemigrations````
1. Aplique as migrations
    - ````python3 manage.py migrate````
1. Rode a aplicação
    - ````python3 manage.py runserver 0.0.0.0:8000````
1. Verifique se está tudo funcionando acessando o seguinte endereço
    - ````http://localhost:8000/api/v1/temperature/````


## Configurando os Sensores

1. Instale o ````matplotlib````
    - ````sudo pip3 install matplotlib````
1. Instale a biblioteca ````sox````
    - ````sudo apt-get install sox````
1. Configure o dispositivo de captura de áudio
    - ````export AUDIODEV=hw:1,0````
    - ````export AUDIODRIVER=alsa````
1. Clone o repositório dos Sensores
    - ````git clone https://github.com/BabyOnBoard/BabyOnBoard-Sensores.git````
1. Compile os arquivos usando o ````Makefile````
    - ````make````
1. Inicie a API e teste cada um dos sensores
    - ````./microfone````: detecta se o bebê está chorando
    - ````./temperatura````: mede a temperatura do bebê
