# Teleprompter com controle remoto por QR Code

App de teleprompter que roda como **APK (Android)** e como **página web** (iPhone, iPad, computador).
Um aparelho fica de "tela" no teleprompter da câmera; outro aparelho (celular, tablet ou navegador) controla
velocidade, tempo, tamanho, espelhamento e roteiros, pareado por QR Code. Sem conta e sem login.

## Como gerar o APK no GitHub

1. Crie uma conta em github.com e um repositório novo (ex.: `teleprompter`), **público**.
2. Envie **todo o conteúdo desta pasta** para o repositório, incluindo a pasta oculta `.github`.
   - Pela web: botão **Add file > Upload files** e arraste tudo.
   - Se a pasta `.github` não subir, use **Add file > Create new file**, digite o nome
     `.github/workflows/build-apk.yml` e cole o conteúdo do arquivo correspondente. Repita para `pages.yml`.
3. Abra a aba **Actions**. O workflow **Gerar APK** começa sozinho (leva uns 5 a 10 minutos).
   Se não começar, escolha **Gerar APK > Run workflow**.
4. Quando ficar verde, abra a execução e baixe **teleprompter-apk** na seção **Artifacts**.
5. Descompacte o .zip. Dentro está `app-debug.apk`. Passe para o Android e instale
   (permita "instalar apps de fontes desconhecidas" quando o Android pedir).

## Versão web para iPhone e navegador

1. No repositório: **Settings > Pages > Build and deployment > Source: GitHub Actions**.
2. Rode o workflow **Publicar versão web** (aba Actions). O endereço aparece no final, algo como
   `https://SEU-USUARIO.github.io/teleprompter/`.
3. No iPhone, abra o endereço no Safari, toque em **Compartilhar > Adicionar à Tela de Início**.
4. No app Android, abra **QR** na tela do teleprompter, expanda **Link do app na web** e cole esse endereço.
   Assim o QR Code abre direto a versão web no iPhone.

## Como usar

- **Tela:** toque em "Usar este aparelho como tela". Aparece o QR Code e um código de 6 letras.
- **Controle:** em outro aparelho, toque em "Controlar outra tela" e escaneie o QR (ou digite o código).
- Crie roteiros pelo controle, envie para a tela, dê play e ajuste tudo em tempo real.

## Observações

- O pareamento usa conexão direta entre os aparelhos (WebRTC). O servidor público gratuito do PeerJS
  só ajuda a eles se encontrarem, então os dois aparelhos precisam de internet.
- Os roteiros ficam salvos no próprio aparelho.
- O APK gerado é de debug, assinado com a chave de teste. Serve para instalar e usar normalmente,
  mas não para publicar na Play Store.
