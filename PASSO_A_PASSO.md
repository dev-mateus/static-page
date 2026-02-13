# Passo a passo: pagina estatica simples com HTML, CSS e JS

Este guia cria a pagina aos poucos. Em cada etapa, voce adiciona um trecho de codigo, entende o motivo e testa no navegador. Ao final, a pagina estara completa.

## 1) Estrutura do projeto

### Objetivo (Etapa 1)

Criar a pasta do projeto e os arquivos base.

### Por que isso existe (Etapa 1)

Separar responsabilidades evita confusao: HTML e estrutura, CSS e aparencia, JS e comportamento.

### Como usar (Etapa 1)

Crie a pasta do projeto e, dentro dela, os arquivos base:

- index.html
- styles.css
- script.js

### Checkpoint de verificacao (Etapa 1)

- A pasta do projeto existe e tem os tres arquivos base.
- Os arquivos estao vazios ou prontos para receber o codigo.

## 2) HTML: esqueleto do documento

### Objetivo (Etapa 2)

Criar o esqueleto minimo do HTML.

### Por que isso existe (Etapa 2)

O navegador precisa do `doctype`, da raiz `html` e das areas `head` e `body` para interpretar corretamente o documento.

### Como usar (Etapa 2)

Cole este codigo em index.html:

### Codigo (Etapa 2)

```html
<!doctype html>
<html lang="pt-BR">
  <head>
  </head>
  <body>
  </body>
</html>
```

### Checkpoint de verificacao (Etapa 2)

- O arquivo abre no navegador sem erros.
- A pagina aparece em branco, como esperado.

## 3) HTML: metadados do head

### Objetivo (Etapa 3)

Adicionar metadados basicos e o link do CSS.

### Por que isso existe (Etapa 3)

Metadados definem codificacao, escala em dispositivos e descricao. O link do CSS conecta o arquivo de estilos.

### Como usar (Etapa 3)

Substitua o conteudo do `head` pelo bloco abaixo:

### Codigo (Etapa 3)

```html
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Fundamentos de Paginas Web</title>
    <meta name="description" content="Pagina estatica simples para praticar HTML, CSS e JavaScript." />
    <link rel="stylesheet" href="styles.css" />
  </head>
```

### Checkpoint de verificacao (Etapa 3)

- O titulo aparece na aba do navegador.
- O arquivo CSS esta linkado (mesmo vazio, o link deve existir).

## 4) HTML: header com logo

### Objetivo (Etapa 4)

Adicionar o cabecalho e a logo.

### Por que isso existe (Etapa 4)

O header organiza a navegacao principal e reforca a identidade da pagina.

### Como usar (Etapa 4)

Dentro do `body`, adicione este bloco:

### Codigo (Etapa 4)

```html
  <header class="site-header">
    <a class="skip-link" href="#conteudo">Pular para o conteudo</a>
    <nav class="navbar" aria-label="Navegacao principal">
      <a class="logo" href="#">
        <span aria-hidden="true">&#9872;</span>
        <span class="logo-text">Web 101</span>
      </a>
    </nav>
  </header>
```

### Checkpoint de verificacao (Etapa 4)

- O cabecalho aparece no topo da pagina.
- A logo aparece ao lado do texto "Web 101".

## 5) HTML: links do menu e botao de tema

### Objetivo (Etapa 5)

Completar a navegacao principal com links e o botao de tema.

### Por que isso existe (Etapa 5)

Links permitem navegar dentro da pagina e o botao controla o modo escuro via JavaScript.

### Como usar (Etapa 5)

Substitua o bloco de navegacao pelo trecho completo abaixo:

### Codigo (Etapa 5)

```html
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
```

### Checkpoint de verificacao (Etapa 5)

- Os tres links de navegacao estao visiveis.
- O botao "Alternar tema" esta presente.

## 6) HTML: hero com texto principal

### Objetivo (Etapa 6)

Adicionar a area de destaque com titulo e texto introdutorio.

### Por que isso existe (Etapa 6)

O hero apresenta o objetivo da pagina e guia o usuario para a acao principal.

### Como usar (Etapa 6)

Dentro do `header`, logo depois do `</nav>`, adicione:

### Codigo (Etapa 6)

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
    </section>
```

### Checkpoint de verificacao (Etapa 6)

- O titulo principal e o botao "Ver exemplo" aparecem.

## 7) HTML: hero com card lateral

### Objetivo (Etapa 7)

Adicionar o card lateral que exibira o status e o relogio.

### Por que isso existe (Etapa 7)

O card mostra informacoes dinamicas atualizadas pelo JavaScript.

### Como usar (Etapa 7)

Substitua a section do hero pelo bloco completo abaixo:

### Codigo (Etapa 7)

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

### Checkpoint de verificacao (Etapa 7)

- O card lateral aparece com texto de status e relogio.

## 8) HTML: main e cabecalho de fundamentos

### Objetivo (Etapa 8)

Criar a area principal e a primeira secao.

### Por que isso existe (Etapa 8)

O `main` identifica o conteudo principal da pagina, e a secao organiza o tema.

### Como usar (Etapa 8)

Depois do `</header>`, adicione:

### Codigo (Etapa 8)

```html
  <main id="conteudo">
    <section id="fundamentos" class="section">
      <header>
        <h2>Fundamentos essenciais</h2>
        <p>Organize o conteudo com tags que fazem sentido.</p>
      </header>
    </section>
  </main>
```

### Checkpoint de verificacao (Etapa 8)

- A secao de fundamentos aparece abaixo do header.

## 9) HTML: grid de fundamentos

### Objetivo (Etapa 9)

Adicionar os tres artigos de fundamentos.

### Por que isso existe (Etapa 9)

Artigos separam topicos relacionados e deixam a leitura mais clara.

### Como usar (Etapa 9)

Dentro da secao de fundamentos, logo abaixo do header, adicione:

### Codigo (Etapa 9)

```html
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
```

### Checkpoint de verificacao (Etapa 9)

- Os tres artigos de fundamentos aparecem.

## 10) HTML: secao de laboratorio

### Objetivo (Etapa 10)

Criar a secao de laboratorio para interacoes praticas.

### Por que isso existe (Etapa 10)

Essa secao separa exercicios praticos do conteudo teorico.

### Como usar (Etapa 10)

Depois da secao de fundamentos, adicione:

### Codigo (Etapa 10)

```html
    <section id="laboratorio" class="section alt">
      <header>
        <h2>Laboratorio pratico</h2>
        <p>Experimente os exemplos e observe o comportamento no navegador.</p>
      </header>
      <div class="lab">
      </div>
    </section>
```

### Checkpoint de verificacao (Etapa 10)

- A secao de laboratorio aparece com o titulo e o texto introdutorio.

## 11) HTML: checklist do laboratorio

### Objetivo (Etapa 11)

Adicionar o checklist com itens da aula.

### Por que isso existe (Etapa 11)

O checklist sera usado para demonstrar eventos e contagem no JavaScript.

### Como usar (Etapa 11)

Dentro de `<div class="lab">`, adicione:

### Codigo (Etapa 11)

```html
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
```

### Checkpoint de verificacao (Etapa 11)

- O checklist aparece com tres itens.
- O texto de progresso aparece abaixo da lista.

## 12) HTML: notas rapidas

### Objetivo (Etapa 12)

Adicionar o formulario de notas e o bloco de resultado.

### Por que isso existe (Etapa 12)

O formulario permite exercitar envio de dados e atualizacao do DOM.

### Como usar (Etapa 12)

Ainda dentro de `<div class="lab">`, adicione este segundo card:

### Codigo (Etapa 12)

```html
        <article class="lab-card">
          <h3>Notas rapidas</h3>
          <form class="note-form" id="noteForm">
            <label for="nota">Escreva uma nota para revisar depois</label>
            <textarea id="nota" name="nota" rows="4" placeholder="Ex.: revisar seletores CSS"></textarea>
            <button type="submit">Salvar nota</button>
          </form>
          <p class="note-output" id="noteOutput" aria-live="polite">Nenhuma nota ainda.</p>
        </article>
```

### Checkpoint de verificacao (Etapa 12)

- O formulario de notas aparece ao lado do checklist.
- O texto "Nenhuma nota ainda." aparece abaixo do formulario.

## 13) HTML: secao de recursos

### Objetivo (Etapa 13)

Criar a secao com links de estudo.

### Por que isso existe (Etapa 13)

Ajuda a direcionar o aluno para documentacao oficial.

### Como usar (Etapa 13)

Depois da secao de laboratorio, adicione:

### Codigo (Etapa 13)

```html
    <section id="recursos" class="section">
      <header>
        <h2>Recursos de estudo</h2>
        <p>Links de referencia para aprofundar o conteudo.</p>
      </header>
      <div class="resource-list">
      </div>
    </section>
```

### Checkpoint de verificacao (Etapa 13)

- A secao de recursos aparece com titulo e descricao.

## 14) HTML: links de recursos

### Objetivo (Etapa 14)

Adicionar os tres links de documentacao.

### Por que isso existe (Etapa 14)

Links externos precisam de `noopener noreferrer` para seguranca.

### Como usar (Etapa 14)

Dentro de `<div class="resource-list">`, adicione:

### Codigo (Etapa 14)

```html
        <a class="resource" href="https://developer.mozilla.org/pt-BR/docs/Web/HTML" target="_blank" rel="noopener noreferrer">
          Documentacao HTML
        </a>
        <a class="resource" href="https://developer.mozilla.org/pt-BR/docs/Web/CSS" target="_blank" rel="noopener noreferrer">
          Guia de CSS
        </a>
        <a class="resource" href="https://developer.mozilla.org/pt-BR/docs/Web/JavaScript" target="_blank" rel="noopener noreferrer">
          JavaScript para iniciantes
        </a>
```

### Checkpoint de verificacao (Etapa 14)

- Os tres links aparecem na secao de recursos.

## 15) HTML: rodape e script

### Objetivo (Etapa 15)

Finalizar a pagina e carregar o JavaScript.

### Por que isso existe (Etapa 15)

O rodape fecha o documento, e o script carrega o comportamento interativo.

### Como usar (Etapa 15)

Depois do `</main>`, adicione:

### Codigo (Etapa 15)

```html
  <footer class="site-footer">
    <p>Prof. Web | Fundamentos de paginas web</p>
    <p>Exercicio: tornar a pagina responsiva na proxima aula.</p>
  </footer>

  <script src="script.js" defer></script>
```

### Checkpoint de verificacao (Etapa 15)

- O rodape aparece no final da pagina.
- O arquivo script.js esta referenciado.

## 16) CSS: variaveis e estilos globais

### Objetivo (Etapa 16)

Definir variaveis e estilos globais.

### Por que isso existe (Etapa 16)

Variaveis evitam repeticao e facilitam ajustes futuros.

### Como usar (Etapa 16)

Cole este bloco em styles.css:

### Codigo (Etapa 16)

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
```

### Checkpoint de verificacao (Etapa 16)

- O fundo e a tipografia mudam ao recarregar a pagina.

## 17) CSS: elementos basicos

### Objetivo (Etapa 17)

Padronizar imagens e links.

### Por que isso existe (Etapa 17)

Imagens responsivas e links sem sublinhado mantem a consistencia visual.

### Como usar (Etapa 17)

Adicione ao final de styles.css:

### Codigo (Etapa 17)

```css
img {
  max-width: 100%;
  display: block;
}

a {
  color: inherit;
  text-decoration: none;
}
```

### Checkpoint de verificacao (Etapa 17)

- Nao ha sublinhado nos links.

## 18) CSS: header e navbar

### Objetivo (Etapa 18)

Estilizar o cabecalho e a barra de navegacao.

### Por que isso existe (Etapa 18)

Um header com destaque melhora a hierarquia visual.

### Como usar (Etapa 18)

Adicione ao final de styles.css:

### Codigo (Etapa 18)

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
```

### Checkpoint de verificacao (Etapa 18)

- O cabecalho vira um bloco destacado.
- A logo aparece alinhada com o texto.

## 19) CSS: links e botao do menu

### Objetivo (Etapa 19)

Estilizar os links do menu e o botao de tema.

### Por que isso existe (Etapa 19)

Feedback visual melhora a navegacao e deixa a interface mais clara.

### Como usar (Etapa 19)

Adicione ao final de styles.css:

### Codigo (Etapa 19)

```css
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
```

### Checkpoint de verificacao (Etapa 19)

- Os links mudam de fundo ao passar o mouse.
- O botao de tema aparece com borda arredondada.

## 20) CSS: layout do hero

### Objetivo (Etapa 20)

Criar o layout em duas colunas do hero.

### Por que isso existe (Etapa 20)

Separar texto e card melhora a leitura e o foco.

### Como usar (Etapa 20)

Adicione ao final de styles.css:

### Codigo (Etapa 20)

```css
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
```

### Checkpoint de verificacao (Etapa 20)

- O hero aparece em duas colunas.
- O botao principal tem destaque e hover.

## 21) CSS: card do hero

### Objetivo (Etapa 21)

Estilizar o card lateral do hero.

### Por que isso existe (Etapa 21)

O card precisa parecer um bloco separado e legivel.

### Como usar (Etapa 21)

Adicione ao final de styles.css:

### Codigo (Etapa 21)

```css
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

### Checkpoint de verificacao (Etapa 21)

- O card tem fundo branco e sombra.
- O relogio fica em destaque.

## 22) CSS: secoes e grid de fundamentos

### Objetivo (Etapa 22)

Estilizar as secoes e a grade de fundamentos.

### Por que isso existe (Etapa 22)

Uma grade consistente melhora a leitura em blocos.

### Como usar (Etapa 22)

Adicione ao final de styles.css:

### Codigo (Etapa 22)

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
```

### Checkpoint de verificacao (Etapa 22)

- Os artigos aparecem em grade.
- Cada card tem borda e sombra.

## 23) CSS: laboratorio e checklist

### Objetivo (Etapa 23)

Estilizar a secao de laboratorio e o checklist.

### Por que isso existe (Etapa 23)

Os cards de laboratorio precisam se destacar do restante da pagina.

### Como usar (Etapa 23)

Adicione ao final de styles.css:

### Codigo (Etapa 23)

```css
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
```

### Checkpoint de verificacao (Etapa 23)

- A secao de laboratorio tem fundo diferenciado.
- Os dois cards aparecem lado a lado.

## 24) CSS: formulario e nota

### Objetivo (Etapa 24)

Estilizar formulario, textarea e area de nota.

### Por que isso existe (Etapa 24)

Formularios precisam de espaco e legibilidade para uso confortavel.

### Como usar (Etapa 24)

Adicione ao final de styles.css:

### Codigo (Etapa 24)

```css
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
```

### Checkpoint de verificacao (Etapa 24)

- O textarea tem bordas arredondadas.
- O bloco de nota tem fundo claro.

## 25) CSS: recursos e rodape

### Objetivo (Etapa 25)

Estilizar os links de recursos e o rodape.

### Por que isso existe (Etapa 25)

Os recursos precisam de destaque visual, e o rodape encerra a pagina com equilibrio.

### Como usar (Etapa 25)

Adicione ao final de styles.css:

### Codigo (Etapa 25)

```css
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

### Checkpoint de verificacao (Etapa 25)

- Os links de recursos aparecem em caixas.
- O rodape fica centralizado.

## 26) CSS: tema escuro

### Objetivo (Etapa 26)

Adicionar o tema escuro usando variaveis.

### Por que isso existe (Etapa 26)

Alternar o tema com variaveis simplifica a manutencao.

### Como usar (Etapa 26)

Adicione ao final de styles.css:

### Codigo (Etapa 26)

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

### Checkpoint de verificacao (Etapa 26)

- Ao adicionar a classe `theme-dark` no `body`, o tema muda.

## 27) JavaScript: selecao de elementos

### Objetivo (Etapa 27)

Selecionar elementos do DOM para uso no script.

### Por que isso existe (Etapa 27)

Sem referencias aos elementos, o JS nao consegue alterar a pagina.

### Como usar (Etapa 27)

Cole este bloco em script.js:

### Codigo (Etapa 27)

```js
const themeToggle = document.querySelector("#themeToggle");
const ctaButton = document.querySelector("#ctaButton");
const statusMessage = document.querySelector("#statusMessage");
const clock = document.querySelector("#clock");
const checklist = document.querySelector("#checklist");
const progressText = document.querySelector("#progressText");
const noteForm = document.querySelector("#noteForm");
const noteOutput = document.querySelector("#noteOutput");
```

### Checkpoint de verificacao (Etapa 27)

- Nao aparece nenhum erro de seletor no console.

## 28) JavaScript: mensagens do CTA

### Objetivo (Etapa 28)

Criar o conjunto de mensagens e o indice atual.

### Por que isso existe (Etapa 28)

Permite alternar mensagens sem repetir codigo.

### Como usar (Etapa 28)

Adicione ao final de script.js:

### Codigo (Etapa 28)

```js
const messages = [
  "Vamos comecar a pratica!",
  "Boa, voce acionou o exemplo.",
  "Explore os elementos e veja o HTML semantico.",
];

let messageIndex = 0;
```

### Checkpoint de verificacao (Etapa 28)

- O array de mensagens esta definido.

## 29) JavaScript: relogio e progresso

### Objetivo (Etapa 29)

Criar funcoes para atualizar relogio e progresso.

### Por que isso existe (Etapa 29)

Funcoes reutilizaveis deixam o codigo mais simples de manter.

### Como usar (Etapa 29)

Adicione ao final de script.js:

### Codigo (Etapa 29)

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
```

### Checkpoint de verificacao (Etapa 29)

- As funcoes existem e nao geram erros ao serem chamadas.

## 30) JavaScript: salvar nota

### Objetivo (Etapa 30)

Criar a funcao que exibe a nota salva.

### Por que isso existe (Etapa 30)

A funcao centraliza a validacao e a atualizacao do texto.

### Como usar (Etapa 30)

Adicione ao final de script.js:

### Codigo (Etapa 30)

```js
const saveNote = (value) => {
  const trimmed = value.trim();
  if (!trimmed) {
    noteOutput.textContent = "Escreva algo antes de salvar.";
    return;
  }
  noteOutput.textContent = `Nota salva: ${trimmed}`;
};
```

### Checkpoint de verificacao (Etapa 30)

- A funcao `saveNote` existe e valida texto vazio.

## 31) JavaScript: eventos

### Objetivo (Etapa 31)

Conectar botoes e formulario aos eventos do usuario.

### Por que isso existe (Etapa 31)

Eventos tornam a interface interativa.

### Como usar (Etapa 31)

Adicione ao final de script.js:

### Codigo (Etapa 31)

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

### Checkpoint de verificacao (Etapa 31)

- O botao "Ver exemplo" muda a mensagem.
- O checklist atualiza o progresso.
- O botao de tema alterna o modo escuro.

## 32) JavaScript: inicializacao

### Objetivo (Etapa 32)

Definir o estado inicial e atualizar o relogio periodicamente.

### Por que isso existe (Etapa 32)

Garante que a interface comeca consistente.

### Como usar (Etapa 32)

Adicione ao final de script.js:

### Codigo (Etapa 32)

```js
updateClock();
updateProgress();
setInterval(updateClock, 1000 * 30);
```

### Checkpoint de verificacao (Etapa 32)

- O relogio mostra a hora correta.
- O texto de progresso inicia com 0 de 3.

## 33) Arvore de elementos

### Objetivo (Etapa 33)

Visualizar a hierarquia semantica do HTML.

### Por que isso existe (Etapa 33)

Uma arvore ajuda a explicar estrutura e responsabilidades das tags.

### Como usar (Etapa 33)

Use a arvore abaixo para explicar o DOM:

### Codigo (Etapa 33)

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

### Checkpoint de verificacao (Etapa 33)

- A arvore corresponde ao HTML escrito.

## 34) Teste da pagina

### Objetivo (Etapa 34)

Verificar se tudo esta funcionando.

### Por que isso existe (Etapa 34)

Testes manuais ajudam a encontrar erros antes de ensinar.

### Como usar (Etapa 34)

Abra index.html no navegador e realize:

- Clique em "Ver exemplo".
- Marque os itens do checklist.
- Salve uma nota.
- Alterne o tema.

### Checkpoint de verificacao (Etapa 34)

- Todas as interacoes respondem como esperado.
- Nenhum erro aparece no console do navegador.

## 35) Exercicios sugeridos

### Objetivo (Etapa 35)

Propor melhorias para aprofundar o aprendizado.

### Por que isso existe (Etapa 35)

Exercicios estimulam autonomia e pratica.

### Como usar (Etapa 35)

Escolha pelo menos um exercicio:

- Tornar o layout responsivo com `@media`.
- Adicionar uma nova secao com conteudo proprio.
- Alterar a paleta de cores mantendo contraste.
- Criar um botao para limpar a nota salva.
- Mostrar uma mensagem quando todos os itens do checklist estiverem marcados.

### Checkpoint de verificacao (Etapa 35)

- Descreva o que mudou e por que mudou.
