# 📍 App Consulta CEP

Um aplicativo Android desenvolvido em **Kotlin** que permite consultar informações de endereços através do código postal (CEP).

## 📋 Índice

- [Visão Geral](#visão-geral)
- [Funcionalidades](#funcionalidades)
- [Requisitos](#requisitos)
- [Instalação](#instalação)
- [Uso](#uso)
- [Arquitetura](#arquitetura)
- [Mockups](#mockups)
- [Tecnologias](#tecnologias)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Contribuindo](#contribuindo)
- [Licença](#licença)

---

## 🎯 Visão Geral

O **App Consulta CEP** é uma aplicação mobile que facilita a busca de informações de endereços brasileiros. Com uma interface intuitiva, o usuário pode inserir um CEP e obter automaticamente:

- 🏠 Endereço completo
- 🏘️ Bairro
- 🏙️ Cidade
- 🗺️ Estado

A aplicação integra-se com APIs públicas para fornecer dados precisos e atualizados.

---

## ✨ Funcionalidades

### Funcionalidades Principais

- ✅ **Busca por CEP** - Insira um CEP para obter o endereço correspondente
- ✅ **Histórico de Buscas** - Acesso rápido aos CEPs consultados anteriormente
- ✅ **Validação de CEP** - Verifica o formato do CEP antes de enviar
- ✅ **Sugestões de Autocompletar** - Preenchimento automático de endereços
- ✅ **Interface Responsiva** - Design adaptável para diferentes tamanhos de tela
- ✅ **Busca Offline** - Consulte históricos mesmo sem conexão
- ✅ **Compartilhamento** - Compartilhe endereços encontrados

### Funcionalidades Secundárias

- 📊 Estatísticas de buscas
- 🎨 Temas claro/escuro
- 🔔 Notificações de atualizações
- ⭐ Favoritos/Marcadores

---

## 📱 Mockups

### Tela 1: Splash Screen / Onboarding

```
┌─────────────────────────────┐
│                             │
│          📍 CEP             │
│                             │
│    Consulta de Endereços    │
│                             │
│      Pressione para         │
│      continuar →            │
│                             │
└─────────────────────────────┘
```

### Tela 2: Tela Principal - Busca

```
┌─────────────────────────────────┐
│ ← ☰        App Consulta CEP  ⚙️ │
├─────────────────────────────────┤
│                                 │
│  📍 Buscar CEP                  │
│  ┌───────────────────────────┐  │
│  │ Digite o CEP (ex: 01310-100)│ │
│  └───────────────────────────┘  │
│              🔍 BUSCAR           │
│                                 │
├─────────────────────────────────┤
│  📌 BUSCAS RECENTES              │
│  ─────────────────────────────  │
│  01310-100 - Av. Paulista, SP   │
│  20040020 - Centro, Rio de J.   │
│  30140071 - Savassi, MG         │
│                                 │
├─────────────────────────────────┤
│  ⭐ FAVORITOS                     │
│  ─────────────────────────────  │
│  01310-100 - Av. Paulista       │
│                                 │
└─────────────────────────────────┘
```

### Tela 3: Resultado da Busca

```
┌─────────────────────────────────┐
│ ← 📍 01310-100            ⋯      │
├─────────────────────────────────┤
│                                 │
│  ✅ CEP ENCONTRADO              │
│                                 │
│  📮 Código Postal                │
│  01310-100                      │
│                                 │
│  🏠 Endereço                    │
│  Avenida Paulista               │
│                                 │
│  🏘️ Bairro                       │
│  Centro                         │
│                                 │
│  🏙️ Cidade                       │
│  São Paulo                      │
│                                 │
│  🗺️ Estado                       │
│  SP                             │
│                                 │
├─────────────────────────────────┤
│ ⭐ FAVORITAR  │ 📤 COMPARTILHAR   │
│              │                   │
│ 📋 COPIAR    │ 🔄 NOVA BUSCA    │
└─────────────────────────────────┘
```

### Tela 4: Histórico Detalhado

```
┌─────────────────────────────────┐
│ ←  📋 Histórico              🗑️  │
├─────────────────────────────────┤
│                                 │
│ 🔍 Filtrar histórico            │
│ ┌───────────────────────────┐   │
│ │ Buscar...                 │   │
│ └───────────────────────────┘   │
│                                 │
│ HOJE                            │
│ ─────────────────────────────   │
│ 01310-100 - Av. Paulista   11:45│
│ 20040020 - Centro          10:30│
│                                 │
│ ONTEM                           │
│ ─────────────────────��───────   │
│ 30140071 - Savassi         15:20│
│ 25970000 - Petrópolis      14:15│
│                                 │
└─────────────────────────────────┘
```

### Tela 5: Menu Lateral / Drawer

```
┌──────────────────────────────────┐
│ ╳                                │
├──────────────────────────────────┤
│                                  │
│ 👤 Allisson Bolo                │
│ allisson@email.com              │
│                                  │
├──────────────────────────────────┤
│ 🏠 Início                         │
│ 📋 Histórico                      │
│ ⭐ Favoritos                      │
│ ⚙️ Configurações                  │
│ ℹ️ Sobre                          │
│ 📧 Contato                        │
│ 🔗 Política de Privacidade       │
│                                  │
├──────────────────────────────────┤
│ 🌙 Modo Escuro (ON/OFF)          │
│                                  │
│               [Sair]             │
│                                  │
└──────────────────────────────────┘
```

### Tela 6: Configurações

```
┌─────────────────────────────────┐
│ ← ⚙️ Configurações            ✓  │
├─────────────────────────────────┤
│                                 │
│ APARÊNCIA                       │
│ ─────────────────────────────   │
│ 🌙 Tema Escuro          [ON/OFF]│
│ 📏 Tamanho da Fonte     [ ◀ M ▶]│
│                                 │
│ NOTIFICAÇÕES                    │
│ ─────────────────────────────   │
│ 🔔 Notificações         [ON/OFF]│
│ 📤 Sons                 [ON/OFF]│
│ 📳 Vibração             [ON/OFF]│
│                                 │
│ DADOS                           │
│ ─────────────────────────────   │
│ 🗑️ Limpar Histórico             │
│ 🗑️ Limpar Cache                 │
│ 💾 Fazer Backup                 │
│                                 │
│ SOBRE                           │
│ ─────────────────────────────   │
│ Versão: 1.0.0                  │
│ Build: 001                      │
│                                 │
└─────────────────────────────────┘
```

### Tela 7: Erro de Conexão / CEP Não Encontrado

```
┌─────────────────────────────────┐
│ ← 📍 Buscar CEP            ⚙️     │
├─────────────────────────────────┤
│                                 │
│           ⚠️ ERRO               │
│                                 │
│  CEP não encontrado ou           │
│  formato inválido.              │
│                                 │
│  Digite um CEP válido:          │
│  XXXXX-XXX                      │
│                                 │
│  ┌───────────────────────────┐  │
│  │ 01310-100                 │  │
│  └───────────────────────────┘  │
│                                 │
│    [TENTAR NOVAMENTE] [VOLTAR]  │
│                                 │
└─────────────────────────────────┘
```

---

## 🛠️ Requisitos

- **Android Mínimo**: API 21+ (Android 5.0)
- **Kotlin**: 1.8.0+
- **Gradle**: 8.0+
- **Java**: JDK 11+

### Dependências Principais

- AndroidX (AppCompat, ConstraintLayout)
- Retrofit 2 (requisições HTTP)
- OkHttp (cliente HTTP)
- Room Database (persistência local)
- LiveData & ViewModel (arquitetura)
- Coroutines (programação assíncrona)

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
3. Navegue até a pasta clonada
4. Clique em **OK**

### 3. Sincronizar Gradle

```bash
./gradlew build
```

### 4. Executar

- Conecte um dispositivo Android ou inicie um emulador
- Pressione **Run** (Shift + F10)

---

## 💻 Uso

### Buscar um CEP

1. **Abra o aplicativo**
2. **Digite o CEP** no campo de entrada (com ou sem hífen)
3. **Clique em "BUSCAR"** ou pressione Enter
4. **Visualize os resultados** com o endereço completo

### Exemplos de CEPs

| CEP | Endereço | Cidade |
|-----|----------|--------|
| 01310-100 | Av. Paulista | São Paulo - SP |
| 20040020 | Av. Rio Branco | Rio de Janeiro - RJ |
| 30140071 | Av. Getúlio Vargas | Belo Horizonte - MG |

### Acessar Histórico

1. Toque no ícone **📋** no menu inferior
2. Veja todos os CEPs que você já consultou
3. Clique em qualquer item para ver os detalhes novamente

### Usar Favoritos

1. Ao visualizar um resultado, clique em **⭐ FAVORITAR**
2. Acesse seus favoritos no menu lateral
3. Remova um favorito deslizando para a esquerda

---

## 🏗️ Arquitetura

### Padrão MVVM (Model-View-ViewModel)

```
┌─────────────────────────────────────┐
│           View (UI)                 │
│  (Activities, Fragments)            │
└──────────────┬──────────────────────┘
               │ Observa
               ▼
┌─────────────────────────────────────┐
│      ViewModel (Lógica)             │
│  (Gerencia estado & dados)          │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│   Repository (Fonte de Dados)       │
│  (API, Local DB)                    │
└─────────────────────────────────────┘
```

### Estrutura de Diretórios

```
app/
├── src/
│   ├── main/
│   │   ├── kotlin/
│   │   │   └── com/cep/
│   │   │       ├── ui/
│   │   │       │   ├── activities/
│   │   │       │   │   └── MainActivity.kt
│   │   │       │   ├── fragments/
│   │   │       │   │   ├── SearchFragment.kt
│   │   │       │   │   ├── HistoryFragment.kt
│   │   │       │   │   └── FavoritesFragment.kt
│   │   │       │   └── adapter/
│   │   │       │       ├── HistoryAdapter.kt
│   │   │       │       └── FavoritesAdapter.kt
│   │   │       ├── viewmodel/
│   │   │       │   └── CepViewModel.kt
│   │   │       ├── model/
│   │   │       │   ├── Address.kt
│   │   │       │   └── SearchResult.kt
│   │   │       ├── repository/
│   │   │       │   └── AddressRepository.kt
│   │   │       ├── network/
│   │   │       │   ├── ApiClient.kt
│   │   │       │   └── CepApiService.kt
│   │   │       ├── database/
│   │   │       │   ├── AppDatabase.kt
│   │   │       │   ├── dao/
│   │   │       │   │   └── AddressDao.kt
│   │   │       │   └── entity/
│   │   │       │       └── AddressEntity.kt
│   │   │       └── utils/
│   │   │           ├── Constants.kt
│   │   │           ├── Extensions.kt
│   │   │           └── CepValidator.kt
│   │   └── res/
│   │       ├── layout/
│   │       ├── drawable/
│   │       ├── values/
│   │       └── menu/
│   └── test/
└── build.gradle.kts
```

---

## 🛠️ Tecnologias

| Tecnologia | Versão | Descrição |
|-----------|--------|-----------|
| **Kotlin** | 1.8.0+ | Linguagem de programação |
| **AndroidX** | Latest | Framework Android moderno |
| **Retrofit** | 2.9.0 | Cliente HTTP tipo-seguro |
| **OkHttp** | 4.10.0 | Cliente HTTP com interceptadores |
| **Room** | 2.5.2 | Banco de dados local |
| **LiveData** | 2.5.1 | Componente de dados observáveis |
| **ViewModel** | 2.5.1 | Gerenciamento de ciclo de vida |
| **Coroutines** | 1.7.1 | Programação assíncrona |
| **Gson** | 2.10.1 | Serialização JSON |
| **Material Design** | 3.0+ | Sistema de design |

---

## 📡 API Utilizada

### ViaCEP API

**Endpoint**: `https://viacep.com.br/ws/{cep}/json/`

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

## 🚀 Recursos Futuros

- [ ] Busca reversa (localidade → CEP)
- [ ] Exportar dados em PDF
- [ ] Integração com mapas (Google Maps)
- [ ] Busca por endereço aproximado
- [ ] Multi-idiomas (EN, ES)
- [ ] Autenticação e sincronização na nuvem
- [ ] Widget para busca rápida

---

## 🐛 Troubleshooting

### Problema: "CEP Não Encontrado"
- Verifique se o CEP está no formato correto: `XXXXX-XXX`
- Certifique-se de que o CEP existe no Brasil
- Tente remover o hífen: `XXXXXBXXX`

### Problema: "Erro de Conexão"
- Verifique sua conexão com a internet
- Tente novamente em alguns momentos
- Verifique se o servidor ViaCEP está online

### Problema: App Lento
- Limpe o cache: Configurações → Dados → Limpar Cache
- Reinicie o aplicativo
- Verifique se você tem espaço suficiente no dispositivo

---

## 🤝 Contribuindo

Contribuições são bem-vindas! Siga os passos:

1. **Fork** o projeto
2. **Crie uma branch** para sua feature (`git checkout -b feature/AmazingFeature`)
3. **Commit** suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. **Push** para a branch (`git push origin feature/AmazingFeature`)
5. **Abra um Pull Request**

### Padrões de Código

- Siga o [Kotlin Style Guide](https://kotlinlang.org/docs/coding-conventions.html)
- Use nomes descritivos para variáveis e funções
- Adicione comentários para lógica complexa
- Mantenha funções pequenas e focadas

---

## 📄 Licença

Este projeto está sob a licença **MIT**. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## 📧 Contato

**Autor**: Allisson Bolo  
**Email**: [seu-email@example.com]  
**GitHub**: [@AllissonBolo](https://github.com/AllissonBolo)  
**LinkedIn**: [Allisson Bolo](https://linkedin.com/in/seu-perfil)

---

## 📝 Changelog

### v1.0.0 (2026-09-11)
- ✨ Release inicial
- ✅ Funcionalidade de busca por CEP
- ✅ Histórico de buscas
- ✅ Favoritos
- ✅ Interface MVVM
- ✅ Suporte offline com Room Database

---

<div align="center">

**Feito com ❤️ por [AllissonBolo](https://github.com/AllissonBolo)**

⭐ Se este projeto foi útil, deixe uma estrela!

</div>