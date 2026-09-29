# Novo Backend Node.js MVC
## Passo a passo para iniciar um novo Projeto BackEnd
- 1 Criar uma **pasta**em sua Área de tabalho e abrir com o **VsCode**
- 2 Criar um arquivo `server.js` contendo:
```js
const express = require("express")
const cors = require("cors")

const routes = require("./src/routes")

const app = express()
app.use(cors())
app.use(express.urlencoded({ extended: true }))
app.use(express.json())
app.use(routes)
const porta = 3000

app.listen(porta, () => {
    console.log(`Servidor respondendo em: http://localhost:${porta}`)
})
```
- 3 Abrir o terminal `CTRL + '` tipo `CMD` ou `bash` e digitar os comandos para iniciar o projeto e instalar as dependencias **express** e **cors**
```bash
npm init -y
npm i express cors
```
- 4 Configurar o `package.json` alterando os campos:
    - "name":"nome_projeto",
    - "main":"server.js"
    - Adicionar o script:
        - "dev": "node --watch server.js"
```json
{
  "name": "nome_do_projeto",
  "version": "1.0.0",
  "main": "server.js",
  "scripts": {
    "dev": "node --watch server.js",
    "start": "node server.js"
  },
  "keywords": [],
  "author": "wellifabio",
  "license": "ISC",
  "description": "",
  "dependencies": {
    "express": "^5.2.1"
  }
}
```
- 5 Criar o arquivo de rotas `src/routes.js`
```js
const express = require("express")
const router = express.Router()

const rotaInicial = (req, res) => {
    res.json("Back-end respondendo")
}

router.get('/',rotaInicial)

module.exports = router
```
- 6 Executar o servidor
```bash
npm run dev
```
- Resultado
```bash
Servidor respondendo em: http://localhost:3000
```
- Segure o `CTRL` e clique no link que aparecerá:
- Resposta:
```text
"Back-end respondendo"
```
- 7 Crie o arquivo `.gitignore` contendo:
```text
node_modules
package-lock.json
```
## Agora desenvolva seus controlles CRUDs e rotas ..
- Dentro da pasta src crie outra pasta `src/controllers` e os arquivos de controle.
- Mãos a obra ...