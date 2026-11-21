# Placa de Avaliação (QR Code → Google)

Site leve para colocar em uma plaquinha no balcão da loja. O cliente lê o QR Code, responde algumas perguntas com toques (sem digitar nada) e o site monta o texto da avaliação. Depois ele publica a avaliação no perfil da loja no Google.

## Arquivos
- `index.html`: página que o cliente vê (estrelas + 6 perguntas rápidas + texto pronto).
- `placa.html`: gerador da placa: QR Code, prévia, impressão em A6 e download do QR em PNG.
- `qrcode.js`: biblioteca de QR Code (qrcode-generator 1.4.4, licença MIT), incluída localmente.

## Como usar
1. **Publique o site** (grátis) no GitHub Pages: *Settings → Pages → Branch: main / root*.
   O endereço fica `https://SEU-USUARIO.github.io/PlacaDeAvalia-o/`.
2. Abra `https://SEU-USUARIO.github.io/PlacaDeAvalia-o/placa.html`.
3. Para cada comércio, informe:
   - **Nome da loja**
   - **Place ID** (começa com `ChIJ…`, pegue no [Place ID Finder](https://developers.google.com/maps/documentation/places/web-service/place-id))
     **ou** o link de *“Pedir avaliações”* do Perfil da Empresa no Google (`https://g.page/r/…/review`).
4. Clique em **Testar o link**, depois em **Imprimir placa (A6)** ou **Baixar QR Code**.

Um único site atende todas as lojas: os dados de cada uma vão dentro do próprio QR Code.

## Por que o cliente precisa tocar em "Publicar" no Google?
O Google **não permite** que sites de terceiros publiquem avaliações em nome do cliente: não existe API para isso. A avaliação precisa sair da conta Google da própria pessoa. Por isso o site faz todo o resto. Ele monta o texto, copia esse texto e abre a tela oficial de avaliação da loja. Lá o cliente só toca nas estrelas, cola o texto e publica.

Seguindo as regras do Google, **todas as notas vão para o Google**, inclusive as baixas. Filtrar notas ruins (*review gating*) é proibido e pode fazer a loja perder avaliações.
