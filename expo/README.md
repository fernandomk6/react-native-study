# EXPO APP Teste

Testando um app mobile com expo.

*Requer android studio*

## Teste pessoal

### Instalação

```bash
npx create-expo-app@latest my-first-expo-app
cd my-first-expo-app
```

### Visializar

Android
```bash
npm run android 
```

Web
```bash
npm run web
```

## Gerando build de desenvolvimento

### Como instalar?

```
npx create-expo-app@latest my-first-expo-app
cd my-first-expo-app
```

### Instalar client de desenvolvimento

```
npx expo install expo-dev-client
```

### Definir o identificador do app

Abra o app.json e adicione dentro de "expo":

```json
"android": {
  "package": "com.seunome.meuteste"
}
```

Troque seunome pelo seu nome. Esse identificador precisa ser único, e depois você usará o mesmo na Play Store.

### Configurar o EAS (serviço de build do Expo)

```
npm install -g eas-cli
eas login
eas build:configure
```

Escolha Android quando perguntar. Isso cria o arquivo eas.json, que já vem com um perfil development.

### Gerar o build de desenvolvimento

```
eas build --profile development --platform android
```

- Na primeira vez, aceite a criação automática da chave de assinatura (keystore).
- O build roda na nuvem e leva de 10 a 30 minutos. Na fila gratuita pode demorar mais.
- No final, o terminal mostra um link e um QR code com o arquivo .apk.

### Instalar no seu celular

1. Abra o link ou escaneie o QR code com o celular.
2. Baixe o APK e toque para instalar.
3. Se o Android pedir, autorize “Instalar apps de fontes desconhecidas” para o navegador usado.

### Rodar e testar

No computador, dentro da pasta do projeto:

```bash
npx expo start --dev-client
```

No celular, abra o app meu-teste e escaneie o QR code que apareceu no terminal (ou escolha o servidor na lista). O app carrega no seu aparelho.

### Conferir que está funcionando

Edite um texto em app/(tabs)/index.tsx e salve. A tela do celular deve atualizar sozinha (hot reload).

