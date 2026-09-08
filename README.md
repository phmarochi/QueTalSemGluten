# Que Tal Sem Glúten — site institucional

Site de página única (landing page) para a padaria e confeitaria sem glúten
**Que Tal Sem Glúten**, de Ponta Grossa (PR). HTML, CSS e JavaScript puros,
sem build e sem dependências — basta abrir o `index.html`.

## Estrutura

```
.
├── index.html          # todo o conteúdo da página
├── css/style.css       # estilos (mobile-first)
├── js/main.js          # menu, faixa animada e galeria com lightbox
├── img/                # fotos dos produtos e logo
└── vercel.json         # cabeçalhos de cache para a Vercel
```

## Rodar localmente

Abrir o `index.html` no navegador já funciona. Para servir com um servidor:

```bash
python3 -m http.server 8000
# abra http://localhost:8000
```

## Publicar

### GitHub

```bash
git init
git add .
git commit -m "Site Que Tal Sem Glúten"
git branch -M main
git remote add origin https://github.com/USUARIO/quetalsemgluten.git
git push -u origin main
```

### Vercel

1. Acesse vercel.com e clique em **Add New → Project**.
2. Importe o repositório do GitHub.
3. Em Framework Preset escolha **Other**; deixe build command e output em branco.
4. Clique em **Deploy**.

Como é um site estático, não há variáveis de ambiente nem build. Cada push na
branch `main` publica automaticamente.

Para usar domínio próprio: Vercel → Project → Settings → Domains.

## Como editar o essencial

**Número do WhatsApp** — está no formato `5542999943591` (55 + DDD + número).
Procure por `wa.me/5542999943591` no `index.html`; aparece nos botões, no
botão flutuante e no rodapé. O texto que já vem escrito na conversa fica
depois de `?text=`.

**Fotos da galeria** — salve a imagem em `img/` (largura de até 1400px é o
suficiente) e copie um bloco dentro de `#galeria-grade`:

```html
<button class="galeria__item" type="button">
  <img src="img/nome-da-foto.jpg" alt="Descrição da foto" loading="lazy">
</button>
```

O lightbox reconhece qualquer item novo automaticamente, sem mexer no
JavaScript. O primeiro item de cada bloco de sete (no celular) e de seis (no
computador) ocupa espaço maior no mosaico.

**Cores** — todas ficam no topo do `css/style.css`, em `:root`. O petróleo e o
dourado vieram do logotipo da marca.

## Pendências antes de ir ao ar

- [ ] Confirmar endereço da loja e horários de atendimento (marcado com `TODO`
      no rodapé do `index.html`)
- [ ] Confirmar a frase sobre cozinha dedicada / ausência de trigo no ambiente
- [ ] Trocar as fotos recortadas de posts por fotos em alta resolução, se a
      loja tiver os originais
- [ ] Definir domínio próprio
