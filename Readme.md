## sCriar aplicação Node.js com Typescript

A aplicação backend que será desenvolvida é uma API de Vendas com Node.js, Typescript, TypeORM, Docker e muito mais.

<br>
<br>

Iniciar a aplicação Node.js com Typescript

```bash
yarn init -y
```
<br>

Fazer a instalação do __Typescript__ na pasta do projeto, como uma dependência de desenvolvimento. Como o código final é convertido para __javascript__ antes de ser disponibilizado online, só precisaremos do __Typescript__ em ambiente de desenvolvimento.

<br>

```bash
yarn add typescript ts-node-dev @types/node -D
```

<br>

Criar o arquivo "tsconfig.json" que conterá as configurações do Typescript, com o comando:
```bash
yarn tsc --init --rootDir src --outDir build \
--esModuleInterop --resolveJsonModule --lib es6 \
--module commonjs --allowJs true --noImplicitAny true
```

<br>
Em resumo, os parâmetros passados são:

<br>
<br>

__rootDir:__ É aqui que o TypeScript procura nosso código.

__outDir:__ Onde o TypeScript coloca nosso código compilado.

__esModuleInterop:__ Se estiver usando commonjs como sistema de módulo (recomendado para aplicativos Node), então esse parâmetro deve ser definido como true.

__resolveJsonModule:__ Se usarmos JSON neste projeto, esta opção permite que o TypeScript o use.

__lib:__ Esta opção adiciona tipos de ambiente ao nosso projeto, permitindo-nos contar com recursos de diferentes versões do Ecmascript, bibliotecas de teste e até mesmo a API DOM do navegador. Usaremos recursos es6 da linguagem.

__module:__ commonjs é o sistema de módulo Node padrão.

__allowJs:__ Se você estiver convertendo um projeto JavaScript antigo em TypeScript, esta opção permitirá que você inclua arquivos .js no projeto.

__noImplicitAny:__ Em arquivos TypeScript, não permita que um tipo seja especificado inexplicitamente. Cada tipo precisa ter um tipo específico ou ser declarado explicitamente any.

<br>

<br>

Compilando o Typescript

<br>

Para compilar nosso código, precisaremos executar o comando tsc, que irá ler o arquivo tsconfig.json no diretório atual e aplicará a configuração ao compilador TypeScript para gerar o código JavaScript compilado.

<br>

```bash
yarn tsc
```

<br>
O código compilado foi gerado na pasta build.

Executar o servidor em desenvolvimento

Usaremos a biblioteca ts-node-dev para execução da aplicação em desenvolvimento.

<br>

Incluir o script para rodar o ts-node-dev no arquivo package.json.
```bash
"scripts": {
  "dev": "ts-node-dev --inspect --transpile-only --ignore-watch node_modules src/server.ts"
}
```
Executar o servidor:
```bash
yarn dev
````
