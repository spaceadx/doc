# SPACE ADSERVER
## rocket.js
### Como usar?
Inclua o rocket2.js no seu projeto
```demo
<script src="https://cdn.00px.net/static/2.4.3.9.min.js"></script>
```

#### Exemplos

+ [Banner HTML5](https://spaceadx.github.io/doc/html5/) - [Download](https://raw.githubusercontent.com/spaceadx/doc/master/examples/html5.zip)
+ [Banner HTML5 floating com botão de fechar](https://spaceadx.github.io/doc/floating/) - [Download](https://raw.githubusercontent.com/spaceadx/doc/master/examples/floating.zip)
+ [Banner HTML5 floating com botão de fechar customizado](https://spaceadx.github.io/doc/floating_custom/) - [Download](https://raw.githubusercontent.com/spaceadx/doc/master/examples/floating_custom.zip)
+ [Banner HTML5 floating com fechamento automático](https://spaceadx.github.io/doc/floating_timeout/) - [Download](https://raw.githubusercontent.com/spaceadx/doc/master/examples/floating_timeout.zip)
+ [Banner HTML5 expansível](https://spaceadx.github.io/doc/expansivel/) - [Download](https://raw.githubusercontent.com/spaceadx/doc/master/examples/expansivel.zip)
+ [Banner HTML5 expansível para a lateral](https://spaceadx.github.io/doc/expansivel_left/) - [Download](https://raw.githubusercontent.com/spaceadx/doc/master/examples/expansivel_left.zip)
+ [Banner HTML5 expansível que empurra o conteúdo](https://spaceadx.github.io/doc/expansivel_push/) - [Download](https://raw.githubusercontent.com/spaceadx/doc/master/examples/expansivel_push.zip)

#### Propriedades
Muitas das propriedades declaradas abaixo podem ser invocadas como métodos caso isso facilite a interpretação

```
var config = {
  //LARGURA (EM PX, OBRIGATÓRIO)
  width: 300,

  //ALTURA (EM PX, OBRIGATÓRIO)
  height: 250,

  //ELEMENTO PARA O REDIRECIONAMENTO (OBRIGATÓRIO)
  //É USADO EM PRATICAMENTE TODOS OS BANNERS
  //PODE SER USADO O OBJETO Element, O ID COM '#id', '.class'. CASO SEJA SEM
  //NENHUM PREFIXO ELE IRÁ PROCURAR PELO ELEMENTO COM O ID CORRESPONDENTE
  clickElement:'banner',

  //CRIAÇÃO AUTOMÁTICA DO BOTÃO DE FECHAR - DEFAULT: false
  //closeButton: false,

  //TEXTO CUSTOMIZADO PARA O BOTÃO DE FECHAR - DEFAULT: 'Fechar X'
  //btnCloseImage: '',

  //IMAGEM CUSTOMIZADA PARA O BOTÃO DE FECHAR - DEFAULT: undefined
  //(DEVE SER PASSADO O CAMINHO RELATIVO A PASTA RAIZ DO BANNER)
  //btnCloseImage: '',

  //TEMPO PARA O AUTO FECHAMENTO - DEFAULT: undefined
  // É DEFINIDO EM MILISEGUNDOS
  //closeTimeout: 15000,

  //BOTÃO DE FECHAR DEFINIDO PELO USUÁRIO - DEFAULT: undefined
  // !! CASO A VARÍAVEL closeButton SEJA true ELA TERÁ PREFERÊNCIA !!
  //PODE SER USADO O OBJETO Element, O ID COM '#id', '.class'. CASO SEJA SEM
  //NENHUM PREFIXO ELE IRÁ PROCURAR PELO ELEMENTO COM O ID CORRESPONDENTE
  //closeElement: 'close',

  //O BANNER DEVE APARECER CENTRALIZADO - DEFAULT: false
  //centralize: false,

  //O BANNER DEVE APARECER CENTRALIZADO VERTICALMENTE - DEFAULT: false
  //centralizeY: false,

  //O BANNER DEVE APARECER CENTRALIZADO HORIZONTALMENTE - DEFAULT: false
  //centralizeX: false,

  //AJUSTA A POSIÇÃO PARA FIXO AO INVÉS DE ABSOLUTA - DEFAULT: false
  //fixed: false,

  //POSIÇÃO FIXA COM DISTÂNCIA DE X PX A PARTIR DO TOPO (EM PX) - DEFAULT: undefined
  //appendTop: 0,

  //POSIÇÃO FIXA COM DISTÂNCIA DE X PX A PARTIR DEBAIXO (EM PX) - DEFAULT: undefined
  //appendBottom: 0,

  //POSIÇÃO FIXA COM DISTÂNCIA DE X PX A PARTIR DA DIREITA (EM PX) - DEFAULT: undefined
  //appendRight: 0,

  //POSIÇÃO FIXA COM DISTÂNCIA DE X PX A PARTIR DA ESQUERDA (EM PX) - DEFAULT: undefined
  //appendLeft: 0
}

new Rocket(config)
```

#### Métodos
Todos os métodos disponíveis

close() :[this]
```
//Método para fechar o banner
var rocket = new Rocket(config)
rocket.close()
```
setCloseTimeout(timer:Integer) :[this]
```
// Seta em quanto tempo o banner será fechado
new Rocket(config).setCloseTimeout(1500)
```
expand(widthExpanded:Integer, heightExpanded:Integer, direction:String[1]) :[this]
```
// Método que deve ser invocado quando o banner precisar expandir
var rocket = new Rocket(config)
rocket.expand(300,600)
// Pode ser chamado para abrir outras direções, por exemplo para a esquerda
rocket.expand(300,600,'l')
```
expandFullScreen() :[this]
```
// Método que deve ser invocado quando o banner precisar expandir em tela cheia
var rocket = new Rocket(config)
rocket.expandFullScreen()
```
collapse() :[this]
```
// Método que deve ser invocado quando o banner precisar retrair
var rocket = new Rocket(config)
rocket.collapse()
```

tracking(event:String, inc:Integer) :[this]
```
// Método para computar um evento que deseja ser informado a Space
// e o incrementa conforme o segundo parametro
var rocket = new Rocket(config)
rocket.tracking('mouseOver')
// Exemplo com incremento customizado
rocket.tracking('purchaseTotal',120)
```

getClickUrl() :[url:string]
```
// Método para pegar a url que o usuário deve ser redirecionado
var rocket = new Rocket(config)
var url = rocket.getClickUrl()
window.open(url)
```