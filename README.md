# Crypto Monitor – Veja o preço do Bitcoin em reais com um clique!

Este app simples mostra a cotação atual do Bitcoin em reais (R$), usando a API pública do [Mercado Bitcoin](https://www.mercadobitcoin.com.br/). Ao tocar no botão **"Atualizar"**, você vê na hora o valor mais recente, junto com data e hora da última verificação.

---

## Como funciona

Ao abrir o app, a tela aparece com os dados zerados. Depois de tocar em **"Atualizar"**, o aplicativo busca a cotação em tempo real e exibe as informações formatadas.

---

## Estrutura do Projeto

Organizado de forma clara:

    kotlin-android-crypto-monitor/
    ├── app/
    │   ├── src/
    │   │   └── main/
    │   │       ├── java/pedrogonvalle/com/github/android_crypto_monitor/
    │   │       │   ├── MainActivity.kt
    │   │       │   ├── model/
    │   │       │   │   ├── Ticker.kt
    │   │       │   │   └── TickerResponse.kt
    │   │       │   └── service/
    │   │       │       ├── MercadoBitcoinService.kt
    │   │       │       └── MercadoBitcoinServiceFactory.kt
    │   │       └── res/
    │   │           ├── layout/
    │   │           |   ├── activity_main.xml
    |   |           |   ├── component_button_refresh.xml
    |   |           |   ├── component_quote_information.xml
    |   |           |   └── component_toolbar_main.xml
    |   |           └── values/
    │   │               ├── colors.xml
    │   │               ├── strings.xml
    │   │               └── themes.xml
    ├── build.gradle.kts
    └── gradle.properties


---

## Arquitetura

Segue o padrão **Model - View - Service**:

- **Model**: Representa os dados da API.
- **View**: Parte visual com botões e textos.
- **Service**: Camada que se comunica com a API usando Retrofit + GSON.

---

## Tecnologias

- **Retrofit**: Para chamadas HTTP.
- **GSON**: Para converter JSON em objetos Kotlin.
- **Coroutines**: Para chamadas assíncronas sem travar a interface.

---

## Lógica na Prática

A `MainActivity` gerencia a interface e as chamadas à API:

- Escuta o clique do botão **"Atualizar"**.
- Chama a função `makeRestCall()` que faz a requisição.
- Exibe os dados formatados (preço e horário).
- Mostra mensagens de erro com `Toast` personalizados em caso de falha.

---

## Layout e Design

Componentes visuais customizados:

- Botão "Atualizar" com estilo próprio.
- Componentes reutilizáveis para cotação e barra superior.
- Layout principal que une tudo numa interface limpa.

---

## Extras

- Mensagens de erro adaptadas para códigos HTTP como 400, 401, 403 e 404.
- Exibição no formato brasileiro: `R$` e `dd/MM/yyyy HH:mm:ss`.
- Estrutura modular, fácil de manter e escalar.

---

## Telas funcionais
Tela não atualizada, demonstrando o padrão ao iniciar o app:

![image](https://github.com/user-attachments/assets/844281a1-e1f4-4800-832a-265519fc668c)

Tela atualizada, após apertar o botão **"Atualizar"**

![image](https://github.com/user-attachments/assets/eaa64bec-78a6-4c5a-803e-29dceaf760f8)

### Feito por **Pedro Gonçalves Valle**
