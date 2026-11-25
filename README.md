# KAVEN — E-commerce de streetwear

Loja virtual minimalista de roupas e acessórios, feita em um único arquivo HTML (`loja.html`), sem dependências para instalar. Visual claro, fotos recortadas só com a peça e atendimento por chatbot.

## O que tem no site

- **Home:** banner, faixa de frases, atalhos circulares por seção, frases de efeito, vitrine e dúvidas frequentes.
- **8 seções:** Camisetas, Camisas, Moletons, Calças, Bermudas, Jaquetas, Calçados e Acessórios. Cada uma tem página própria com espaço para a foto de cada produto.
- **Menu:** botão "Menu" que abre um painel lateral e uma faixa de navegação abaixo do topo.
- **Carrinho:** quantidades, tamanho por peça e cálculo de frete.
- **Pagamento:** Pix (5% de desconto), cartão em até 6x sem juros e boleto.
- **Chatbot de ajuda:** botão "Ajuda" em todas as páginas (veja a seção abaixo).
- **Animações leves:** as seções surgem ao rolar a página, e são desativadas para quem prefere menos movimento.

## Como usar

Abra o `loja.html` no navegador. Não precisa instalar nada.

## Como personalizar

Tudo fica no `<script>` do `loja.html`.

| O que mudar | Onde |
|---|---|
| Nome, preço e seção dos produtos | objeto `RAW` (formato `Nome\|preço;Nome\|preço`) |
| Foto de um produto | objeto `IMG` (imagem em base64) e `PI` (liga o nome do produto à imagem) |
| Foto do círculo de cada seção | objeto `CI` |
| Produtos da vitrine | lista `VIT` |
| Tamanhos por tipo de peça | função `sizes` (roupas P a GG, calçados 39 a 43, acessórios único) |
| Valor do frete por km | constante `KM_PRICE` (hoje R$ 0,25) |
| WhatsApp e e-mail da loja | constantes `WA` e `MAIL` |
| Respostas do chatbot | lista `KB` |
| Dúvidas frequentes | lista `FAQ` |

## Frete

O frete é a distância entre a loja (centro de São Paulo) e o endereço do cliente, multiplicada por R$ 0,25 por km. O cliente informa CEP e número no carrinho.

**Importante:** hoje a distância é uma estimativa de demonstração baseada no CEP. Para valer de verdade, troque a função `distanceKm` por uma chamada ao seu servidor que consulte o endereço (por exemplo, ViaCEP) e uma API de rotas (por exemplo, Google Distance Matrix ou OpenRouteService). A chave dessas APIs deve ficar no servidor, nunca no site.

## Pagamento

A tela de pagamento coleta nome, e-mail e endereço e confirma o pedido em modo demonstração, **sem cobrar nada**. Para vender de verdade, conecte um gateway (Mercado Pago, Stripe, Pagar.me ou similar) na função `pay`.

## Chatbot

- **Perguntas frequentes:** responde por palavras-chave sobre frete, pagamento, desconto, trocas, tamanhos, seções, loja e horário.
- **Com IA:** quando disponível, entende perguntas livres e responde só com as informações da loja (frete, pagamento, trocas, tamanhos e lista de produtos com preços).
- **Quando não sabe:** mostra links para falar com a loja por WhatsApp e e-mail, com a dúvida do cliente já escrita.

A versão com IA usa o recurso da página publicada no Claude. Fora dele, ou se a IA não estiver disponível, o chatbot continua funcionando no modo de perguntas frequentes. Em um site próprio, ligue a IA por um servidor seu.

## Políticas escritas no site (exemplos, ajuste como quiser)

- Troca ou devolução em até 7 dias após o recebimento, com a peça sem uso e com etiqueta.
- Garantia de 30 dias para defeitos de fábrica.
- Atendimento de segunda a sexta, das 9h às 18h.

## Pendências antes de ir ao ar

- Trocar os dados provisórios: número de WhatsApp, e-mail, nomes e preços dos produtos.
- Conectar o cálculo de frete real e o gateway de pagamento.
- Substituir as fotos de referência por fotos dos seus produtos. Algumas imagens atuais têm marcas de terceiros visíveis.
- Preencher as peças que ainda estão sem foto.

## Visual

Paleta de preto, areia e oliva sobre fundo claro. Títulos em Archivo e textos em Work Sans (Google Fonts), com fontes alternativas caso não carreguem.
