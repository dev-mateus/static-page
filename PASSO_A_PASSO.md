# Passo a passo: pagina estatica simples com HTML, CSS e JS

Este guia cria a pagina aos poucos. Em cada etapa, voce adiciona um trecho de codigo, entende o motivo e testa no navegador. Ao final, a pagina estara completa.

## 1) Estrutura do projeto

Crie a pasta do projeto e, dentro dela, os arquivos base:

- index.html

- styles.css

- script.js

Separar responsabilidades evita confusao: HTML e estrutura, CSS e aparencia, JS e comportamento.

### Checkpoint de verificacao (Etapa 1)

- A pasta do projeto existe e tem os tres arquivos base.

- Os arquivos estao vazios ou prontos para receber o codigo.

## 2) HTML basico do documento

### O que vamos fazer (Etapa 2)

Criar o esqueleto do HTML com metadados e o link para o CSS.

### Conceitos utilizados (Etapa 2)

- `<!doctype html>`: define HTML5.

- `lang="pt-BR"`: idioma do documento.

- `meta charset` e `meta viewport`: codificacao e escala em dispositivos.

- `link` para o CSS.

### Codigo (cole em index.html) (Etapa 2)

```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Fundamentos de Paginas Web</title>
    <meta name="description" content="Pagina estatica simples para praticar HTML, CSS e JavaScript." />
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
  </body>
</html>
```

### Checkpoint de verificacao (Etapa 2)

- O arquivo HTML abre no navegador sem erros.

- O titulo aparece na aba do navegador.

- O arquivo CSS esta linkado (mesmo vazio, o link deve existir).

## 3) Header com navegacao

### O que vamos fazer (Etapa 3)

Adicionar um cabecalho com navegacao e um link para pular para o conteudo. Isso melhora acessibilidade e usabilidade.

### Conceitos utilizados (Etapa 3)

- `<header>` e `<nav>`: estrutura semantica.

- Link de pulo: melhora navegacao por teclado.

- Lista de links: agrupamento logico de navegacao.

### Codigo (adicione dentro de `<body>`) (Etapa 3)

```html
  <header class="site-header">
    <a class="skip-link" href="#conteudo">Pular para o conteudo</a>
    <nav class="navbar" aria-label="Navegacao principal">
      <a class="logo" href="#">
        <span aria-hidden="true">&#9872;</span>
        <span class="logo-text">Web 101</span>
      </a>
      <ul class="nav-links">
        <li><a href="#fundamentos">Fundamentos</a></li>
        <li><a href="#laboratorio">Laboratorio</a></li>
        <li><a href="#recursos">Recursos</a></li>
      </ul>
      <button class="theme-toggle" type="button" id="themeToggle" aria-pressed="false">
        Alternar tema
      </button>
    </nav>
  </header>
```

### Checkpoint de verificacao (Etapa 3)

- O cabecalho aparece no topo da pagina.

- Os tres links de navegacao estao visiveis.

- O botao "Alternar tema" esta presente.

## 4) Hero (area de destaque)

### O que vamos fazer (Etapa 4)

Adicionar um destaque com titulo, texto e um card lateral. Esse bloco explica o tema da aula e mostra um status que sera atualizado no JS.

### Conceitos utilizados (Etapa 4)

- `<section>` com `aria-labelledby`.

- `<aside>` para conteudo complementar.

- IDs para facilitar a integracao com JavaScript.

### Codigo (adicione dentro do `<header>` logo depois do `</nav>`) (Etapa 4)

```html
    <section class="hero" aria-labelledby="titulo-principal">
      <div class="hero-text">
        <p class="eyebrow">Aula pratica</p>
        <h1 id="titulo-principal">Fundamentos de paginas web</h1>
        <p>
          Esta pagina demonstra HTML semantico, estilos organizados e JavaScript
          simples para interacoes.
        </p>
        <button class="primary-cta" type="button" id="ctaButton">Ver exemplo</button>
      </div>
      <aside class="hero-card" aria-live="polite">
        <h2 class="card-title">Status da aula</h2>
        <p class="card-message" id="statusMessage">Aguardando sua interacao.</p>
        <p class="card-meta" id="clock">--:--</p>
      </aside>
    </section>
```

### Checkpoint de verificacao (Etapa 4)

- O titulo principal e o botao "Ver exemplo" aparecem.

- O card lateral mostra o texto de status e o relogio.

## 5) Conteudo principal com secoes

### O que vamos fazer (Etapa 5)

Criar tres secoes no `<main>` para organizar o conteudo: fundamentos, laboratorio e recursos.

### Conceitos utilizados (Etapa 5)

- `<main>`: area principal do documento.

- `<section>` e `<article>`: agrupam topicos.

- IDs para navegacao interna.

### Codigo (adicione depois do `</header>`) (Etapa 5)

```html
  <main id="conteudo">
    <section id="fundamentos" class="section">
      <header>
        <h2>Fundamentos essenciais</h2>
        <p>Organize o conteudo com tags que fazem sentido.</p>
      </header>
      <div class="grid">
        <article class="topic">
          <h3>HTML semantico</h3>
          <p>
            Use <code>&lt;header&gt;</code>, <code>&lt;main&gt;</code>, <code>&lt;section&gt;</code> e
            <code>&lt;article&gt;</code> para dar significado ao conteudo.
          </p>
        </article>
        <article class="topic">
          <h3>CSS organizado</h3>
          <p>
            Separe responsabilidades com variaveis, seletores claros e regras
            reutilizaveis.
          </p>
        </article>
        <article class="topic">
          <h3>JS com objetivo</h3>
          <p>
            Crie interacoes pequenas e previsiveis, sem misturar com a camada de estilo.
          </p>
        </article>
      </div>
    </section>

    <section id="laboratorio" class="section alt">
      <header>
        <h2>Laboratorio pratico</h2>
        <p>Experimente os exemplos e observe o comportamento no navegador.</p>
      </header>
      <div class="lab">
        <article class="lab-card">
          <h3>Checklist da aula</h3>
          <ul class="checklist" id="checklist">
            <li>
              <label>
                <input type="checkbox" name="item" />
                Estrutura basica do HTML
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" name="item" />
                Estilos com variaveis
              </label>
            </li>
            <li>
              <label>
                <input type="checkbox" name="item" />
                Interacao com JavaScript
              </label>
            </li>
          </ul>
          <p class="progress" id="progressText">0 de 3 itens concluidos</p>
        </article>
        <article class="lab-card">
          <h3>Notas rapidas</h3>
          <form class="note-form" id="noteForm">
            <label for="nota">Escreva uma nota para revisar depois</label>
            <textarea id="nota" name="nota" rows="4" placeholder="Ex.: revisar seletores CSS"></textarea>
            <button type="submit">Salvar nota</button>
          </form>
          <p class="note-output" id="noteOutput" aria-live="polite">Nenhuma nota ainda.</p>
        </article>
      </div>
    </section>

    <section id="recursos" class="section">
      <header>
        <h2>Recursos de estudo</h2>
        <p>Links de referencia para aprofundar o conteudo.</p>
      </header>
      <div class="resource-list">
        <a class="resource" href="https://developer.mozilla.org/pt-BR/docs/Web/HTML" target="_blank" rel="noopener noreferrer">
          Documentacao HTML
        </a>
        <a class="resource" href="https://developer.mozilla.org/pt-BR/docs/Web/CSS" target="_blank" rel="noopener noreferrer">
          Guia de CSS
        </a>
        <a class="resource" href="https://developer.mozilla.org/pt-BR/docs/Web/JavaScript" target="_blank" rel="noopener noreferrer">
          JavaScript para iniciantes
        </a>
      </div>
    </section>
  </main>
```

### Checkpoint de verificacao (Etapa 5)

- Os tres blocos de conteudo aparecem abaixo do header.

- Os links internos levam para as secoes corretas.

- O formulario de notas e o checklist aparecem na secao laboratorio.

## 6) Rodape e script

### O que vamos fazer (Etapa 6)

Fechar a pagina com rodape e carregar o JS no final do corpo para garantir que o HTML ja exista quando o script rodar.

### Codigo (adicione depois do `</main>`) (Etapa 6)

```html
  <footer class="site-footer">
    <p>Prof. Web | Fundamentos de paginas web</p>
    <p>Exercicio: tornar a pagina responsiva na proxima aula.</p>
  </footer>

  <script src="script.js" defer></script>
```

### Checkpoint de verificacao (Etapa 6)

- O rodape aparece no final da pagina.

- O arquivo script.js esta referenciado.

## 7) CSS: base e variaveis

### O que vamos fazer (Etapa 7)

Definir variaveis e estilos globais para evitar repeticao e manter consistencia visual.

### Codigo (cole em styles.css) (Etapa 7)

```css
:root {
  color-scheme: light;
  --bg: #f6f1e8;
  --surface: #ffffff;
  --ink: #1f1c1a;
  --muted: #5c4f46;
  --accent: #cc4b2c;
  --accent-dark: #a53b22;
  --border: #e2d6c6;
  --shadow: 0 20px 50px rgba(31, 28, 26, 0.1);
  --radius: 18px;
  --font-title: "Merriweather", "Georgia", serif;
  --font-body: "Source Sans 3", "Segoe UI", sans-serif;
}

* {

  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: var(--font-body);
  background: radial-gradient(circle at top left, #fffaf3 0%, #f6f1e8 60%, #efe5d8 100%);
  color: var(--ink);
  line-height: 1.6;
}

img {
  max-width: 100%;
  display: block;
}

a {
  color: inherit;
  text-decoration: none;
}
```

### Checkpoint de verificacao (Etapa 7)

- O fundo e a tipografia mudam ao recarregar a pagina.

- Nao ha sublinhado nos links.

## 8) CSS: header, hero e navegacao

### O que vamos fazer (Etapa 8)

Dar estilo ao cabecalho e ao destaque principal.

### Codigo (adicione ao final de styles.css) (Etapa 8)

```css
.site-header {
  padding: 24px 8vw 64px;
}

.skip-link {
  position: absolute;
  left: -999px;
  top: 16px;
  background: var(--accent);
  color: white;
  padding: 8px 16px;
  border-radius: 999px;
}

.skip-link:focus {
  left: 16px;
}

.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
  padding: 16px 20px;
  background: var(--surface);
  border-radius: var(--radius);
  box-shadow: var(--shadow);
  border: 1px solid var(--border);
}

.logo {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  font-weight: 700;
  letter-spacing: 0.5px;
}

.logo-text {
  font-family: var(--font-title);
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 16px;
  font-weight: 600;
}

.nav-links a {
  padding: 8px 12px;
  border-radius: 999px;
  transition: background 0.2s ease;
}

.nav-links a:hover,
.nav-links a:focus {
  background: #f2e6d6;
}

.theme-toggle {
  border: 1px solid var(--border);
  background: transparent;
  padding: 8px 14px;
  border-radius: 999px;
  font-weight: 600;
  cursor: pointer;
}

.hero {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  gap: 32px;
  margin-top: 40px;
  align-items: center;
}

.hero-text h1 {
  font-family: var(--font-title);
  font-size: 48px;
  line-height: 1.1;
  margin-bottom: 16px;
}

.eyebrow {
  text-transform: uppercase;
  letter-spacing: 3px;
  font-size: 12px;
  font-weight: 700;
  color: var(--accent);
  margin-bottom: 12px;
}

.primary-cta {
  margin-top: 24px;
  background: var(--accent);
  color: white;
  border: none;
  padding: 12px 20px;
  border-radius: 999px;
  font-weight: 700;
  cursor: pointer;
  transition: transform 0.2s ease, background 0.2s ease;
}

.primary-cta:hover {
  background: var(--accent-dark);
  transform: translateY(-1px);
}

.hero-card {
  background: var(--surface);
  border-radius: var(--radius);
  padding: 24px;
  border: 1px solid var(--border);
  box-shadow: var(--shadow);
}

.card-title {
  font-family: var(--font-title);
  margin-bottom: 8px;
}

.card-message {
  font-weight: 600;
  margin-bottom: 12px;
}

.card-meta {
  font-size: 24px;
  color: var(--accent);
  font-weight: 700;
}
```

### Checkpoint de verificacao (Etapa 8)

- O cabecalho vira um bloco destacado.

- O hero aparece em duas colunas.

- O botao principal muda ao passar o mouse.

## 9) CSS: secoes e cards

### O que vamos fazer (Etapa 9)

Estilizar as secoes principais, os cards e o laboratorio.

### Codigo (adicione ao final de styles.css) (Etapa 9)

```css
.section {
  padding: 64px 8vw;
}

.section header h2 {
  font-family: var(--font-title);
  font-size: 32px;
  margin-bottom: 8px;
}

.section header p {
  color: var(--muted);
}

.grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 20px;
  margin-top: 32px;
}

.topic {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 24px;
  box-shadow: var(--shadow);
}

.topic h3 {
  margin-bottom: 12px;
}

.section.alt {
  background: #f2e6d6;
}

.lab {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 24px;
  margin-top: 32px;
}

.lab-card {
  background: var(--surface);
  border-radius: var(--radius);
  padding: 24px;
  border: 1px solid var(--border);
  box-shadow: var(--shadow);
}

.checklist {
  list-style: none;
  display: grid;
  gap: 12px;
  margin-bottom: 16px;
}

.checklist input {
  margin-right: 8px;
}

.progress {
  font-weight: 700;
  color: var(--accent);
}

.note-form {
  display: grid;
  gap: 12px;
}

textarea {
  resize: vertical;
  border-radius: 12px;
  border: 1px solid var(--border);
  padding: 10px;
  font-family: inherit;
}

.note-form button {
  border: none;
  background: var(--ink);
  color: white;
  padding: 10px 16px;
  border-radius: 10px;
  font-weight: 600;
  cursor: pointer;
}

.note-output {
  margin-top: 16px;
  padding: 12px;
  background: #f7efe5;
  border-radius: 12px;
  color: var(--muted);
}

.resource-list {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 16px;
  margin-top: 24px;
}

.resource {
  display: block;
  padding: 16px;
  border-radius: 14px;
  border: 1px dashed var(--accent);
  font-weight: 600;
  background: #fff7ef;
  text-align: center;
}

.site-footer {
  padding: 32px 8vw 48px;
  text-align: center;
  color: var(--muted);
}
```

### Checkpoint de verificacao (Etapa 9)

- Os cards aparecem em grade.

- O laboratorio mostra dois cards lado a lado.

- O rodape esta centralizado.

## 10) CSS: tema escuro

### O que vamos fazer (Etapa 10)

Adicionar uma classe que muda as variaveis para o modo escuro.

### Codigo (adicione ao final de styles.css) (Etapa 10)

```css
body.theme-dark {
  color-scheme: dark;
  --bg: #16120f;
  --surface: #241c18;
  --ink: #f7efe5;
  --muted: #c8b6a6;
  --accent: #f08d49;
  --accent-dark: #e07a35;
  --border: #3d2f27;
  --shadow: 0 20px 50px rgba(0, 0, 0, 0.35);
  background: radial-gradient(circle at top left, #2b1f19 0%, #16120f 70%, #120d0b 100%);
}

body.theme-dark .section.alt {
  background: #201813;
}
```

### Checkpoint de verificacao (Etapa 10)

- Ao adicionar a classe `theme-dark` no `body`, o tema muda.

- O fundo da secao alternativa escurece.

## 11) JavaScript: selecao de elementos

### O que vamos fazer (Etapa 11)

Selecionar elementos que serao manipulados no JS.

### Codigo (cole em script.js) (Etapa 11)

```js
const themeToggle = document.querySelector("#themeToggle"); 
const ctaButton = document.querySelector("#ctaButton"); 
const statusMessage = document.querySelector("#statusMessage"); 
const clock = document.querySelector("#clock"); 
const checklist = document.querySelector("#checklist"); 
const progressText = document.querySelector("#progressText"); 
const noteForm = document.querySelector("#noteForm"); 
const noteOutput = document.querySelector("#noteOutput"); 

const messages = [ 
  "Vamos comecar a pratica!", 
  "Boa, voce acionou o exemplo.", 
  "Explore os elementos e veja o HTML semantico.", 
]; 

let messageIndex = 0; 
```

### Checkpoint de verificacao (Etapa 11)

- Nao aparece nenhum erro de seletor no console.

- O array de mensagens esta definido.

## 12) JavaScript: funcoes de atualizacao

### O que vamos fazer (Etapa 12)

Criar funcoes reutilizaveis para atualizar relogio, progresso e nota.

### Codigo (adicione ao final de script.js) (Etapa 12)

```js
const updateClock = () => { 
  const now = new Date(); 
  const hours = String(now.getHours()).padStart(2, "0"); 
  const minutes = String(now.getMinutes()).padStart(2, "0"); 
  clock.textContent = `${hours}:${minutes}`; 
}; 

const updateProgress = () => { 
  const total = checklist.querySelectorAll("input[name='item']").length; 
  const checked = checklist.querySelectorAll("input[name='item']:checked").length; 
  progressText.textContent = `${checked} de ${total} itens concluidos`; 
}; 

const saveNote = (value) => { 
  const trimmed = value.trim(); 
  if (!trimmed) { 
    noteOutput.textContent = "Escreva algo antes de salvar."; 
    return; 
  } 
  noteOutput.textContent = `Nota salva: ${trimmed}`; 
}; 
```

### Checkpoint de verificacao (Etapa 12)

- As funcoes existem e nao geram erros ao serem chamadas.

## 13) JavaScript: eventos

### O que vamos fazer (Etapa 13)

Conectar botoes e formularios aos eventos do usuario.

### Codigo (adicione ao final de script.js) (Etapa 13)

```js
ctaButton.addEventListener("click", () => { 
  statusMessage.textContent = messages[messageIndex]; 
  messageIndex = (messageIndex + 1) % messages.length; 
}); 

checklist.addEventListener("change", updateProgress); 

noteForm.addEventListener("submit", (event) => { 
  event.preventDefault(); 
  saveNote(noteForm.nota.value); 
  noteForm.reset(); 
}); 

themeToggle.addEventListener("click", () => { 
  const isDark = document.body.classList.toggle("theme-dark"); 
  themeToggle.setAttribute("aria-pressed", String(isDark)); 
}); 
```

### Checkpoint de verificacao (Etapa 13)

- O botao "Ver exemplo" muda a mensagem.

- O checklist atualiza o texto de progresso.

- O botao de tema alterna o modo escuro.

## 14) JavaScript: inicializacao

### O que vamos fazer (Etapa 14)

Definir o estado inicial da pagina e atualizar o relogio periodicamente.

### Codigo (adicione ao final de script.js) (Etapa 14)

```js
updateClock(); 
updateProgress(); 
setInterval(updateClock, 1000 * 30); 
```

### Checkpoint de verificacao (Etapa 14)

- O relogio mostra a hora correta.

- O texto de progresso inicia com 0 de 3.

## 15) Arvore de elementos (visao simplificada)

Use esta arvore para explicar a semantica e a hierarquia do HTML.

```text
html
|-- head
|   |-- meta (charset)
|   |-- meta (viewport)
|   |-- title
|   |-- meta (description)
|   `-- link (styles.css)
`-- body
    |-- header.site-header
    |   |-- a.skip-link
    |   |-- nav.navbar
    |   |   |-- a.logo
    |   |   |-- ul.nav-links
    |   |   |   |-- li > a (Fundamentos)
    |   |   |   |-- li > a (Laboratorio)
    |   |   |   `-- li > a (Recursos)
    |   |   `-- button.theme-toggle
    |   `-- section.hero
    |       |-- div.hero-text
    |       |   |-- p.eyebrow
    |       |   |-- h1
    |       |   |-- p
    |       |   `-- button.primary-cta
    |       `-- aside.hero-card
    |           |-- h2
    |           |-- p#statusMessage
    |           `-- p#clock
    |-- main#conteudo
    |   |-- section#fundamentos
    |   |   |-- header
    |   |   |   |-- h2
    |   |   |   `-- p
    |   |   `-- div.grid
    |   |       |-- article.topic (HTML semantico)
    |   |       |-- article.topic (CSS organizado)
    |   |       `-- article.topic (JS com objetivo)
    |   |-- section#laboratorio
    |   |   |-- header
    |   |   `-- div.lab
    |   |       |-- article.lab-card (Checklist)
    |   |       `-- article.lab-card (Notas)
    |   `-- section#recursos
    |       |-- header
    |       `-- div.resource-list
    |           |-- a.resource (HTML)
    |           |-- a.resource (CSS)
    |           `-- a.resource (JavaScript)
    |-- footer.site-footer
    `-- script (script.js)
```

### Checkpoint de verificacao (Etapa 15)

- A arvore corresponde ao HTML escrito.

- Os elementos principais usam tags semanticas corretas.

## 16) Como testar no navegador

1) Abra o arquivo `index.html` no navegador.

2) Clique em "Ver exemplo" para mudar o texto.

3) Marque os itens do checklist.

4) Escreva uma nota e clique em "Salvar".

5) Clique em "Alternar tema" para ver o modo escuro.

6) Recarregue a pagina e observe quais informacoes sao reiniciadas.

### Checkpoint de verificacao (Etapa 16)

- Todas as interacoes respondem como esperado.

- Nenhum erro aparece no console do navegador.

## 17) Exercicios sugeridos

- Tornar o layout responsivo com `@media`.

- Adicionar uma nova secao com conteudo proprio.

- Alterar a paleta de cores mantendo contraste.

- Criar um botao para limpar a nota salva.

- Mostrar uma mensagem quando todos os itens do checklist estiverem marcados.

### Checkpoint de verificacao (exercicios sugeridos)

- Escolha pelo menos um exercicio para implementar.

- Descreva o que mudou e por que mudou.

---
