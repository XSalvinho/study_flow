# 📚 StudyFlow

Aplicativo de estudos desenvolvido em **Flutter** que organiza o conteúdo por áreas do conhecimento e permite praticar com **questões reais do ENEM**, consumidas de uma API pública.

![Flutter](https://img.shields.io/badge/Flutter-3.x-02569B?logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-3.13+-0175C2?logo=dart&logoColor=white)
![Material 3](https://img.shields.io/badge/Material-3-red)

---

## ✨ Funcionalidades

- **Áreas de estudo:** Matemática, Linguagens, Ciências Humanas e Ciências da Natureza, cada uma com sua lista de conteúdos.
- **Filtro por nível:** filtre os conteúdos de cada área por *Básico*, *Intermediário* ou *Avançado*.
- **Detalhe do conteúdo:** tela com título, nível e descrição do tema.
- **Questões do ENEM:** lista de questões carregadas da [api.enem.dev](https://docs.enem.dev/).
- **Resolução de questões:** leia o enunciado (com imagens, quando houver), escolha uma alternativa e veja na hora se acertou, junto com o gabarito.
- **Tratamento de erros:** indicador de carregamento, mensagem de falha e botão **Tentar novamente** caso a API não responda.

## 🧭 Fluxo de navegação

```
HomePage
 ├── Questões do ENEM ─► EnemPage ─► QuestaoEnemPage
 └── Área de estudo ───► MateriaPage ─► ConteudoPage
```

## 🛠️ Tecnologias

| Tecnologia | Uso |
|---|---|
| [Flutter](https://flutter.dev/) / Dart | Interface e lógica do app |
| Material 3 | Design (tema gerado a partir de uma cor base) |
| [`http`](https://pub.dev/packages/http) | Requisições à API do ENEM |
| [api.enem.dev](https://docs.enem.dev/) | Fonte das questões |

## 📁 Estrutura do projeto

```
lib/
├── main.dart                  # Ponto de entrada e tema do app
├── data/
│   └── dados_estudo.dart      # Matérias e conteúdos (dados locais)
├── models/
│   ├── materia.dart
│   ├── conteudo.dart
│   └── questao_enem.dart      # Questão e alternativas (com fromJson)
├── services/
│   └── enem_service.dart      # Comunicação com a API do ENEM
├── screens/
│   ├── home_page.dart
│   ├── materia_page.dart
│   ├── conteudo_page.dart
│   ├── enem_page.dart
│   └── questao_enem_page.dart
└── widgets/
    ├── materia_card.dart
    └── conteudo_card.dart
```

## 🚀 Como executar

### Pré-requisitos

- [Flutter SDK](https://docs.flutter.dev/get-started/install) com Dart `^3.13.0`
- Um emulador, dispositivo físico ou navegador configurado

### Passo a passo

```bash
# 1. Clone o repositório
git clone https://github.com/SEU-USUARIO/study_flow.git

# 2. Entre na pasta do projeto
cd study_flow

# 3. Instale as dependências
flutter pub get

# 4. Execute o app
flutter run
```

Para rodar em uma plataforma específica:

```bash
flutter run -d chrome    # Web
flutter run -d windows   # Windows
```

> As questões do ENEM precisam de **conexão com a internet**.

## 🔌 API utilizada

As questões são buscadas em:

```
GET https://api.enem.dev/v1/exams/{ano}/questions?limit=10&offset=0
```

O serviço (`EnemService`) busca por padrão as **10 primeiras questões** da prova de **2022**, com timeout de 15 segundos.

## 🗺️ Próximos passos

- [ ] Escolher o ano da prova e paginar as questões
- [ ] Salvar o progresso e o histórico de acertos
- [ ] Adicionar mais conteúdos e explicações detalhadas
- [ ] Adicionar testes automatizados

## 👤 Autor

Feito por **Leonardo** — estudante de desenvolvimento de software no SENAI.

[GitHub](https://github.com/SEU-USUARIO)

## 📄 Licença

Projeto desenvolvido para fins de estudo. Defina a licença que preferir (por exemplo, MIT) antes de publicar.
