#Criar projeto mobile, o prefix template serve para escolher se o projeto inicialmente
#utiliza alguma tecnologia como TypeScript
npx create-expo-app --template

#Instala o Client do expo que possibilita rodar a aplicação
npm i expo-cli -g
npm i @expo/webpack-config@^0.17.2

#Start project
npx expo start

#Instalar no projeto fonts do google
npx expo install expo-font @expo-google-fonts/inter