# Next Level Week 02

Projeto Happy - Visitação de Orfanatos - Next Level Week 3 - Rocketseat

## Estrutura do Projeto

| Pasta | Descrição |
| ----------- | ----------- |
| ./backend | API REST feita em Express e TypeScript e banco de dados SQLite |
| ./web | Interface web em RectJS e TypeScript |
| ./mobile | Interface mobile em ReactNative e TypeScript |


## Entidades

| Entidades | Atributos |
| ----------- | ----------- |
| orphanages | id, name, latitude, longitude, about, instructions, opening_hours, open_on_weekends |
| images | id, path, orphanage_id |

## Funcionalidades

* Listagem de orfanatos no mapa
* Detalhes de um orfanato
* Cadastro de orfanato

## Iniciando o projeto

Após clonar o projeto, é necessário atualizar as dependências e efetuar as migrações do banco de dados.

Baixar, migrar banco e executar Server (a partir da raiz; precisa ser executado primeiro)

```bash
cd backend
yarn
yarn typeorm migration:run
```

Baixar e executar Web (a partir da raiz)
```bash
cd web
yarn
```

Baixar e executar Mobile (a partir da raiz)
```bash
cd mobile
yarn
```

## Configurações


Arquivo **./backend/src/views/images_view.ts**

```javascript
// Substituir <ip_backend> pelo IP em que está executando o backend, no método render
render(image: Image) {
  return {
    id: image.id,
    url: `<ip_backend>/uploads/${image.path}`,
  }
},
```

Arquivo **./mobile/src/services/api.ts**

```javascript
// Substituir <ip_backend> pelo endereço IP em que está executando o backend
const api = axios.create({
  baseURL: 'http://<ip_backend>:3333',
})
```

Criar arquivo **.env**, conforme o arquivo **.env.example**, contendo a chave do MapBox

 * Chave deve ser criada em https://www.mapbox.com/