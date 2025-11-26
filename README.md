# Guia de Hospedagem: PotêncIA Website

Este guia explica como colocar seu site no ar gratuitamente usando **GitHub Pages**, configurar um domínio **GoDaddy** e ativar o **formulário de contato** para receber emails reais.

## Passo 1: Preparar o Envio de Emails ✅ (Já Configurado)

O formulário de contato já está integrado com o **Formspree** e enviará os emails para: **mauroperiquito@potenciatech.ai**

- Endpoint configurado: `https://formspree.io/f/xanzrokl`
- Status: Ativo e pronto para uso

**Nota:** Na primeira vez que alguém enviar o formulário, você receberá um email do Formspree pedindo confirmação. Clique no link de confirmação para ativar completamente o formulário.

## Passo 2: Hospedar no GitHub Pages

1. Crie um novo repositório no GitHub chamado `potencia-website`.
2. Deixe como **Public** e marque **Add a README file**.
3. Faça upload do arquivo `index.html`.
4. Vá em **Settings > Pages**.
5. Em **Branch**, selecione `main` e clique em **Save**.

Após alguns minutos, seu site ficará disponível em:
https://seuusuario.github.io/potencia-website/

## Passo 3: Configurar Domínio na GoDaddy

No GitHub:
1. Vá em **Settings > Pages**.
2. Em **Custom domain**, digite: www.potenciatech.ai
3. Clique em **Save**.

Na GoDaddy:
1. Vá para **Gerenciar DNS** do domínio.
2. Crie um registro **CNAME**:
   - Host: www
   - Aponta para: seuusuario.github.io
   - TTL: padrão

(Opcional) Configure redirecionamento do domínio raiz para:
https://www.potenciatech.ai

## Finalização

Ative a opção **Enforce HTTPS** no GitHub assim que estiver disponível.

## Resumo Técnico

- Tecnologia: HTML5 Single Page + React (via CDN) + TailwindCSS (via CDN)
- Cores:
  - Preto: #000000
  - Azul: rgba(35, 30, 98)
  - Dourado: rgba(227, 182, 50)
- Envio de formulário: via **Formspree**
- Email de destino: mauroperiquito@potenciatech.ai
