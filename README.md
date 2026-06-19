[README.md](https://github.com/user-attachments/files/29117372/README.md)
<div align="center">

```
$ whoami
ThinkAI Pro

$ cat mission.txt
IA local · Termux · Automação · Android
```

**IA local no seu bolso. Tecnologia de verdade.**

[![Site](https://img.shields.io/badge/🌐_Site-ThinkAI_Pro-6C63FF?style=for-the-badge)](https://ThinkAIPro.github.io/thinkai-pro/)
[![WhatsApp](https://img.shields.io/badge/💬_WhatsApp-Entrar_no_Grupo-25D366?style=for-the-badge)](https://chat.whatsapp.com/SEU-LINK-AQUI)
[![YouTube](https://img.shields.io/badge/▶️_YouTube-@ThinkAIPro-FF4444?style=for-the-badge)](https://youtube.com/@ThinkAIPro)

</div>

---

## 📋 Sobre o Projeto

Site oficial do canal **ThinkAI Pro** — landing page estática single-page, sem frameworks, com arquitetura orientada a dados: todo o conteúdo dinâmico (tutoriais, redes sociais, benefícios) é gerado a partir de um único objeto JavaScript (`CONFIG`), facilitando a manutenção sem precisar editar HTML.

> 🎯 Foco do canal: **IA local (Ollama/LLaMA), Termux, automação e tecnologia acessível no Android** — sem nuvem, sem mensalidade, sem complicação.

---

## 🚀 Demo ao Vivo

| | |
|--|--|
| 🌐 **Site** | https://ThinkAIPro.github.io/thinkai-pro/ |

---

## 📂 Estrutura do Repositório

```
thinkai-pro/
│
├── index.html          # Página única — HTML + CSS + JS (CONFIG)
└── README.md            # Este arquivo
```

---

## ⚙️ Tecnologias Utilizadas

```
HTML5 Semântico    →  Estrutura com seções e IDs para navegação por âncora
CSS3 Puro          →  Variáveis, Grid, Flexbox, keyframes e backdrop-filter
JavaScript Vanilla →  IIFEs que renderizam o conteúdo a partir do CONFIG
Google Fonts CDN   →  Inter (textos) + JetBrains Mono (terminal/labels)
GitHub Pages       →  Hospedagem gratuita e automática
```

---

## 🎨 Paleta de Cores

```css
:root {
  --bg:       #0D0F14;   /* fundo principal */
  --surface:  #13161F;   /* fundo de seções alternadas */
  --card:     #1A1D27;   /* fundo dos cards */
  --border:   #252836;   /* bordas e divisores */
  --accent:   #6C63FF;   /* roxo principal */
  --accent2:  #A78BFA;   /* roxo claro — destaques */
  --green:    #25D366;   /* verde WhatsApp */
  --green2:   #4ECCA3;   /* verde claro — terminal */
  --text:     #E8E8F0;   /* texto principal */
  --muted:    #6B6F84;   /* texto secundário */
}
```

> Alterar qualquer valor aqui propaga a mudança por toda a página automaticamente.

---

## 🖥️ Mapa de Seções

```
┌──────────────────────────────────┐
│  NAV         — Logo + Links       │  fixa, blur
├──────────────────────────────────┤
│  HERO        — Título + Terminal  │  efeito de digitação animado
├──────────────────────────────────┤
│  SOBRE       — 4 cards            │  vem de CONFIG.about
├──────────────────────────────────┤
│  TUTORIAIS   — Grid de cards      │  vem de CONFIG.tutorials
├──────────────────────────────────┤
│  COMUNIDADE  — CTA WhatsApp       │  vem de CONFIG.whatsappLink + waPerks
├──────────────────────────────────┤
│  REDES       — Grid social        │  vem de CONFIG.social
├──────────────────────────────────┤
│  FOOTER      — Copyright + Links  │  gerado via JS
└──────────────────────────────────┘
```

---

## ⭐ Arquitetura: O Objeto `CONFIG`

Toda a manutenção do site é feita em um único lugar: o objeto `CONFIG`, no final do `index.html`, dentro da tag `<script>`.

```js
const CONFIG = {
  channelName: "ThinkAI Pro",
  whatsappLink: "https://chat.whatsapp.com/SEU-LINK-AQUI",
  social: [ /* redes sociais */ ],
  about: [ /* cards "sobre o canal" */ ],
  tutorials: [ /* tutoriais */ ],
  waPerks: [ /* benefícios do grupo */ ],
};
```

> ⛔ **Não edite** o código abaixo do comentário `Não edite abaixo desta linha` — essa parte apenas lê o `CONFIG` e renderiza a página.

---

## ✏️ Como Personalizar

### 1. Trocar o link do WhatsApp

```js
whatsappLink: "https://chat.whatsapp.com/SEU-LINK-REAL",
```

> Esse único campo alimenta os dois botões de WhatsApp da página (hero e seção Comunidade).

### 2. Adicionar uma Rede Social

```js
social: [
  { name: "YouTube", handle: "@ThinkAIPro", url: "https://youtube.com/@ThinkAIPro", icon: "▶", bg: "#1a0a0a", color: "#FF4444" },
  // adicione novas redes copiando o padrão acima — deixe url: "" para ocultar
],
```

### 3. Editar os Cards "Sobre"

```js
about: [
  { icon: "🤖", title: "IA 100% local", text: "Descrição do card aqui." },
  // adicione, edite ou remova quantos quiser
],
```

### 4. Adicionar um Tutorial

```js
tutorials: [
  {
    tag:   "IA Local",                 // categoria do card
    title: "Título do tutorial",
    desc:  "Descrição curta em 1-2 linhas.",
    time:  "15 min",                   // ou "Em breve"
    url:   "#",                        // "#" deixa o card desabilitado
  },
],
```

> 💡 Use `url: "#"` para marcar tutoriais como **"Em breve"** — o card fica visualmente desabilitado automaticamente. Quando o conteúdo estiver pronto, troque pelo link real.

### 5. Editar os Benefícios do WhatsApp

```js
waPerks: [
  "🔥 Promoções todo dia",
  "📚 Tutoriais em primeira mão",
  // adicione, edite ou remova livremente
],
```

### 6. Trocar Cores do Tema

Edite as variáveis em `:root { }` no `<style>`:

```css
:root {
  --accent: #6C63FF;   /* troque aqui para mudar o roxo */
  --green:  #25D366;   /* troque aqui para mudar o verde */
}
```

### 7. Editar o Título do Hero (texto fixo)

O `<h1>` do hero **não** vem do `CONFIG` — edite direto no HTML:

```html
<h1>
  <span class="accent">IA local</span> no seu bolso.<br/>
  Tecnologia de <span class="under">verdade</span>.
</h1>
```

### 8. Editar as Frases do Terminal Animado

```js
const phrases = [
  'ollama run llama3',
  'python server.py',
  'pkg install python -y',
  // adicione/edite os comandos exibidos no efeito de digitação
];
```

---

## 🌱 Expansão Futura

```
cursos.html      →  Mural de cursos com links de afiliado (Hotmart, Kiwify...)
noticias.html    →  Lista de notícias seguindo o mesmo padrão CONFIG
#promocoes       →  Nova seção dentro do próprio index.html
```

> Para manter a identidade visual, qualquer página nova deve reaproveitar as mesmas variáveis CSS (`--accent: #6C63FF`, `--green: #25D366`) e as fontes Inter + JetBrains Mono.

---

## 📡 Hospedagem no GitHub Pages

### Publicar

```
1. Crie um repositório público: thinkai-pro
2. Faça upload de index.html
3. Settings > Pages > Branch: main > / (root) > Save
4. Aguarde 1-2 minutos
5. Acesse: https://ThinkAIPro.github.io/thinkai-pro/
```

### Atualizar

```
1. Abra o arquivo no GitHub
2. Clique no ícone de lápis ✏️
3. Edite o CONFIG ou o HTML
4. Commit changes
5. Site atualizado em até 2 minutos ✅
```

---

## ✅ Checklist de Lançamento

- [ ] Substituir `whatsappLink` pelo link real do grupo
- [ ] Preencher URLs reais em `CONFIG.social`
- [ ] Revisar os 4 cards de `CONFIG.about`
- [ ] Adicionar tutoriais reais em `CONFIG.tutorials`
- [ ] Trocar `url: "#"` pelos links conforme os tutoriais ficarem prontos
- [ ] Revisar `CONFIG.waPerks`
- [ ] Editar o título do hero, se desejar
- [ ] Revisar as frases do terminal animado
- [ ] Testar todos os links e botões
- [ ] Verificar responsividade em celular
- [ ] Fazer upload no GitHub e ativar GitHub Pages
- [ ] Compartilhar o site no canal 🚀

---

## 📄 Licença

Projeto de uso pessoal do canal **ThinkAI Pro**.
Todos os direitos reservados ao autor © 2025.

---

<div align="center">

Feito com 💜 e muito Termux — **ThinkAI Pro**

[![WhatsApp](https://img.shields.io/badge/💬_Grupo_WhatsApp-Entrar_Grátis-25D366?style=flat-square)](https://chat.whatsapp.com/SEU-LINK-AQUI)

*IA local • Termux • Automação • Android*

</div>
