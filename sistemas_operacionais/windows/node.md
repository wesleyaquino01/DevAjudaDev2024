# _Início_

    1º Instale o node

## _Verificar as versões no Windows_

    node --version
    npm --version
    ng version


# _Instalando um Projeto já existente_ 
    (Clone o projeto com o $ git clone "link_do_projeto" e entre na pasta que foi criada com o "cd nome_da_pasta_que_foi_criada)
    
    npm install
    npm start


# _Lidando com o Cache no Node_ 
    npm cache verify
    npm cache clean --force

# _Desistalando Pacote_
    npm uninstall <package-name>
### _Usando a flag -S, ou --save, essa operação também irá remover a referência no arquivo package.json._
    npm uninstall -S <package-name>
### _Se o pacote era uma dependência de desenvolvimento_
    npm uninstall -D <package-name>
### _Se o pacote está instalado globalmente_
    npm uninstall -g <package-name>


## _Angular_ 
### _Instala o Angular Globalmente_
    npm install -g @angular/cli@<versao>

### _Verificar versão do Angular e do Angular CLI_

    ng version
