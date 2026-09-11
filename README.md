📱 AppConsultaCEP - Documentação Completa
🎯 Visão Geral
AppConsultaCEP é um aplicativo Android em Kotlin que permite consultar informações de endereços através de um CEP (Código de Endereçamento Postal) brasileiro, utilizando a API pública do ViaCEP.

📋 Funcionalidades
✅ Busca de endereço por CEP
✅ Validação de CEP (8 dígitos)
✅ Exibição de informações:

Logradouro
Bairro
Unidade Federativa (UF)
DDD (Código de área telefônico)
Cidade
🏗️ Arquitetura do Projeto
Code
AppConsultaCEP/
├── app/
│   ├── src/main/
│   │   ├── java/com/example/appconsultacep/
│   │   │   ├── MainActivity.kt          (Tela principal)
│   │   │   ├── api/
│   │   │   │   ├── ViaCepClient.kt      (Cliente Retrofit)
│   │   │   │   └── ViaCepService.kt     (Interface da API)
│   │   │   └── model/
│   │   │       └── ResponseEndereco.kt  (Modelo de dados)
│   │   └── res/
│   │       ├── layout/
│   │       │   └── activity_main.xml    (Layout da UI)
│   │       └── (recursos: drawable, font, values, etc)
│   └── build.gradle.kts                (Dependências)
└── settings.gradle.kts
🧩 Componentes
1️⃣ MainActivity.kt - Controlador Principal
Kotlin
class MainActivity : AppCompatActivity()
Responsabilidades:

Gerencia a interface com o usuário
Valida entrada do CEP (8 dígitos)
Faz requisição à API ViaCEP
Preenche os campos com os dados recebidos
2️⃣ ViaCepClient.kt - Singleton do Retrofit
Kotlin
object ViaCepClient
Responsabilidades:

Instancia o cliente Retrofit uma única vez
Define a URL base: https://viacep.com.br
Configura conversor JSON (Gson)
3️⃣ ViaCepService.kt - Interface da API
Kotlin
interface ViaCepService
Método:

Kotlin
@GET("ws/{cep}/json/")
suspend fun buscarEndereco(@Path("cep") cep: String): ResponseEndereco
4️⃣ ResponseEndereco.kt - Data Class
Kotlin
data class ResponseEndereco(
    val logradouro: String,
    val bairro: String,
    val uf: String,
    val localidade: String,
    val ddd: String
)
🎨 Layout da Tela Principal
XML
activity_main.xml
Cores e Estilo:

🎨 Background: #FFEAE6 (Rosa claro)
🔴 Título: #854646 (Marrom)
🟠 Botão: #750404 (Marrom escuro)
Componentes:

✍️ EditText para CEP - Entrada numérica
🔘 Botão CONSULTAR - Dispara busca
📝 5 EditTexts de saída - Logradouro, Bairro, UF, DDD, Cidade
📱 MOCKUP DA TELA PRINCIPAL
Code
┌─────────────────────────────────┐
│                                 │
│      Consulta de CEP            │  ← Título (24sp, bold)
│                                 │
│  ┌──────────────────────────┐   │
│  │ Digite seu CEP           │   │  ← TextInputLayout
│  │ [            ]           │   │
│  └──────────────────────────┘   │
│                                 │
│  ┌──────────────────────────┐   │
│  │     CONSULTAR            │   │  ← Botão (marrom escuro)
│  └──────────────────────────┘   │
│                                 │
│  Logradouro:  [            ]    │
│                                 │
│  Bairro:      [            ]    │
│                                 │
│  UF:          [            ]    │
│                                 │
│  DDD:         [            ]    │
│                                 │
│  Cidade:      [            ]    │
│                                 │
└─────────────────────────────────┘
🔧 Dependências
Gradle
// Retrofit 2 - Cliente HTTP
implementation("com.squareup.retrofit2:retrofit:2.11.0")
implementation("com.squareup.retrofit2:converter-gson:2.11.0")

// AndroidX e Material
implementation(libs.androidx.core.ktx)
implementation(libs.androidx.appcompat)
implementation(libs.material)
implementation(libs.androidx.constraintlayout)
🚀 Como Usar
Inserir CEP - Digite um CEP válido com 8 dígitos (ex: 01311100)
Clicar em CONSULTAR - O app buscará as informações na API ViaCEP
Ver Resultado - Os campos serão preenchidos automaticamente com:
Logradouro (rua/avenida)
Bairro
Estado (UF)
DDD
Localidade (cidade)
🌐 API Utilizada
ViaCEP - https://viacep.com.br

Code
Endpoint: GET /ws/{cep}/json/
Exemplo: https://viacep.com.br/ws/01311100/json/
✨ Tecnologias
Linguagem: Kotlin
Framework Android: Android 24+ (API Level 24)
Padrão de Requisição: Retrofit 2 + Coroutines
Serialização: Gson
Layout: ConstraintLayout com Material Design
Status: ✅ Projeto funcional e pronto para uso!
