# Política de Privacidade — OpenGuardWRT

**Última atualização: 30 de agosto de 2026**

> Também publicada como página em:
> https://bitten-security.github.io/openguardwrt-privacy/

[OpenGuardWRT](https://github.com/bitten-security/OpenGuardWRT) é um
painel de leitura para o seu próprio roteador OpenWrt e instância do
AdGuard Home. Este documento explica, de forma direta, que dados o app
manuseia.

## Resumo

**O OpenGuardWRT não tem servidor próprio, não coleta dados, não usa
analytics, não tem anúncios e não compartilha nada com terceiros.** O app
fala apenas com o endereço do roteador que você mesmo configura, na sua
rede local ou por um túnel/VPN que você mesmo monta.

## Quais dados o app manuseia

- **Credenciais de acesso ao roteador e ao AdGuard Home** (usuário e senha
  que você cadastra na tela de conexão): ficam armazenadas somente no seu
  aparelho, em texto cifrado dentro do Android Keystore (via
  `flutter_secure_storage`). Nunca são enviadas a nenhum servidor além do
  próprio roteador/AdGuard Home que você configurou, e nunca em texto
  puro fora dessa comunicação direta.
- **Dados exibidos no painel** (dispositivos conectados, tráfego, status
  de DNS, etc.): são lidos diretamente do seu roteador a cada tela e
  ficam só na memória do app enquanto você usa — nada é enviado para fora
  do seu roteador/rede.
- **Bloqueio de app (PIN/biometria)**, se você ativar: usa a autenticação
  biométrica do próprio Android (`local_auth`). O app recebe apenas um
  "sim/não" do sistema operacional — nunca tem acesso à sua digital ou
  rosto.
- **Preferências do app** (tema, idioma, configurações de exibição): ficam
  salvas localmente no aparelho.

## O que o app nunca faz

- Não tem conta de usuário nem cadastro.
- Não envia dados para nenhum servidor nosso — porque não existe nenhum.
- Não usa analytics, rastreamento, SDKs de anúncio ou telemetria de
  qualquer tipo.
- Não compartilha dados com terceiros.
- Não lê nem armazena os campos de senha/credenciais de DDNS ou de
  certificados ACME configurados no seu roteador — mesmo sendo somente
  leitura, esses dois campos específicos são propositalmente ignorados
  pelo app.

## Teste de Bufferbloat

O botão "Testar" do Teste de Bufferbloat carrega, dentro do próprio app
(numa WebView), a página de um provedor externo à sua escolha —
[LibreQoS](https://test.libreqos.com) ou
[Waveform](https://www.waveform.com/tools/bufferbloat). A medição em si
roda inteiramente nos servidores desses provedores, contra a conexão de
internet do seu aparelho — o OpenGuardWRT não participa da medição, só
exibe a página deles. Consulte a política de privacidade de cada um se
for usar esse teste.

## Permissões do Android usadas

- **Internet**: necessária para o app se conectar ao endereço do seu
  roteador/AdGuard Home.
- **Biometria** (opcional, só se você ativar o bloqueio de app): usada
  exclusivamente para desbloquear o próprio app no seu aparelho.

Nenhuma outra permissão (câmera, localização, contatos, armazenamento,
etc.) é solicitada.

## Contato

Dúvidas sobre esta política: joaopbit@proton.me

---
