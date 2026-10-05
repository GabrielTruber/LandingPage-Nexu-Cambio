# Contexto do projeto (para retomar em outra máquina)

Landing page one-page da Nexo Câmbio, vendida a um cliente que já tem domínio próprio. HTML/CSS/JS puros, sem build. Idioma: português do Brasil.

## Estado atual
- **Página oficial: `index.html`** (raiz). Os 3 protótipos antigos ficam em `layouts/` e são listados em `prototipos.html`.
- **Publicado no GitHub Pages:** https://gabrieltruber.github.io/LandingPage-Nexu-Cambio/ (branch `master`, pasta raiz). Cada push em `master` republica em 1–2 min. Repositório e site são **públicos**.
- Teste local: `python -m http.server 8080` na raiz.
- Logos dos 8 parceiros em `assets/bancos/` (usadas pelo `index.html`) e `assets/parceiros/` (usadas pelos layouts antigos).
- Painel de cotações no topo: Dólar e Euro, AwesomeAPI (atualiza a cada 30 s, reserva Frankfurter). Sem "Ao vivo" nem "Atualizado às" (removidos a pedido do usuário). Os layouts antigos também têm Libra (GBP).

## Decisões
- Hospedagem estática (GitHub Pages ou Cloudflare Pages), **sem VM**. Só o domínio custa (~R$ 40/ano). Para ligar o domínio do cliente: arquivo `CNAME` na raiz + DNS (CNAME `www` → `gabrieltruber.github.io`; 4 IPs A do GitHub para o domínio raiz — confirmar na doc oficial).
- Cotação **não é tempo real puro**: a API gratuita tem cache de ~5 min e fica parada com o mercado fechado. O WebSocket da AwesomeAPI foi testado e **não funcionou**.
- O usuário **não gosta de frases que "sujam a tela"** (textos de marketing/rótulos extras). Evitar inventar texto; preferir só o conteúdo do deck.
- Fora do git de propósito (`.gitignore`): `Logos/` (cópias das logos) e `*.pptx` (deck com conteúdo "Confidencial"; repo público). Em casa, peça o deck `NEXO_CAMBIO_Apresentacao_Institucional_FINAL.pptx` de novo se precisar.

## Pendências
- Confirmar com a Nexo: uso das logos de terceiros e se os R$ 449 MM (deck confidencial) podem ser públicos.
- **Telefone do Leonardo:** a página mostra `47 99963 1711`, mas o deck traz só `9 9963 1711`. O DDD 47 foi acrescentado — confirmar.
- Texto que **não está no deck** (criado por quem montou a página): seção "Metodologia Nexo" (4 etapas, SWIFT etc.), "Alcance Global", selo "Foco em Performance", frases do hero e do rodapé. Validar com a Nexo ou remover.
- Número "3.748 operações" é a soma de 3.024 + 724 (slide 6, só imagem); o deck não traz o total.
- Conteúdo do deck ainda fora da página: bloco do app Nexo (milhas, cashback, +3 mil marcas, Apple Store/Google Play).
- Possível: incluir Libra (GBP) na barra de cotações do `index.html`; ligar o domínio do cliente; decidir se o site deve ficar privado.
