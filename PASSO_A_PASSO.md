# Passo a passo: pagina estatica simples com HTML, CSS e JS

Este guia cria a pagina **tijolo por tijolo**. Cada etapa constrói uma parte do HTML, adiciona classes semanticas, e aplica CSS para estilizar. Assim, voce ve o progresso visual em tempo real e entende como cada elemento contribui para a pagina final.

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

## 4.1) HTML: header e navbar - Estrutura sem classes

### Objetivo (Etapa 4.1)

Criar a estrutura do cabecalho com navbar e logo usando apenas tags HTML semanticas.

### Por que isso existe (Etapa 4.1)

Comecamos com a estrutura pura, sem classes. Assim, voce entende a hierarquia das tags antes de estilizar.

### Como usar (Etapa 4.1)

Dentro do `body`, adicione este bloco:

### Codigo (Etapa 4.1)

```html
  <header>
    <a href="#conteudo">Pular para o conteudo</a>
    <nav aria-label="Navegacao principal">
      <a href="#">Web 101</a>
      <ul>
        <li><a href="#fundamentos">Fundamentos</a></li>
        <li><a href="#laboratorio">Laboratorio</a></li>
        <li><a href="#recursos">Recursos</a></li>
      </ul>
      <button type="button">Alternar tema</button>
    </nav>
  </header>
```

### Checkpoint de verificacao (Etapa 4.1)

- O cabecalho aparece no topo com elementos em linha.
- Os tres links de navegacao estao visiveis.
- O botao "Alternar tema" esta presente.

## 4.2) HTML: header e navbar - Adicionar classes

### Objetivo (Etapa 4.2)

Adicionar classes semanticas ao header para permitir estilizacao.

### Por que isso existe (Etapa 4.2)

Com classes, conseguimos direcionar CSS para elementos especificos sem afetar toda a pagina.

### Como usar (Etapa 4.2)

Substitua o bloco do header pelo codigo com classes:

### Codigo (Etapa 4.2)

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

### Checkpoint de verificacao (Etapa 4.2)

- As classes foram adicionadas.
- A pagina continua visualmente igual (sem CSS ainda).
- Nao ha erros no console.

## 4.3) CSS: estilizar header e navbar

### Objetivo (Etapa 4.3)

Aplicar CSS para estilizar header, navbar e seus componentes internos.

### Por que isso existe (Etapa 4.3)

CSS transforma o HTML bruto em uma interface visualmente atrativa e organizada.

### Como usar (Etapa 4.3)

Cole este bloco em styles.css (comece com variaveis primeiro):

### Codigo (Etapa 4.3)

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

.site-header {
  padding: 24px 8vw 48px;
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
```

### Checkpoint de verificacao (Etapa 4.3)

- O header aparece com fundo e espacamento apropriado.
- A navbar tem card com borda e sombra.
- A logo aparece alinhada no canto esquerdo.
- Os links estao centralizados e mudam de fundo ao passar mouse.
- O botao de tema tem borda e esta alinhado a direita.

## 5) HTML: seção hero com texto e card

### Objetivo (Etapa 5)

Adicionar a area de destaque (hero) com titulo, texto introdutorio e card lateral.

### Por que isso existe (Etapa 5)

O hero e um ponto focal importante da pagina. Apresenta a proposta de valor e chama o usuario para a acao.

### Como usar (Etapa 5)

Dentro do `body`, logo apos `</header>`, adicione:

### Codigo (Etapa 5)

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

### Checkpoint de verificacao (Etapa 5)

- O titulo principal aparece com tamanho destacado.
- O botao "Ver exemplo" esta presente.
- O card lateral aparece com texto "Status da aula".

## 5.1) CSS: estilizar hero

### Objetivo (Etapa 5.1)

Aplicar CSS para criar o layout em duas colunas e estilizar o card.

### Por que isso existe (Etapa 5.1)

O layout de duas colunas melhora a leitura e separa visualmente texto da informacao dinamica.

### Como usar (Etapa 5.1)

Adicione ao final de styles.css:

### Codigo (Etapa 5.1)

```css
.hero {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  gap: 32px;
  margin: 40px 8vw;
  align-items: center;
  padding: 0;
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

### Checkpoint de verificacao (Etapa 5.1)

- O hero aparece em duas colunas lado a lado.
- O card lateral tem borda, sombra e espacamento.
- O botao principal muda de cor ao passar o mouse.
- O titulo aparece em tamanho grande e fonte de titulo.

## 6) HTML: main com as tres secoes de conteudo

### Objetivo (Etapa 6)

Criar a area principal com tres secoes: Fundamentos, Laboratorio e Recursos.

### Por que isso existe (Etapa 6)

A tag `main` semanticamente identifica o conteudo principal. As tres secoes organizam temas distintos.

### Como usar (Etapa 6)

Depois do `</section>` do hero, adicione:

### Codigo (Etapa 6)

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

### Checkpoint de verificacao (Etapa 6)

- As tres secoes aparecem abaixo do hero.
- Os artigos de fundamentos estao visiveis.
- O checklist, notas e links aparecem na pagina.

## 6.1) CSS: estilizar as secoes e conteudo principal

### Objetivo (Etapa 6.1)

Aplicar CSS para estilizar as tres secoes, grades e cards.

### Por que isso existe (Etapa 6.1)

CSS organiza o conteudo em blocos visuais consistentes e melhor legibilidade.

### Como usar (Etapa 6.1)

Adicione ao final de styles.css:

### Codigo (Etapa 6.1)

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
```

### Checkpoint de verificacao (Etapa 6.1)

- Os artigos de fundamentos aparecem em grid de 3 colunas.
- A secao de laboratorio tem fundo diferenciado.
- Os dois cards (checklist e notas) aparecem lado a lado.
- Os tres links de recursos aparecem em caixas com borda tracejada.

## 7) HTML: rodape e script

### Objetivo (Etapa 7)

Adicionar o rodape e referenciar o arquivo JavaScript.

### Por que isso existe (Etapa 7)

O rodape finaliza a pagina semanticamente. O script ativa as interacoes dinamicas.

### Como usar (Etapa 7)

Depois do `</main>`, adicione:

### Codigo (Etapa 7)

```html
  <footer class="site-footer">
    <p>Prof. Web | Fundamentos de paginas web</p>
    <p>Exercicio: tornar a pagina responsiva na proxima aula.</p>
  </footer>

  <script src="script.js" defer></script>
```

### Checkpoint de verificacao (Etapa 7)

- O rodape aparece no final da pagina.
- Nao ha erros de referencia ao script.

## 7.1) CSS: estilizar rodape e tema escuro

### Objetivo (Etapa 7.1)

Aplicar CSS ao rodape e adicionar variacoes de tema escuro.

### Por que isso existe (Etapa 7.1)

O rodape fecha a pagina com equilibrio visual. O tema escuro permite flexibilidade de uso.

### Como usar (Etapa 7.1)

Adicione ao final de styles.css:

### Codigo (Etapa 7.1)

```css
.site-footer {
  padding: 32px 8vw 48px;
  text-align: center;
  color: var(--muted);
}

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

### Checkpoint de verificacao (Etapa 7.1)

- O rodape aparece centralizado e em cor discreta.
- (CSS do tema escuro esta pronto; sera ativado por JavaScript).

## 8) JavaScript: selecionar elementos do DOM

### Objetivo (Etapa 8)

Capturar referencias aos elementos HTML que serao manipulados.

### Por que isso existe (Etapa 8)

Sem referencias, JavaScript nao consegue alterar a pagina. Seletores sao o primeiro passo.

### Como usar (Etapa 8)

Cole este bloco em script.js:

### Codigo (Etapa 8)

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

### Checkpoint de verificacao (Etapa 8)

- Abra o console do navegador (F12).
- Nao aparecem erros de seletor (ex.: "Cannot read property").

## 9) JavaScript: definir mensagens e variaveis

### Objetivo (Etapa 9)

Criar um array de mensagens e indice para alternar entre elas.

### Por que isso existe (Etapa 9)

Arrays e variaveis permitem comportamento dinamico sem duplicar codigo.

### Como usar (Etapa 9)

Adicione ao final de script.js:

### Codigo (Etapa 9)

```js
const messages = [
  "Vamos comecar a pratica!",
  "Boa, voce acionou o exemplo.",
  "Explore os elementos e veja o HTML semantico.",
];

let messageIndex = 0;
```

### Checkpoint de verificacao (Etapa 9)

- Array esta definido.
- Nao ha erros de sintaxe no console.

## 10) JavaScript: criar funcoes reutilizaveis

### Objetivo (Etapa 10)

Definir funcoes para atualizar relogio, progresso e salvar notas.

### Por que isso existe (Etapa 10)

Funcoes reutilizaveis deixam o codigo limpo e facil de manter.

### Como usar (Etapa 10)

Adicione ao final de script.js:

### Codigo (Etapa 10)

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

### Checkpoint de verificacao (Etapa 10)

- Funcoes estao definidas.
- Nao ha erros no console.

## 11) JavaScript: conectar eventos aos elementos

### Objetivo (Etapa 11)

Adicionar listeners de eventos para interacoes do usuario.

### Por que isso existe (Etapa 11)

Eventos conectam HTML, CSS e JavaScript em uma experiencia interativa.

### Como usar (Etapa 11)

Adicione ao final de script.js:

### Codigo (Etapa 11)

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

### Checkpoint de verificacao (Etapa 11)

- Clique em "Ver exemplo" e veja mensagens diferentes aparecerem.
- Marque itens do checklist e veja o progresso mudar.
- Escreva uma nota, envie e veja a nota ser exibida.
- Clique em "Alternar tema" e veja o fundo mudar para escuro.

## 12) JavaScript: inicializar estado e loops

### Objetivo (Etapa 12)

Chamar funcoes de inicializacao e configurar atualizacoes periodicas.

### Por que isso existe (Etapa 12)

Inicializacao garante que a pagina comeca em estado consistente. Loops periodicos atualizam dados.

### Como usar (Etapa 12)

Adicione ao final de script.js:

### Codigo (Etapa 12)

```js
updateClock();
updateProgress();
setInterval(updateClock, 1000 * 30);
```

### Checkpoint de verificacao (Etapa 12)

- O relogio mostra a hora correta ao carregar a pagina.
- O texto de progresso inicia com "0 de 3 itens concluidos".
- O relogio atualiza a cada 30 segundos automaticamente.

## 13) Arvore de elementos (DOM)

### Objetivo (Etapa 13)

Visualizar a hierarquia completa dos elementos HTML.

### Por que isso existe (Etapa 13)

Uma arvore ajuda a entender a estrutura e as relacoes entre elementos.

### Como usar (Etapa 13)

Use a arvore abaixo como referencia:

### Codigo (Etapa 13)

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
    |   `-- nav.navbar
    |       |-- a.logo
    |       |-- ul.nav-links
    |       |   |-- li > a (Fundamentos)
    |       |   |-- li > a (Laboratorio)
    |       |   `-- li > a (Recursos)
    |       `-- button.theme-toggle
    |-- section.hero
    |   |-- div.hero-text
    |   |   |-- p.eyebrow
    |   |   |-- h1#titulo-principal
    |   |   |-- p
    |   |   `-- button.primary-cta
    |   `-- aside.hero-card
    |       |-- h2.card-title
    |       |-- p#statusMessage
    |       `-- p#clock
    |-- main#conteudo
    |   |-- section#fundamentos.section
    |   |   |-- header
    |   |   |   |-- h2
    |   |   |   `-- p
    |   |   `-- div.grid
    |   |       |-- article.topic (HTML semantico)
    |   |       |-- article.topic (CSS organizado)
    |   |       `-- article.topic (JS com objetivo)
    |   |-- section#laboratorio.section.alt
    |   |   |-- header
    |   |   |   |-- h2
    |   |   |   `-- p
    |   |   `-- div.lab
    |   |       |-- article.lab-card (Checklist)
    |   |       |   |-- h3
    |   |       |   |-- ul.checklist#checklist
    |   |       |   `-- p.progress#progressText
    |   |       `-- article.lab-card (Notas)
    |   |           |-- h3
    |   |           |-- form.note-form#noteForm
    |   |           `-- p.note-output#noteOutput
    |   `-- section#recursos.section
    |       |-- header
    |       |   |-- h2
    |       |   `-- p
    |       `-- div.resource-list
    |           |-- a.resource (HTML)
    |           |-- a.resource (CSS)
    |           `-- a.resource (JavaScript)
    |-- footer.site-footer
    `-- script (script.js)
```

### Checkpoint de verificacao (Etapa 13)

- A arvore corresponde ao seu HTML.
- Voce consegue rastrear um elemento pela hierarquia usando DevTools (F12).

## 14) Teste completo da pagina

### Objetivo (Etapa 14)

Validar que todas as funcionalidades funcionam corretamente.

### Por que isso existe (Etapa 14)

Testes manuais ajudam a encontrar erros e confirmar que tudo esta integrado.

### Como usar (Etapa 14)

Abra index.html no navegador e realize cada teste:

1. **Clique no botao "Ver exemplo"**: Veja tres mensagens diferentes aparecerem.
2. **Marque os checkboxes**: Veja o progresso atualizar para "1 de 3", "2 de 3", etc.
3. **Escreva e envie uma nota**: Veja o texto aparecer como "Nota salva: [seu texto]".
4. **Alterne o tema**: Clique em "Alternar tema" e veja o fundo mudar para escuro e cores ajustarem.
5. **Verifique o relogio**: Veja a hora no card atualizar.

### Checkpoint de verificacao (Etapa 14)

- Todas as interacoes respondem como esperado.
- Nenhum erro aparece no console (F12 > Console).
- O tema escuro e claro funcionam corretamente.
- A pagina e responsiva e legivel em seu navegador.

## 15) Exercicios sugeridos

### Objetivo (Etapa 15)

Propor desafios praticos para aprofundar o aprendizado.

### Por que isso existe (Etapa 15)

Exercicios estimulam autonomia, pratica e consolidacao do conhecimento.

### Como usar (Etapa 15)

Escolha pelo menos um exercicio e execute:

**Nivel 1 (facil)**:

- Alterar a paleta de cores mantendo o contraste.
- Adicionar um novo artigo na secao de Fundamentos.
- Mudar o emoji na logo para outro de sua escolha.

**Nivel 2 (intermediario)**:

- Tornar o layout responsivo com `@media` para celular.
- Criar um botao para limpar a nota salva.
- Adicionar uma nova secao com conteudo proprio.

**Nivel 3 (avancado)**:

- Salvar a nota em localStorage para persistencia.
- Mostrar uma mensagem especial quando todos os checkboxes forem marcados.
- Criar alternancia de tema com icones (sol e lua).

### Checkpoint de verificacao (Etapa 15)

- Descreva qual exercicio escolheu e por que.
- Mostre o resultado funcionando.
- Explique que partes do codigo HTML, CSS e JavaScript foram modificadas.
