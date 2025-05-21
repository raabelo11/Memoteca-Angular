# Configurações iniciais para rodar o Projeto Memoteca

Este documento lista todas as ferramentas e comandos necessários para configurar e rodar o projeto Memoteca.

---

## 1. Instalar Node.js e npm

- Baixe e instale a versão LTS do Node.js (inclui o npm) em:  
  https://nodejs.org/

- Verifique as versões instaladas:  
  ```bash
  node -v
  npm -v

## 2. Instalar Angular CLI globalmente

- npm install -g @angular/cli
- Verifique as versões instaladas:  
  ```bash
  ng version

## 3. Configurar o projeto Angular

Navegue até a pasta do seu projeto Angular (ou clone o repositório):
- cd Memoteca-Angular

Instale as dependências do projeto:
- npm install

## 4. Instalar json-server localmente na versão recomendada

- npm install json-server@0.17.3 --save-dev

Criar e configurar o arquivo db.json. Na raiz do projeto, crie o arquivo db.json com o seguinte conteúdo:

{
  "pensamentos": []
}

Executar o json-server na porta 3000

- npx json-server --watch db.json --port 3000

Executar o projeto Angular

- ng serve

## Observações:

- A aplicação Angular ficará disponível em: http://localhost:4200
- Para buscar todos os pensamentos (GET): http://localhost:3000/pensamentos
- Para criar um pensamento (POST): http://localhost:3000/pensamentos
- Sempre que alterar o arquivo db.json, reinicie o json-server para aplicar as mudanças.
- Caso receba erro 404 em POST ou GET, confira se o json-server está rodando e se o arquivo db.json contém o recurso correto (pensamentos).
- Utilize o Angular HttpClient para consumir a API no frontend.
