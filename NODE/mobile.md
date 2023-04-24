### Criar projeto mobile, o prefix template serve para escolher se o projeto inicialmente
### utiliza alguma tecnologia como TypeScript

    npx create-expo-app --template

## Acesse a pasta e então prossiga

### Instalar tailwind

    npm i nativewind
    npm i --save-dev tailwindcss
    npx tailwindcss init

### Instala o Client do expo que possibilita rodar a aplicação

    npm i expo-cli -g
    npm i @expo/webpack-config@^0.17.2

### Para leitura de SVG

    npm i react-native-svg
    npx expo i react-native-svg
    npm i react-native-svg-transformer

### Para debug no navegador Web

    npx expo install react-native-web@~0.18.10 react-dom@18.2.0 @expo/webpack-config@^18.0.1

### Instalar no projeto fonts do google

    npx expo install expo-font @expo-google-fonts/inter
    
### Lib Para icons

    import {Feather} from '@expo/vector-icons'  


### Start project

    npx expo start --clear

### Para menus de navegação

    npm i @react-navigation/native
    npx expo install react-native-screens react-native-safe-area-context
    npm i @react-navigation/native-stack

