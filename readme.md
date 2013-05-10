#Yeoman/Ember Starter

Este projeto visa facilitar o início da criação de projetos com [EmberJs](http://emberjs.com/) usando o [Yeoman](http://yeoman.io), por enquanto que o [https://github.com/yeoman/generator-ember](https://github.com/yeoman/generator-ember) não faz seu papel inicial corretamente.

##1 - Node.js
Antes de mais nada, este projeto usa tecnologais que necessitam do Node.js, que pode ser baixado no link [http://nodejs.org/download/](http://nodejs.org/download/)

##2 - Yeoman

Este projeto foi criado usando o [Yeoman](http://yeoman.io), portanto é preciso ter instalado em sua máquina. Para isso, execute o comando abaixo:

	npm install -g yo
	
##3 - Dependências

As dependências do projeto não são adicionadas no versionamento. Portanto, antes de mais nada execute o comando abaixo em seu terminal:

	npm install && bower install

Este comando irá instalar as dependências contidas em `component.json` e `package.json` para o correto funcionamento do projeto.

Se tudo deu certo você poderá executar o comando `grunt server` e ver a página aberta no endereço [http://localhost:9000/](http://localhost:9000/)

Para mais informações sobre o Yeoman visite [http://yeoman.io/gettingstarted.html](http://yeoman.io/gettingstarted.html)


##Problemas no procedimento de instalação

###Problemas ao tentar executar o npm, erro de conexão ao tentar buscar e instalar o Yeoman
Caso sua rede esteja usando proxy, o npm precisa ser informado disso, caso você não tenha ou o NPM esteja ignorando as váriaveis de ambiente `http_proxy` nem `https_proxy`. Para configurar o NPM para rodar com proxy execute o comando abaixo substituindo a url pela url do proxy de sua rede.

	npm config set proxy http://proxy.empresa.com:8080 && npm config set https-proxy http://proxy.empresa.com:8080

Vide [https://npmjs.org/doc/config.html](https://npmjs.org/doc/config.html)

###Problemas ao tentar executar o bower, erro de conexão ao tentar buscar e instalar dependências
Caso sua rede esteja usando proxy, o bower não irá usar as dependências por padrão de proxy do NPM e de ambiente com caixa baixa. Para concertar isto, basta adicionar no npm ou no seu path as variáveis `HTTP_PROXY` e `HTTPS_PROXY` com um dos comandos abaixo:

	npm config set HTTP_PROXY http://proxy.empresa.com:8080 && npm config set HTTPS_PROXY http://proxy.empresa.com:8080

Ou em seu arquivo `~/.bashrc`, ou `~/.zshrc` caso use zshel, adicone as variáveis

	export HTTP_PROXY=http://proxy.empresa.com:8080
	export HTTPS_PROXY=http://proxy.empresa.com:8080
	
Vide [https://github.com/bower/bower/issues/208](https://github.com/bower/bower/issues/208)
	
###Erro ao instalar a dependência PhantomJS, problemas com o arquivo zip
Caso o npm reclame ao tentar instalar o PhantomJS por erro ao descompactar o zip baixado, basta baixar o zip manualmente em [http://phantomjs.org/download.html](http://phantomjs.org/download.html) e substituir o arquivo corrompido, cuja a localização é indicada no log de erro, pelo arquivo baixado manualmente e rodar novamente o comando para instalar as dependências como descrito no **passo 3**.