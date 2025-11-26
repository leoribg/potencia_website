# Guia de Hospedagem: POTÊNCIA. Website

Este guia explica como hospedar o site usando **Firebase Hosting** ou **GitHub Pages**, configurar domínio e ativar o formulário de contato.

---

## 🔥 Firebase Hosting (Recomendado)

### Pré-requisitos

1. Conta Google/Firebase
2. Node.js instalado (para Firebase CLI)

### Instalação do Firebase CLI

```bash
# Instalar Firebase Tools globalmente
npm install -g firebase-tools

# Verificar instalação
firebase --version
```

### Configuração Inicial do Projeto

```bash
# 1. Fazer login no Firebase
firebase login

# 2. Inicializar projeto (já configurado neste projeto)
firebase init hosting

# Configurações usadas:
# - Public directory: public
# - Configure as single-page app: Yes
# - Set up automatic builds with GitHub: No
```

### Testando Localmente

```bash
# Iniciar servidor local (porta padrão 5000)
firebase serve

# Ou especificar uma porta customizada
firebase serve --port 8080

# Acessar no navegador: http://localhost:5000
```

### Deploy para Produção

```bash
# Deploy completo
firebase deploy

# Deploy apenas do hosting (mais rápido)
firebase deploy --only hosting

# Deploy com mensagem de commit
firebase deploy -m "Atualização do logo POTÊNCIA.IA."
```

### Comandos Úteis do Firebase

```bash
# Ver informações do projeto
firebase projects:list

# Abrir console do Firebase no navegador
firebase open hosting:site

# Ver histórico de deploys
firebase hosting:channel:list

# Rollback para versão anterior (via console web)
# Firebase Console > Hosting > Release history
```

### Estrutura do Projeto Firebase

```
potencia_website/
├── firebase.json          # Configuração do Firebase
├── .firebaserc            # Projeto ativo
└── public/
    └── index.html         # Website
```

### URLs Após Deploy

- **URL de Produção:** https://potencia-74784.web.app
- **URL Alternativa:** https://potencia-74784.firebaseapp.com

---

## Passo 1: Preparar o Envio de Emails ✅ (Já Configurado)

O formulário de contato já está integrado com o **Formspree** e enviará os emails para: **mauroperiquito@potenciatech.ai**

- Endpoint configurado: `https://formspree.io/f/xanzrokl`
- Status: Ativo e pronto para uso

**Nota:** Na primeira vez que alguém enviar o formulário, você receberá um email do Formspree pedindo confirmação. Clique no link de confirmação para ativar completamente o formulário.

## 📄 GitHub Pages (Alternativa)

### Configuração Básica

1. Crie um novo repositório no GitHub chamado `potencia-website`.
2. Deixe como **Public** e marque **Add a README file**.
3. Faça upload do arquivo `index.html`.
4. Vá em **Settings > Pages**.
5. Em **Branch**, selecione `main` e clique em **Save**.

Após alguns minutos, seu site ficará disponível em:
https://seuusuario.github.io/potencia-website/

---

## 🌐 Configurar Domínio Customizado (GoDaddy)

### Para Firebase Hosting

```bash
# Adicionar domínio customizado via CLI
firebase hosting:channel:deploy preview --expires 7d
```

**Ou via Console Web:**

1. Acesse [Firebase Console](https://console.firebase.google.com/)
2. Vá em **Hosting > Add custom domain**
3. Digite: `www.potenciatech.ai`
4. Siga as instruções para adicionar registros DNS

**Na GoDaddy:**

1. Vá para **Gerenciar DNS** do domínio
2. Adicione os registros fornecidos pelo Firebase:
   - **Tipo A** para domínio raiz (potenciatech.ai)
   - **CNAME** para www (www.potenciatech.ai)

### Para GitHub Pages

**No GitHub:**
1. Vá em **Settings > Pages**
2. Em **Custom domain**, digite: `www.potenciatech.ai`
3. Clique em **Save**

**Na GoDaddy:**
1. Vá para **Gerenciar DNS** do domínio
2. Crie um registro **CNAME**:
   - Host: `www`
   - Aponta para: `seuusuario.github.io`
   - TTL: padrão

---

## ✅ Checklist de Publicação

- [x] Firebase configurado e testado localmente
- [x] Formulário de contato integrado (Formspree)
- [x] Logo atualizado para POTÊNCIA.IA.
- [x] Cores da marca aplicadas
- [x] Sistema de tema claro/escuro implementado (padrão: claro)
- [ ] Deploy realizado para produção
- [ ] Domínio customizado configurado
- [ ] HTTPS ativado
- [ ] Teste de formulário em produção
- [ ] Google Analytics verificado

## 📋 Resumo Técnico

### Stack Tecnológico
- **Frontend:** HTML5 Single Page Application
- **Framework:** React 18 (via CDN - desenvolvimento)
- **Styling:** TailwindCSS 3.x (via CDN)
- **Icons:** Lucide Icons
- **Fonts:** Google Fonts (Inter + Montserrat)
- **Build Tool:** Babel Standalone (JSX/ESNext transpilation)

### Hospedagem e Infraestrutura
- **Hosting Principal:** Firebase Hosting
- **Analytics:** Firebase Analytics (Google Analytics 4)
- **Formulário:** Formspree (https://formspree.io/f/xanzrokl)
- **Email de destino:** mauroperiquito@potenciatech.ai
- **Projeto Firebase:** potencia-74784

### Identidade Visual
- **Nome:** POTÊNCIA.IA.
- **Cores da Marca:**
  - Preto: `#000000` / `#050505`
  - Azul Potência: `rgba(37, 32, 101, 1)` → `#252065` (POTÊNC text)
  - Dourado Potência: `rgba(228, 179, 69, 1)` → `#E4B345` (IA. text)
- **Tipografia:**
  - Display/Títulos: Montserrat (bold, black weights)
  - Corpo: Inter (light, regular, semibold)

### 🎨 Theme System (NEW!)
- **Dual Theme Support**: Light (default) and Dark modes
- **Theme Toggle**: Sun/moon icon in navigation bar
- **Persistent Preference**: User choice saved in localStorage
- **Smooth Transitions**: All colors animate smoothly between themes
- **Brand Immersion**: ✨ **ALL text in Light Mode uses Potência Blue (#252065)!** ✨
- **Complete Branding**: Every word reinforces your brand identity in light mode
- **Accessibility**: Maintains excellent contrast ratios (WCAG AAA compliant)
- **Documentation**: See `THEME_IMPLEMENTATION.md` and `BLUE_TEXT_UPDATE.md` for details

### Configuração Firebase
```json
{
  "projectId": "potencia-74784",
  "appId": "1:99516338484:web:d501c1a3a7ef71d9785561",
  "measurementId": "G-B9999E0MNN"
}
```

### Performance
- ✅ Responsive Design (Mobile First)
- ✅ Smooth Scroll Navigation
- ✅ Lazy Loading Icons
- ✅ Glass Morphism Effects
- ✅ Custom Animations
- ✅ SEO Optimized
- ✅ Dual Theme System (Light/Dark)
- ✅ Persistent Theme Preference (localStorage)
- ✅ Smooth Color Transitions (0.3s ease)

---

## 🚀 Comandos Rápidos

```bash
# Testar localmente
firebase serve

# Deploy para produção
firebase deploy

# Ver logs
firebase hosting:channel:list

# Abrir console
firebase open hosting
```

---

## 📞 Suporte

Para dúvidas sobre configuração:
- **Email:** mauroperiquito@potenciatech.ai
- **Projeto Firebase:** potencia-74784
- **Documentação:** [Firebase Docs](https://firebase.google.com/docs/hosting)
