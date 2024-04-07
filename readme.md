# Iniciando o projeto:

- npm init
- npm install express
- npm install -g typescript (globalmente)
- npm install typescript (localmente)
- tsc --init
- npm i cross-env dotenv express helmet rimraf
- npm i @types/express @types/node
- npm i --save-dev concurrently
- npm i -D nodemon
| --save-dev ou -D serve para especificar que são dependencias necessárias apenas durante o desenvolvimento |

- npm run serve


# Explicando Scripts

build: Responsável por criar uma build do seu projeto.
- rimraf dist: Remove o diretório dist antes de cada compilação. rimraf é um pacote que remove diretórios de forma cruzada, funcionando em todos os sistemas operacionais.
- tsc: Compila o código TypeScript presente no seu projeto. Ele converte arquivos TypeScript em JavaScript.

preserve: Este script simplesmente executa o script build. Ele é útil quando você deseja ter um script de construção padrão que possa ser chamado de maneira consistente.

serve: Este script é usado para iniciar o servidor de desenvolvimento. Ele executa dois comandos em paralelo:
- tsc --watch: Monitora os arquivos TypeScript para mudanças e compila-os automaticamente sempre que houver uma mudança.
- nodemon -q dist/index.js: Inicia o servidor Node.js utilizando o nodemon. O -q significa "quiet" e faz com que o nodemon opere em modo silencioso. Ele reinicia o servidor sempre que houver alterações nos arquivos no diretório dist.

test: Este script é uma configuração padrão para testes. Atualmente, ele apenas imprime uma mensagem de erro indicando que nenhum teste foi especificado e sai com um código de saída 1, o que indica um erro.


start: Este é um nome comum para um script que inicia seu aplicativo. Quando você executa npm start no terminal, ele executará este script.
- cross-env NODE_ENV=production: cross-env é uma ferramenta que permite definir variáveis ​​de ambiente de forma consistente em diferentes sistemas operacionais. NODE_ENV=production define a variável de ambiente NODE_ENV como production. Essa variável de ambiente é frequentemente usada para indicar em qual ambiente seu aplicativo está sendo executado. Definir NODE_ENV como production geralmente é usado para sinalizar que o aplicativo está em um ambiente de produção, o que pode influenciar o comportamento do aplicativo (como habilitar o modo de produção em alguns frameworks ou bibliotecas).
- node dist/index.js: Este é o comando que realmente inicia seu aplicativo. node é o interpretador JavaScript do Node.js e dist/index.js é o arquivo JavaScript principal do seu aplicativo após a compilação. Normalmente, dist/index.js é o ponto de entrada do seu aplicativo compilado quando você está usando TypeScript.