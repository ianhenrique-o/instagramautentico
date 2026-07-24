# Raio-X do Instagram Autêntico — Landing Page

Página pronta pra subir no GitHub Pages. É um site estático de um arquivo só (`index.html`), com código limpo e editável: as fontes vêm do Google Fonts e as animações do GSAP, ambas carregadas por CDN (link no próprio HTML). As **suas imagens** ficam na pasta `assets`.

## Estrutura

```
(raiz do repositório)
├── index.html          ← a página (só edite o link de checkout, explicado abaixo)
├── .nojekyll           ← faz o GitHub Pages servir o site como está (não apague)
├── README.md           ← este arquivo
└── assets/             ← coloque as suas imagens aqui
    ├── ian.jpg
    ├── fathima-antes.png
    └── fathima-depois.png
```

> Importante: mande estes arquivos pra **raiz** do repositório (o `index.html` tem que ficar na raiz, não dentro de uma subpasta). Ao descompactar o .zip, é só selecionar tudo o que está dentro e subir.

## 1. As imagens (a sua dúvida principal)

A página **não** carrega as imagens de dentro do arquivo HTML. Ela procura por 3 arquivos dentro da pasta `assets`, com nomes fixos. Isso é de propósito: fotos pesam muito, então o certo é mantê-las como arquivos separados (fica mais leve, mais fácil de trocar e o navegador consegue guardar em cache).

Basta colocar os arquivos abaixo dentro de `assets` com o nome exato:

| Arquivo | Onde aparece | Sugestão |
|---|---|---|
| `ian.jpg` | Seção "O Método Raio-X" | Foto sua, vertical, ~800×1000px |
| `fathima-antes.png` | Seção "Prova real" (antes) | Print do perfil com 8.930 seguidores |
| `fathima-depois.png` | Seção "Prova real" (depois) | Print do perfil com 33,6 mil seguidores |

Enquanto o arquivo não existir, a página mostra um espaço reservado bonito no lugar — ou seja, ela nunca fica "quebrada". Assim que você colocar a imagem com o nome certo e subir, ela aparece automaticamente.

> Se o seu arquivo tiver outra extensão (ex.: `ian.png` em vez de `ian.jpg`), renomeie pra bater com a tabela, ou me avise que eu ajusto o código.

## 2. O link de compra (checkout)

Abra o `index.html` num editor de texto e procure por esta linha (está bem no comecinho do bloco de script):

```js
const CHECKOUT_URL = "#";
```

Troque o `#` pelo link do seu checkout, por exemplo:

```js
const CHECKOUT_URL = "https://pay.seucheckout.com/xxxx";
```

Pronto: os 3 botões da página passam a apontar pra lá de uma vez.

## 3. Subir no GitHub Pages (passo a passo)

1. Crie um repositório novo no GitHub (pode ser público).
2. Faça upload de **tudo que está nesta pasta** — o `index.html` e a pasta `assets` com as imagens dentro. (No site do GitHub: botão "Add file" → "Upload files" → arraste os arquivos.)
3. No repositório, vá em **Settings → Pages**.
4. Em "Build and deployment", em **Source**, escolha **Deploy from a branch**.
5. Em **Branch**, escolha `main` e a pasta `/ (root)`. Clique em **Save**.
6. Espere 1 a 2 minutos. O GitHub vai te dar o endereço no formato `https://seu-usuario.github.io/nome-do-repositorio/`.

O arquivo precisa se chamar `index.html` (já está com esse nome) pra ser aberto como página inicial.

### Domínio próprio (opcional)

Se quiser usar um domínio seu (ex.: `raiox.seunome.com.br`) em vez do endereço do GitHub, dá pra configurar em **Settings → Pages → Custom domain**. É só apontar o DNS do seu domínio pro GitHub. Se precisar, me chama que eu te passo o caminho.

## Observações

- As fontes (Google Fonts) e as animações (GSAP) são carregadas por CDN, então a página precisa de internet pra exibir tudo — o que é o normal num site publicado. Em troca, o código fica limpo, leve e fácil de editar.
- Não use `localStorage` nem nada assim: é uma página estática, feita pra carregar rápido e converter.
