# MeuLayoutApp

Aplicativo desenvolvido em **Flutter e Dart** para praticar a construção e organização de interfaces utilizando diferentes widgets de layout.

O projeto apresenta um dashboard de observações, trabalhando conceitos como `Row`, `Column`, `Expanded`, `Stack`, `Positioned`, `Card`, `GridView`, alinhamento e criação de widgets personalizados.

A aplicação foi desenvolvida de forma incremental através de uma versão base e **8 exercícios de fixação**.

---

## Versão Base — V.0.0

A versão inicial apresentava um dashboard com o título **"Resumo das Observações"** e uma primeira linha contendo cards de estatísticas.

Também havia uma seção de **"Destaque da Semana"**, utilizando um card com informações sobre uma observação.

A estrutura principal utilizava widgets como:

- `Scaffold`
- `AppBar`
- `SingleChildScrollView`
- `Column`
- `Row`
- `Card`
- `Container`
- `Icon`
- `Text`
- `Stack`
- `Positioned`

Nessa versão, os cards de estatísticas ainda eram construídos diretamente na tela, sem um widget separado para reutilização.

---

## Exercício 01 — V.0.0.1

### Objetivo

Adicionar um terceiro card na primeira linha de estatísticas.

### O que mudou

Foi adicionado um novo card contendo:
Icon(Icons.camera_alt)
A contagem:
45
e a legenda:
Fotos
O Expanded foi utilizado para manter a proporção entre as três colunas da Row.

### Resultado
A primeira linha passou a apresentar três estatísticas:
Aves Vistas
Locais Visitados
Fotos

## Exercício 02 — V.0.0.2

### Objetivo

Alterar o alinhamento da Column principal.

### O que mudou

A propriedade:
crossAxisAlignment
da Column principal foi alterada de:
CrossAxisAlignment.start
para:
CrossAxisAlignment.center

### Resultado
Os elementos da tela passaram a ser centralizados no eixo cruzado da Column, alterando a forma como os componentes são posicionados horizontalmente.

## Exercício 03 — V.0.0.3

### Objetivo

Adicionar uma nova seção chamada "Últimos Registros" no final da tela.

### O que mudou

Foi criado um Container contendo uma Row.
A Row possui:
um ícone de lista;
o texto "Últimos Registros";
um botão "Ver todos".
Para distribuir os elementos nas extremidades da linha foi utilizada:
mainAxisAlignment: MainAxisAlignment.spaceBetween

### Resultado
A tela passou a apresentar uma nova seção de registros na parte inferior do dashboard.

## Exercício 04 — V.0.0.4

### Objetivo

Provocar propositalmente um erro de overflow no layout.

### O que mudou
O exercício consiste em remover o Expanded de um elemento da Row e inserir um texto extremamente longo dentro dele.

### Resultado

A alteração provoca um estouro horizontal de espaço no layout.
No navegador, o Flutter passa a apresentar as conhecidas faixas amarelas e pretas de overflow, indicando que o conteúdo ultrapassou o espaço disponível.
O exercício serviu para compreender a importância do Expanded na distribuição de espaço dentro de uma Row.

## Exercício 05 — V.0.0.5

### Objetivo

Adicionar um segundo selo sobreposto ao Card de Destaque.

### O que mudou
Foi adicionado um novo Positioned dentro do Stack, localizado no canto inferior esquerdo do card.
O selo contém:
Confirmado
e utiliza fundo verde:
color: Colors.green

### Resultado

O Card de Destaque passou a possuir dois selos:
Raro, no canto superior direito;
Confirmado, no canto inferior esquerdo.
Foi utilizado o Stack junto com Positioned para realizar a sobreposição dos elementos.

## Exercício 06 — V.0.0.6

### Objetivo

Substituir o fundo simples do destaque por um widget Card do Material.

### O que mudou
O conteúdo do destaque passou a ser envolvido por:
Card(
  elevation: 4,
  ...
)
A propriedade:
elevation: 4
foi utilizada para criar um efeito de elevação no card.

### Resultado
O destaque passou a utilizar um Card do Material com elevação, deixando a estrutura visual mais próxima dos componentes padrões do Flutter.
Os selos continuaram sobrepostos através do Stack.

## Exercício 07 — V.0.0.7

### Objetivo

Separar a estrutura dos cards de estatísticas em um widget personalizado.

### O que mudou

A estrutura dos cards de estatísticas foi extraída para um novo widget chamado:
BlocoEstatistica
Foi criado o arquivo:
lib/widgets/bloco_estatistica.dart
O widget passou a receber os dados de cada estatística por parâmetros, como:
icone
quantidade
legenda
cor
No main.dart, o widget passou a ser utilizado desta forma:
BlocoEstatistica(
  icone: Icons.camera_alt,
  quantidade: '45',
  legenda: 'Fotos',
  cor: Colors.teal.shade100,
)

### Resultado
A estrutura do código ficou mais organizada e reutilizável.
Em vez de repetir a estrutura de cada card, a aplicação passou a utilizar o mesmo widget BlocoEstatistica com diferentes valores.

## Exercício 08 — V.0.0.8

### Objetivo

Refatorar a seção de estatísticas utilizando GridView.count para organizar os quatro cards em uma grade 2x2.

### O que mudou

A estrutura anterior baseada em Row e Expanded foi substituída por:
GridView.count(
  crossAxisCount: 2,
)
Também foram definidos espaçamentos entre os cards:
crossAxisSpacing: 12.0,
mainAxisSpacing: 12.0,
Como o GridView está dentro de uma SingleChildScrollView, foram utilizados:
shrinkWrap: true,
physics: const NeverScrollableScrollPhysics(),
Os quatro cards passaram a utilizar o widget personalizado BlocoEstatistica.
As estatísticas apresentadas são:
124 — Aves Vistas
18 — Locais Visitados
45 — Fotos
32 — Registros

### Resultado
Os quatro cards passaram a ser exibidos em uma grade de 2 colunas por 2 linhas, deixando o layout mais organizado e substituindo a estrutura anterior de Row e Expanded.

## Histórico de Versões
Versão	Exercício	Alteração principal
V.0.0	Base	Dashboard inicial com estatísticas e destaque
V.0.0.1	Exercício 01	Adição do terceiro card de estatística
V.0.0.2	Exercício 02	crossAxisAlignment.center na Column principal
V.0.0.3	Exercício 03	Nova seção "Últimos Registros"
V.0.0.4	Exercício 04	Teste de overflow proposital
V.0.0.5	Exercício 05	Segundo selo "Confirmado" usando Stack
V.0.0.6	Exercício 06	Utilização de Card com elevation: 4
V.0.0.7	Exercício 07	Criação do widget BlocoEstatistica
V.0.0.8	Exercício 08	GridView.count com grade 2x2

### Estrutura Final do Projeto
lib/
├── main.dart
└── widgets/
    └── bloco_estatistica.dart

### Tecnologias Utilizadas
Flutter
Dart
Git
GitHub
