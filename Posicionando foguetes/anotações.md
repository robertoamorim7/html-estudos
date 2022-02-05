# Page Layouts
- tables
- floats e clear
- frameworks e grid systems
- flexbox
- grid

## Posicionamentos

Controlar onde, na página, o elemento irá ficar, alterando o fluxo normal dos elementos.

- name: position
- value: static|relative|absolut|fixed

Por padrão todos são static. Isso significa que os elementos irão seguir o fluxo normal do HTML.

==================================================================
## relative
O position indica onde o elemento vai ser posicionado na página. Ao usar o position podemos adicionar outras propriedades como top, right, bottom, left e z-index, que vão determinar o posicionamento final do elemento.

Quando o position é relative os elementos são deslocados do seu posicionamento normal, mas sem afetar o posicionamento de outros elementos da página.

```css
    .box {
  width: 50px;
  height: 50px;
  margin-bottom: 8px;
}

.box1 {
  background-color: red;
  position: relative;
  left: 100px;
  top: 80px
}

.box2 {
  background-color: green;
}

.box3 {
  background-color: blue;
}
```
```html
    <div class="box box1"></div>
    <div class="box box2"></div>
    <div class="box box3"></div>
```
================================================================
## absolute
Quando o position é absolute o elemento é deslocado saindo do fluxo normal. O elemento de position absolute é posicionado em relação ao seu parent element mais próximo. Se esse elemento "pai" não existir, ele será posicionando em relação ao bloco contendo a raiz do elemento.
```css
.box {
  width: 50px;
  height: 50px;
  margin-bottom: 8px;
}

.box1 {
  background-color: red;
  position: absolute;
  left: 100px;
  top: 80px
}

.box2 {
  background-color: green;
}

.box3 {
  background-color: blue;
}
```
=================================================================
## fixed
Quando aplicado o position fixed é como se criasse um elemento flutuante que fica fixo na página, independente do scrolling feito.
================================================================

## element stacking
É o empilhamento de elementos. Podemos usar o z-index para determinar a ordem da posição do elemento. Quanto maior o z-index, mais "acima" vai aparecer o elemento.

```html
<div class="box box1"></div>
<div class="box box2"></div>
<div class="box box3"></div>
```
```css
.box {
  width: 50px;
  height: 50px;
  margin-bottom: 8px;
}

.box1 {
  background-color: red;
  position: absolute;
  left: 5px;
  top: 5px;
  z-index: 3;
}

.box2 {
  background-color: green;
  position: absolute;
  left: 10px;
  top: 10px
}

.box3 {
  background-color: blue;
  position: absolute;
  left: 15px;
  top: 15px
}
```
=============================================================

# Flexbox
- Nos permite posicionar os elementos dentro da caixa
- Controle em uma dimensão (horizontal ou vertical)
- Alinhamento, direcionamento, ordenar e tamanhos

```css
div.parent {
	display: flex;
}
```

## flex-direction
-Qual a direção do flex: horizontal ou vertical
-row | column

## alinhamento
-justify-content
-align-items

===============================================================

# Grid
- posicionamento dos elementos dentro da caixa
- posicionamento horizontal e vertical ao mesmo tempo
- pode ser flexível ou fixo
- cria espaços para os elementos filhos habitarem

```html
<body>
    <head>Topo</head>
    <main>Conteúdo</main>
    <aside>Infos adicionais</aside>
    <footer>Rodapé</footer>
</body>
```
```css
body {
    margin: 0;
    height: 100vh;
    display: grid;
    grid-template-areas:
        "header header"
        "main aside"
        "footer footer";

    grid-template-rows: 30px 1fr 40px;
    grid-template-columns: 1fr 80px;
}
header {
    grid-area: header;
    background-color: green;
}
main {
    grid-area: main;
    background-color: red;
}
aside {
    grid-area: aside;
    background-color: blue;
}
footer {
    grid-area: footer;
    background-color: gray;
}
```
===========================================================

# Grid ou Flexbox
Podemos usar o Display Flex e Display Grid ao mesmo tempo.

```html
<body>
    <header>
        <div>Logo</div>
        <div>Menu</div>
    </header>
    <main>Conteúdo</main>
    <aside>Infos adicionais</aside>
    <footer>Rodapé</footer>
</body>
```

```css
body {
    margin: 0;
    height: 100vh;
    display: grid;
    grid-template-areas: 
    "header header"
    "main aside"
    "footer footer";
    grid-template-rows: 30px 1fr 40px;
    grid-template-columns: 1fr 80px;
}

header {
    grid-area: header;
    background-color: green;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 8px;
}

main {
    grid-area: main;
    background-color: red;
}

aside {
    grid-area: aside;
    background-color: blue;
}

footer {
    grid-area: footer;
    background-color: gray;
}
```