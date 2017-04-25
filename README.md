# SPACE ADSERVER
## rocket.js
### Como usar?
Inclua o rocket2.js no seu projeto
```demo
<script src="https://cdn.00px.net/static/rocket2.min.js"></script>
```

#### Exemplos

+ [Banner HTML5](https://yvesroos.github.io/templates/html5/index.html)
+ [Banner HTML5 floating com botão de fechar](https://yvesroos.github.io/templates/floating/index.html)
+ [Banner HTML5 floating com botão de fechar customizado](https://yvesroos.github.io/templates/floating_custom/index.html)
+ [Banner HTML5 floating com fechamento automático](https://yvesroos.github.io/templates/floating_timeout/index.html)
+ [Banner HTML5 expansível](https://yvesroos.github.io/templates/expansivel/index.html)

#### Propriedades
Muitas das propriedades declaradas abaixo podem ser invocadas como métodos caso isso facilite a interpretação

```
var config = {
  //LARGURA (EM PX, OBRIGATÓRIO)
  width: 300,

  //ALTURA (EM PX, OBRIGATÓRIO)
  //height: 250,

  //ELEMENTO PARA O PARA REDIRECIONAR
  //É USADO EM PRATICAMENTE TODOS OS BANNERS
  //PODE SER USADO O OBJETO Element, O ID COM '#id', '.class'. CASO SEJA SEM
  //NENHUM PREFIXO ELE IRÁ PROCURAR PELO ELEMENTO COM O ID CORRESPONDENTE
  clickElement:'banner',

  //LARGURA QUANDO EXPANDIR (EM PX)
  // expanded_width: 300,

  //LARGURA QUANDO EXPANDIR (EM PX)
  // expanded_height: 500,

  //CRIAÇÃO AUTOMATICAMENTE DO BOTÃO DE FECHAR
  //closeButton: false,

  //IMAGEM CUSTOMIZADA PARA O BOTÃO DE FECHAR
  //(DEVE SER PASSADO O CAMINHO RELATIVO A PASTA RAIZ DO BANNER)
  //btnImage: '',

  //O BANNER DEVE APARECER CENTRALIZADO
  //centralize: false,

  //O BANNER DEVE APARECER CENTRALIZADO VERTICALMENTE
  //centralizeY: false,

  //O BANNER DEVE APARECER CENTRALIZADO HORIZONTALMENTE
  //centralizeX: false,

  //POSIÇÃO FIXA COM DISTÂNCIA DE X PX A PARTIR DO TOPO (EM PX)
  //appendTop: 0,

  //POSIÇÃO FIXA COM DISTÂNCIA DE X PX A PARTIR DEBAIXO (EM PX)
  //appendBottom: 0,

  //POSIÇÃO FIXA COM DISTÂNCIA DE X PX A PARTIR DA DIREITA (EM PX)
  //appendRight: 0,

  //POSIÇÃO FIXA COM DISTÂNCIA DE X PX A PARTIR DA ESQUERDA (EM PX)
  //appendLeft: 0,

  //TEMPO PARA O BANNER FECHAR AUTOMATICAMENTE (EM MILISEGUNDOS)
  //closeTimeout: 1500,
}

new Rocket(config)
```

#### Métodos
Todos os métodos disponíveis

setClickElement(element:String|Object) :[this]
```
// Seta qual a área clicavel do banner *tem que ser o id do element
new Rocket(config).setClickElement(document.getElementById('id')) ou
new Rocket(config).setClickElement('id') ou
new Rocket(config).setClickElement('#id') ou
new Rocket(config).setClickElement('.class')
```
close() :[this]
```
//Método para fechar o banner
var rocket = new Rocket(config)
rocket.close()
```
centralize() :[this]
```
// Centraliza o banner
new Rocket(config).centralize()
```
centralizeY() :[this]
```
// Centraliza o banner verticalmente
new Rocket(config).centralizeY()
```
centralizeX() :[this]
```
// Centraliza o banner horizontalmente
new Rocket(config).centralizeX()
```
appendTop(timer:Integer) :[this]
```
// Ajusta o banner com distância de X px do topo
new Rocket(config).appendTop(15)
```
appendBottom(timer:Integer) :[this]
```
// Ajusta o banner com distância de X px de baixo
new Rocket(config).appendBottom(15)
```
appendLeft(timer:Integer) :[this]
```
// Ajusta o banner com distância de X px da esquerda
new Rocket(config).appendLeft(15)
```
appendRight(timer:Integer) :[this]
```
// Ajusta o banner com distância de X px da direita
new Rocket(config).appendRight(15)
```
setCloseButton(imageButton:String = undefined, text:String = 'Fechar X') :[this]
```
// Seta o botão de fechar, pode ser informado o caminho relativo da
// imagem do botão ou o texto que deseja aparecer no botão
new Rocket(config).setCloseButton('images/fechar.png', 'Fechar X')
```
setCloseElement(closeButtonID:String) :[this]
```
// Seta qual é o elemento que fecha o banner
new Rocket(config).setCloseElement(document.getElementById('id')) ou
new Rocket(config).setCloseElement('id') ou
new Rocket(config).setCloseElement('#id') ou
new Rocket(config).setCloseElement('.class')
```
setCloseTimeout(timer:Integer) :[this]
```
// Seta em quanto tempo o banner será fechado
new Rocket(config).setCloseTimeout(1500)
```
expand(widthExpanded:Integer, heightExpanded:Integer) :[this]
```
// Método que deve ser invocado quando o banner precisar expandir
var rocket = new Rocket(config)
rocket.expand(300,600)
```
collapse() :[this]
```
// Método que deve ser invocado quando o banner precisar retrair
var rocket = new Rocket(config)
rocket.collapse()
```

#### Exemplo
```demo
<script src="https://cdn.00px.net/static/rocket2.min.js"></script>
<script type="text/javascript">
  //PADRÃO
  var rocket = new ROCKET({width: 300, height: 250}).setClickElement("banner");
  //EXPAND
  document.getElementById("divCollapsed").addEventListener("mouseenter", function(){
    rocket.expand(300,600);
  });
  //COLLAPSE
  document.getElementById("divExpanded").addEventListener("mouseout", function(){
    rocket.collapse();
  });
</script>
```