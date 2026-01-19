# Documentação StarCode - Guia de Conteúdo

Este guia orienta como substituir os placeholders por conteúdos reais, gerenciar itens da equipe e do portfólio, e realizar ajustes básicos de estilo.

---

## 🖼️ Como Gerenciar Imagens

Todas as imagens devem ser colocadas na pasta `ASSETS/`.

### 1. Logo Oficial

- Substitua `ASSETS/logo.png` pela sua logo oficial. (linha 27 e linha 423 no `index.html`)
- **Dica**: Utilize o formato PNG com fundo transparente para um visual mais profissional.

### 2. Fotos da Equipe e Prints de Projetos

Agora o código já possui as tags `<img>` prontas. Para alterar as fotos, basta mudar o caminho no atributo `src`:

1. **Equipe**: No `index.html`, localize a tag `<img>` dentro de `.team-photo` (linha 247 em diante) e altere o `src`:
   ```html
   <img src="ASSETS/fotos-equipe/sua-foto.jpg" alt="Nome do Membro" />
   ```
   _Nota: O site agora utiliza molduras maiores (240x320px). Recomenda--se fotos em proporção retrato 3:4._
2. **Portfólio**: Localize a tag `<img>` dentro de `.project-screenshot` (linha 149 em diante) e altere o `src`:
   ```html
   <img src="ASSETS/seu-projeto.jpg" alt="Nome do Projeto" />
   ```
   _Nota: A área de destaque foi ajustada para 380px de altura para garantir que o conteúdo caiba em diferentes telas. O site ajusta o print automaticamente para preencher este espaço._\_

---

## 👥 Gerenciando a Seção Equipe

A seção de equipe é composta por blocos chamados `.team-card` dentro da div `.team-scroll`.

### Como alterar um membro existente:

1. Abra o arquivo `index.html`.
2. Procure pela seção `<!-- Seção Equipe -->` (linha 238).
3. Altere os textos entre as tags:
   - `<h3>` (ex: linha 250): Nome do colaborador.
   - `<p class="team-role">` (ex: linha 251): Cargo ou função.
   - `<p class="team-skills">` (ex: linha 252): Habilidades ou ferramentas.

### Como adicionar um novo membro:

1. Copie todo o bloco de um membro existente (ex: linhas 246-254, do `<!-- Membro X -->` até o fechamento da `</div>` do `.team-card`).
2. Cole logo após o último membro, antes do fechamento da `</div>` da classe `.team-scroll` (antes da linha 415).
3. O site ajustará o scroll automaticamente para incluir o novo integrante.

### Como excluir um membro:

1. Localize o bloco `.team-card` do membro que deseja remover (ex: linhas 246-254).
2. Apague o bloco completo (da linha `<div class="team-card">` até a respectiva `</div>`).

---

---

## ⏳ Gerenciando a Seção de Jornada (Timeline)

A timeline mostra a trajetória da empresa, localizada logo após a animação inicial. Ela utiliza uma estrutura que se adapta automaticamente de horizontal (desktop) para vertical (mobile).

### Como alterar um marco da timeline:

1. Abra o arquivo `index.html`.
2. Procure pela seção `<!-- Timeline Section -->` (linha 83).
3. Dentro de cada `.timeline-item`, altere:

- `.timeline-year` (ex: linha 94): O ano do marco.
- `<h3>` (ex: linha 95): O título do marco (ex: "Fundação").
- `.timeline-text` (ex: linha 96): A descrição do acontecimento.
- **Ícones**: Substitua as classes do `<i>` (ex: linha 90 `fa-solid fa-rocket`) por outros ícones do FontAwesome.

### Como adicionar um novo marco:

1. Copie todo o bloco `.timeline-item` (ex: linhas 88-101, do começo ao fim da div).
2. Cole na posição desejada (cronológica) dentro da div `.timeline` (linha 86).
3. O layout se ajustará automaticamente.

---

## 📁 Gerenciando a Seção Portfólio

Os projetos são exibidos em um carrossel. Cada projeto é um bloco `.project-card` dentro de `.carousel-track`.

### Como alterar um projeto existente:

1. Abra o arquivo `index.html`.
2. Procure pela seção `<!-- Seção Portfólio -->` (linha 139).
3. Altere as informações:
   - `<h3>` (ex: linha 153): Nome do projeto.
   - `<p>` (ex: linha 154): Descrição curta.
   - **Imagem** (ex: linha 150): Altere o `src` da tag `<img>` dentro de `.project-screenshot` para o caminho da sua imagem.

### Como atualizar os links dos projetos:

Cada projeto possui dois links principais dentro da div `.project-links`:

1. **Link "Ver Site"** (primeiro link):

   - Localize a tag `<a href="#" class="project-link" target="_blank">` com o texto "Ver Site" (ex: linha 156).
   - Substitua o `#` no `href` pela URL do site/demo do projeto.
   - Exemplo: `<a href="https://meu-projeto.vercel.app" class="project-link" target="_blank">`

2. **Link "GitHub"** (segundo link):
   - Localize a tag `<a href="#" class="project-link" target="_blank">` com o texto "GitHub" (ex: linha 164).
   - Substitua o `#` no `href` pela URL do repositório no GitHub.
   - Exemplo: `<a href="https://github.com/usuario/nome-do-repo" class="project-link" target="_blank">`

**Exemplo completo de bloco de links:**

```html
<div class="project-links">
  <a href="https://meu-site.com" class="project-link" target="_blank">
    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
      <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
      <polyline points="15 3 21 3 21 9"></polyline>
      <line x1="10" y1="14" x2="21" y2="3"></line>
    </svg>
    Ver Site
  </a>
  <a
    href="https://github.com/usuario/repo"
    class="project-link"
    target="_blank"
  >
    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
      <path
        d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
      ></path>
    </svg>
    GitHub
  </a>
</div>
```

### Como adicionar um novo projeto:

1. Copie o bloco de um projeto existente (ex: linhas 148-174, da `<div class="project-card">` até a sua `</div>`).
2. Cole logo após o último projeto, dentro da div com o atributo `data-flickity` (linha 145).
3. Atualize a imagem, título, descrição e links conforme as instruções acima.
4. O carrossel Flickity identificará o novo projeto automaticamente.

### Como excluir um projeto:

1. Localize o bloco `.project-card` correspondente (ex: linhas 148-174).
2. Apague o bloco completo (do `<div class="project-card">` até o `</div>` correspondente).

---

## 🎨 Personalização de Estilos

### Cores e Temas

No arquivo `style.css`, você pode alterar as cores globais no topo do arquivo:

```css
:root {
  --cor-primaria: #1f71b1;
  --cor-secundaria: #085ea9;
  /* ... outras cores */
}
```

### Fontes (linhas 12-15 no `index.html`)

Para trocar a fonte, altere o link do Google Fonts no `<head>` do `index.html` e atualize a variável `--font-main` (se existir) ou a propriedade `font-family` no `body` do `style.css`.

### Ícones e Redes Sociais

O projeto utiliza o **FontAwesome** para os ícones. Os links de redes sociais no footer possuem cores de marca automáticas ao passar o mouse.

**Como alterar os links sociais:**

1. No `index.html`, localize o bloco `<div class="social-links">` (linha 425).
2. Altere o `href` de cada rede social:
   - **WhatsApp** (linha 426): `https://wa.me/SEUNUMERO`
   - **LinkedIn** (linha 429): `https://linkedin.com/in/SEUPERFIL`
   - **GitHub** (linha 432): `https://github.com/SEUUSUARIO`
   - **Instagram** (linha 435): `https://instagram.com/SEUPERFIL`
   - **E-mail** (linha 438): `mailto:seuemail@exemplo.com`

**Como trocar um ícone:**
Substitua a classe `<i>` dentro do link pelo código do ícone desejado do [FontAwesome](https://fontawesome.com/search). Exemplo: `<i class="fa-brands fa-x-twitter"></i>`.

---

## ⚙️ Configurações Técnicas (script.js)

- **Velocidade do Carrossel de Projetos** (linha 146 no `index.html`): Altere o valor `5000` (milissegundos) no atributo `autoPlay` para mudar a velocidade de transição automática dos projetos.
- **Velocidade do Scroll da Equipe** (linha 244 no `index.html`): Altere o valor `4000` no atributo `autoPlay` para mudar o intervalo de movimento da equipe.
