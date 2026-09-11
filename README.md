# 📍 App Consulta CEP

Um aplicativo Android desenvolvido em **Kotlin** que permite consultar informações de endereços através do código postal (CEP) usando a API ViaCEP.

---

## 📋 Índice

- [Sobre](#sobre)
- [Funcionalidades](#funcionalidades)
- [Mockup da Tela](#mockup-da-tela)
- [Requisitos](#requisitos)
- [Instalação](#instalação)
- [Como Usar](#como-usar)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Tecnologias](#tecnologias)
- [API Utilizada](#api-utilizada)
- [Exemplos de CEPs](#exemplos-de-ceps)

---

## 🎯 Sobre

O **App Consulta CEP** é uma aplicação mobile simples e intuitiva que permite aos usuários buscar informações completas de endereços brasileiros através de um CEP (Código de Endereçamento Postal). A aplicação consome dados da API pública **ViaCEP**, oferecendo resultados precisos em tempo real.

---

## ✨ Funcionalidades

- ✅ **Busca por CEP** - Digite um CEP de 8 dígitos para obter o endereço
- ✅ **Validação de CEP** - Verifica se o CEP possui exatamente 8 dígitos
- ✅ **Exibição de Resultados** - Mostra logradouro, bairro, UF, DDD e cidade
- ✅ **Interface Simples** - Design limpo e intuitivo
- ✅ **Requisição Assíncrona** - Usa Coroutines para não travar a UI

---

## 📱 Mockup da Tela

### Tela Principal - Consulta de CEP

```
┌─────────────────────────────────────┐
│                                     │
│     🔴 Consulta de CEP 🔴          │
│                                     │
│  ┌──────────────────────────────┐   │
│  │ Digite seu CEP               │   │
│  │ [    Digite seu CEP    ]     │   │
│  └──────────────────────────────┘   │
│                                     │
│        [    CONSULTAR    ]           │
│                                     │
├─────────────────────────────────────┤
│  Logradouro:                        │
│  ┌──────────────────────────────┐   │
│  │ [Resultado]                  │   │
│  └──────────────────────────────┘   │
│                                     │
│  Bairro:                            │
│  ┌──────────────────────────────┐   │
│  │ [Resultado]                  │   │
│  └──────────────────────────────┘   │
│                                     │
│  UF:                                │
│  ┌──────────────────────────────┐   │
│  │ [Resultado]                  │   │
│  └──────────────────────────────┘   │
│                                     │
│  DDD:                               │
│  ┌──────────────────────────────┐   │
│  │ [Resultado]                  │   │
│  └──────────────────────────────┘   │
│                                     │
│  Cidade:                            │
│  ┌──────────────────────────────┐   │
│  │ [Resultado]                  │   │
│  └──────────────────────────────┘   │
│                                     │
└─────────────────────────────────────┘
```

### Esquema de Cores

| Elemento | Cor | Código |
|----------|-----|--------|
| Fundo | Rosa Claro | `#FFEAE6` |
| Título | Vermelho Escuro | `#854646` |
| Rótulos | Laranja | `#BA3D11` |
| Botão | Vermelho Escuro | `#750404` |
| Input CEP | Rosa | `#6EFFD6D6` |

---

## 🛠️ Requisitos

- **Android Mínimo**: API 24+ (Android 7.0)
- **Kotlin**: 1.8.0+
- **Gradle**: 8.0+
- **Java**: JDK 11+
- **Conexão com Internet**: Obrigatória para consultar a API

---

## 📦 Instalação

### 1. Clonar o Repositório

```bash
git clone https://github.com/AllissonBolo/AppConsultaCEP.git
cd AppConsultaCEP
```

### 2. Abrir no Android Studio

1. Abra o **Android Studio**
2. Selecione **File → Open**
3. Navegue até a pasta do projeto
4. Clique em **OK**

### 3. Sincronizar Gradle

O Android Studio sincronizará automaticamente, ou execute:

```bash
./gradlew build
```

### 4. Executar o App

- Conecte um dispositivo Android ou inicie um emulador
- Clique em **Run** (Shift + F10)

---

## 💻 Como Usar

1. **Abra o aplicativo**
2. **Digite um CEP válido** no campo de entrada (8 dígitos numéricos)
   - Exemplo: `01310100`
3. **Clique no botão "CONSULTAR"**
4. **Aguarde o resultado** - Os dados do endereço aparecerão nos campos abaixo

### Validação

- O CEP deve ter **exatamente 8 dígitos**
- Caso contrário, você verá a mensagem: `CEP inválido`

---

## 📂 Estrutura do Projeto

```
AppConsultaCEP/
├── app/
│   └── src/main/
│       ├── java/com/example/appconsultacep/
│       │   ├── MainActivity.kt              # Tela principal
│       │   ├── api/
│       │   │   ├── ViaCepClient.kt          # Cliente Retrofit
│       │   │   └── ViaCepService.kt         # Interface da API
│       │   └── model/
│       │       └── ResponseEndereco.kt      # Modelo de dados
│       └── res/
│           ├── layout/
│           │   └── activity_main.xml        # Layout da tela
│           ├── values/
│           │   ├── strings.xml
│           │   ├── colors.xml
│           │   └── themes/
│           ├── drawable/                    # Ícones e imagens
│           ├── font/                        # Fontes customizadas
│           └── mipmap/                      # Ícones do app
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
```

---

## 🛠️ Tecnologias

| Tecnologia | Versão | Descrição |
|-----------|--------|-----------|
| **Kotlin** | 1.8.0+ | Linguagem de programação |
| **AndroidX** | Latest | Framework Android moderno |
| **Retrofit** | 2.11.0 | Cliente HTTP tipo-seguro |
| **Gson** | 2.10.1+ | Serialização JSON |
| **Material Design** | 3.0+ | Componentes de UI |
| **Coroutines** | Latest | Programação assíncrona |
| **ConstraintLayout** | Latest | Layout flexível |

---

## 📡 API Utilizada

### ViaCEP API

**Documentação**: [ViaCEP](https://viacep.com.br/)

**Endpoint**: 
```
GET https://viacep.com.br/ws/{cep}/json/
```

**Parâmetros**:
- `{cep}` - CEP sem formatação (8 dígitos)

**Exemplo de Requisição**:
```bash
GET https://viacep.com.br/ws/01310100/json/
```

**Exemplo de Resposta**:
```json
{
  "cep": "01310-100",
  "logradouro": "Avenida Paulista",
  "complemento": "lado ímpar",
  "bairro": "Bela Vista",
  "localidade": "São Paulo",
  "uf": "SP",
  "ibge": "3550308",
  "gia": "",
  "ddd": "11",
  "siafi": "7107"
}
```

---

## 📝 Exemplos de CEPs

| CEP | Endereço | Cidade |
|-----|----------|--------|
| `01310100` | Avenida Paulista | São Paulo - SP |
| `20040020` | Avenida Rio Branco | Rio de Janeiro - RJ |
| `30140071` | Avenida Getúlio Vargas | Belo Horizonte - MG |
| `80010000` | Avenida Getúlio Vargas | Porto Alegre - RS |
| `70040902` | Esplanada dos Ministérios | Brasília - DF |

---

## 🔍 Detalhes da Implementação

### MainActivity.kt

A atividade principal gerencia:
- Captura do input do usuário (CEP)
- Validação do CEP (8 dígitos)
- Chamada assíncrona à API
- Exibição dos resultados nos campos

### API - ViaCepClient.kt

Singleton que:
- Configura a instância do Retrofit
- Define a URL base (`https://viacep.com.br`)
- Adiciona conversor Gson para JSON

### API - ViaCepService.kt

Interface Retrofit que:
- Define o endpoint: `ws/{cep}/json/`
- Retorna um objeto `ResponseEndereco`
- Usa `suspend` para suportar Coroutines

### Model - ResponseEndereco.kt

Data class que mapeia a resposta JSON:
- `logradouro` - Nome da rua/avenida
- `bairro` - Bairro
- `uf` - Estado (sigla)
- `localidade` - Cidade
- `ddd` - Código de área telefônico

---

## 🚀 Melhorias Futuras

- [ ] Tratamento de erros com mensagens customizadas
- [ ] Cache de buscas locais
- [ ] Histórico de CEPs consultados
- [ ] Modo offline
- [ ] Integração com Google Maps
- [ ] Busca reversa (endereço → CEP)
- [ ] Compartilhamento de endereços
- [ ] Tema escuro

---

## 🐛 Troubleshooting

### "CEP inválido"
- Verifique se digitou **exatamente 8 dígitos**
- Não use hífen ou espaço no CEP
- Exemplo correto: `01310100` ❌ Incorreto: `01310-100`

### "Erro de conexão"
- Verifique sua conexão com a internet
- Tente novamente em poucos momentos
- Certifique-se de que o servidor ViaCEP está online

### App congela ao buscar
- Ensure you're using a device/emulator with a stable internet connection
- Tente com CEPs conhecidos primeiro

---

## 📧 Contato

**Autor**: Allisson Bolo  
**GitHub**: [@AllissonBolo](https://github.com/AllissonBolo)  
**Repositório**: [AppConsultaCEP](https://github.com/AllissonBolo/AppConsultaCEP)

---

## 📄 Licença

Este projeto está sob a licença **MIT**. Sinta-se livre para usar, modificar e distribuir.

---

<div align="center">

**Feito com ❤️ por [AllissonBolo](https://github.com/AllissonBolo)**

⭐ Se este projeto foi útil, deixe uma estrela!

</div>