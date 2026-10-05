# Gratificados — como criar a app (APK e iOS)

Esta versão já inclui o teu logo (azul-marinho e dourado) como ícone e ecrã de arranque (`assets/icon.png`, `assets/splash.png` e `www/icon-*.png`), e as cores novas.

Esta pasta tem tudo o que é preciso. **Não foi testada a compilação na nuvem** (não tenho acesso à internet aqui), por isso, se um passo falhar, copia a mensagem de erro e diz-me.

## Opção A — A mais fácil: instalar no ecrã principal (iPhone e Android), sem lojas e sem custos
1. Cria uma conta grátis em github.com e um repositório **público** novo (ex.: `gratificados`).
2. Carrega o conteúdo desta pasta para o repositório (incluindo a pasta escondida `.github`). Num computador é só arrastar tudo para a página do repositório → "Add file" → "Upload files".
3. No repositório: **Settings → Pages → Source: GitHub Actions**. Depois **Actions → "Publicar app" → Run workflow**.
4. Ao terminar aparece um endereço (https://O-TEU-NOME.github.io/gratificados/). Abre-o:
   - **iPhone:** Safari → Partilhar → *Adicionar ao Ecrã Principal*.
   - **Android:** Chrome → menu ⋮ → *Instalar app*.
5. Fica com o ícone e o nome "Gratificados", abre em ecrã inteiro e funciona sem internet. O ícone do ecrã principal passa a ser o desta pasta (`www/icon-192.png`, `www/icon-512.png`, `www/apple-touch-icon.png`); para o mudar, substitui esses ficheiros.
   O repositório só tem o código da app. **Os teus registos ficam só no telemóvel** e nunca vão para o GitHub.

## Opção B — APK para Android (instala fora da Play Store)
1. Com o repositório criado como acima, vai a **Actions → "Criar APK (Android)" → Run workflow**.
2. Ao terminar, descarrega o artefacto **Gratificados-APK** (zip com o `app-debug.apk`).
3. No telemóvel Android, abre o APK e permite "instalar apps desconhecidas".
Para a Google Play é preciso uma conta de programador (25 USD, pagamento único) e um APK/AAB assinado.

## Opção C — iOS nativo (precisa de Apple Developer)
1. **Actions → "Criar IPA (iOS)" → Run workflow** gera o `Gratificados-sem-assinatura.ipa` (sem assinatura).
2. Para instalar no iPhone o IPA tem de ser assinado:
   - **Conta Apple Developer (99 USD/ano):** assinar e publicar no TestFlight/App Store (precisa de certificados; posso ajudar a configurar).
   - **Grátis, com Apple ID:** Sideloadly ou AltStore (precisam de um computador) e a app tem de ser renovada de 7 em 7 dias.
Sem Mac, não dá para compilar localmente: por isso a compilação é feita na nuvem (macOS do GitHub).

## Notas
- `www/index.html` é a mesma app, com: ficheiros para instalar (manifest e modo offline) e gravação de backups pela folha de partilha na app nativa.
- A exportação para Excel e a fonte usam bibliotecas da internet; sem ligação a app usa CSV e a letra do sistema.
- Para mudar o nome ou o identificador da app: `capacitor.config.json` (`appName`, `appId`).
- Ícone de origem: `assets/icon.png` (1024×1024) e ecrã de arranque `assets/splash.png`.
