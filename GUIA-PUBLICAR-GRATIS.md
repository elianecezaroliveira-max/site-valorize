# Como publicar o site consultoriavalorize.com.br de graça

Você vai usar o **GitHub Pages** (hospedagem gratuita, sem mensalidade, sem anúncios) e apontar o seu domínio do **Registro.br** para ele. Leva uns 20 minutos e depois é só esquecer.

---

## Passo 0 — Edite seus dados no site (2 min)

Abra o arquivo `index.html` em qualquer editor de texto (Bloco de Notas serve). Perto do final, procure o bloco:

```
const CONFIG = {
  whatsapp: "5511999999999",
  telefoneExibido: "(11) 99999-9999",
  email: "contato@consultoriavalorize.com.br",
  instagram: "https://instagram.com/consultoriavalorize",
  facebook: "https://facebook.com/consultoriavalorize",
  endereco: "Atendimento online em todo o Brasil",
  cnpj: "CNPJ 00.000.000/0001-00"
};
```

Troque só o texto entre aspas pelos seus dados e salve. Todo botão de WhatsApp, e-mail, Instagram etc. do site usa esse bloco.

Se quiser mudar textos (títulos, depoimentos, taxas do simulador), é só procurar o texto no arquivo e trocar. As taxas do simulador ficam na linha `const TAXAS = {...}`.

---

## Passo 1 — Crie uma conta no GitHub (grátis)

1. Acesse https://github.com e clique em **Sign up**.
2. Use seu e-mail, crie uma senha e confirme o código que chega no e-mail.

## Passo 2 — Crie o repositório do site

1. Logada, clique no **+** (canto superior direito) → **New repository**.
2. Em *Repository name* digite: `site-valorize`
3. Deixe **Public** marcado e clique em **Create repository**.

## Passo 3 — Envie os arquivos

1. Na página do repositório, clique em **uploading an existing file** (ou **Add file → Upload files**).
2. Arraste os dois arquivos: `index.html` e `CNAME`.
3. Clique em **Commit changes** (botão verde).

## Passo 4 — Ative o GitHub Pages

1. No repositório, clique em **Settings** → menu lateral **Pages**.
2. Em *Source* escolha **Deploy from a branch**; em *Branch* escolha **main** e pasta **/ (root)**. Clique **Save**.
3. Em *Custom domain* digite `consultoriavalorize.com.br` e clique **Save**.
   (Se aparecer aviso de DNS, é normal — vamos resolver no próximo passo.)

## Passo 5 — Aponte o domínio no Registro.br

1. Entre em https://registro.br → **Painel** → clique no domínio **consultoriavalorize.com.br**.
2. Clique em **Editar zona** / **Configurar endereçamento** (DNS).
   Se aparecer "Utilizar DNS do Registro.br", escolha essa opção.
3. Apague registros antigos do Canva (tipo A ou CNAME apontando para o Canva) e crie estes:

| Tipo  | Nome  | Valor / Dados            |
|-------|-------|--------------------------|
| A     | (vazio) | 185.199.108.153        |
| A     | (vazio) | 185.199.109.153        |
| A     | (vazio) | 185.199.110.153        |
| A     | (vazio) | 185.199.111.153        |
| CNAME | www   | SEUUSUARIO.github.io     |

   *(Troque `SEUUSUARIO` pelo seu nome de usuário do GitHub — está na URL do seu perfil.)*

4. Salve. O Registro.br leva de alguns minutos até algumas horas para propagar.

## Passo 6 — Ative o cadeado (HTTPS)

Depois que o DNS propagar, volte em **Settings → Pages** no GitHub e marque **Enforce HTTPS**. Pronto: o site abre em https://consultoriavalorize.com.br com cadeado.

---

## Para atualizar o site depois

Edite o `index.html` no seu computador, entre no repositório no GitHub, clique no arquivo `index.html` → ícone de lápis (ou **Upload files** de novo para substituir) → **Commit changes**. Em 1 minuto o site atualiza.

## Cancelar o Canva

Depois que o site novo estiver no ar, cancele a assinatura do Canva Pro/Sites em **Configurações → Cobrança e planos**. Nada do domínio depende do Canva.

## Alternativa igualmente grátis: Netlify

Se preferir arrastar-e-soltar sem GitHub: crie conta em https://app.netlify.com, arraste a pasta com o `index.html`, em **Domain management** adicione `consultoriavalorize.com.br` e siga as instruções de DNS que ele mostra (ele vai pedir para apontar registros no Registro.br do mesmo jeito).
