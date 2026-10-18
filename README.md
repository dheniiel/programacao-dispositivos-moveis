# Programação para Dispositivos Móveis

Exercícios e projetos da disciplina **Programação para Dispositivos Móveis** (6º período de Sistemas de Informação, IF Goiano, Campus Ceres), desenvolvidos em **Dart** e **Flutter**.

Os exemplos usam o contexto agrícola da região: talhões, culturas (soja, milho, sorgo), cotação da saca e alqueire goiano. Eles fazem parte do **Caderno de Campo do Vale**, um app de registro de atividades agrícolas construído ao longo do semestre.

## Tecnologias

- Dart 3
- Flutter (Material 3)
- VS Code e DartPad

## Estrutura

```
ProgramacaoDispositivosMoveis/
├── blocoA/                            Variáveis, tipos, const/final e funções
├── blocoB/                            Null safety
├── blocoC/                            Strings
├── blocoD/                            Condicionais e laços
├── aula-03-widgets-layout/            Widgets de layout (exercicios/ + projeto-inicial/)
├── aula-04-calculadora-guiada/        App: Calculadora de Receita da Lavoura
└── funcionalidade_cardeno_de_campo/   App: Comparador de Propostas de Venda
```

## Exercícios de Dart

### Bloco A: variáveis e funções

| Arquivo | O que faz |
|---|---|
| `exercicioUm` | Declara os dados de um produtor com tipos explícitos e os exibe com interpolação. |
| `exercicioDois` | Mesmo exercício com `var`, mostrando o tipo inferido com `runtimeType`. |
| `exercicioTres` | Compara `const` (tempo de compilação) e `final` (tempo de execução). |
| `exercicioQuarto` | Converte uma área entre alqueire goiano e hectares (fator 4,84). |
| `exercicioCinco` | Encontra a maior, a menor e a média de três cotações. |

### Bloco B: null safety

| Arquivo | O que faz |
|---|---|
| `exercicioUm` | Usa `??` para exibir um valor padrão quando o telefone é nulo. |
| `exercicioDois` | Usa `?.` para acessar uma propriedade de uma variável que pode ser nula. |
| `exercicioTres` | Classifica a chuva (sem registro, seca ou normal) a partir de um `double?`. |
| `exercicioQuatro` | Calcula sacas por hectare e retorna `null` quando a área é inválida. |
| `exercicioCinco` | Mostra o erro gerado ao usar `!` em um valor nulo. |

### Bloco C: strings

| Arquivo | O que faz |
|---|---|
| `exercicioUm` | Concatena partes de uma frase. |
| `exercicioDois` | Formata um valor em reais. |
| `exercicioTres` | Exibe um endereço em várias linhas com `\n`. |
| `exercicioQuatro` | Converte uma string de culturas em lista com `split`, `trim` e `toUpperCase`. |

### Bloco D: controle de fluxo

| Arquivo | O que faz |
|---|---|
| `exercicioUm` | Classifica a produtividade (baixa, média, alta) com `if / else`. |
| `exercicioDois` | Mesma classificação com `switch` e padrões relacionais. |
| `exercicioTres` | Gera uma tabela de conversão de 10 a 100 hectares com `for`. |
| `exercicioQuatro` | Conta em quantos dias um estoque de 5000 unidades se esgota. |

## Aula 03: widgets de layout

Exercícios em ciclos para montar a primeira tela do Caderno de Campo:

| Ciclo | Conteúdo |
|---|---|
| 1 | `Column`, `Row`, `Container`, `Padding` e `SizedBox`: cabeçalho da propriedade. |
| 2 | `Expanded` e `Flexible`: correção de erros de *overflow*. |
| 3 | `ListView.builder`: lista rolável de talhões. |
| 4 | Tela de resumo juntando cabeçalho, cards de números e lista de talhões. |

A pasta `exercicios/` tem os arquivos de cada ciclo e as versões resolvidas. O `projeto-inicial/` é o projeto Flutter da tela de resumo.

## Aula 04: Calculadora de Receita da Lavoura

App em que o produtor informa área (ha), produtividade (sacas/ha) e cotação da saca (R$), e recebe a receita bruta estimada:

```
receita = área × produtividade × cotação
```

- `StatefulWidget` e `setState` para atualizar a tela
- `TextEditingController` em cada campo, liberados no `dispose()`
- Validação de campos vazios, inválidos ou menores ou iguais a zero
- Aceita vírgula ou ponto como separador decimal
- Resultado formatado no padrão brasileiro (`R$ 1.250,50`)
- Botões **Calcular** e **Limpar**

## Funcionalidade: Comparador de Propostas de Venda

Funcionalidade do Caderno de Campo para comparar propostas de compra de sacas:

- Cadastro de propostas com comprador, preço da saca (R$) e prazo de pagamento (dias)
- Validação em tempo real com `onChanged` e `errorText`
- Botão **Inserir** habilitado apenas quando o formulário é válido
- Lista ordenada automaticamente do maior para o menor preço
- Exclusão de propostas e limpeza do formulário
- Dados mantidos apenas em memória

## Como executar

**Exercícios de Dart** (blocos A a D):

```bash
dart run blocoA/exercicioUm.dart
```

Ou cole o código no [DartPad](https://dartpad.dev).

**Projetos Flutter** (pré-requisito: Flutter SDK, verificado com `flutter doctor`):

```bash
cd aula-04-calculadora-guiada     # ou funcionalidade_cardeno_de_campo
flutter pub get
flutter run
```

Para o `aula-03-widgets-layout/projeto-inicial`, rode `flutter create .` antes, pois as pastas nativas não estão versionadas. Os arquivos de `aula-03-widgets-layout/exercicios/` também rodam no DartPad, no modo Flutter.

## Autor

Dheniel ([@dheniiel](https://github.com/dheniiel))
