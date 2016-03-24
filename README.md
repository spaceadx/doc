# SPACE ADSERVER
## rocket.js
### Como usar?
Inclua o rocket.js no seu projeto
```demo
<script src="https://azure-2mobile.netdna-ssl.com/static/rocket.js"></script>
```
#### Métodos
Todos os métodos disponíveis

setClickTag(tag:String) :[this]
```
// Seta a click tag
new Rocket().setClickTag("%%CLICKTAG%%")
```
setClickElement(elementID:String) :[this]
```
// Seta qual a área clicavel do banner *tem que ser o id do element
new Rocket().setClickElement("clickAreaDiv")
```
setCloseElement(closeButtonID:String) :[this]
```
// Seta qual é o elemento que fecha o banner
new Rocket().setCloseElement("btnFechar")
```
setCloseTimeout(timer:Integer) :[this]
```
// Seta em quanto tempo o banner será fechado
new Rocket().setCloseTimeout(15)
```
setExpandable(collapsedID:String, expandedID: String) :[this]
```
// Seta quais os elementos minimizado e expandido e adiciona o mouseover automaticamente para quando passar o mouse sobre o minimizado expandir.
new Rocket().setExpandable("divCollapsed","divExpanded")
```
.setExpandElement("btnParaExpandir","divCollapsed",function(){
          alert('expandiu');
        });
setExpandElement(expandButtonID:String, elementToShowID:String, callback:Function(void)) :[this]
```
// Seta o botão que deve expandir o banner e a qual div deve ser exibida, executa o callback assim que o botão for clicado.
new Rocket().setExpandElement("btnParaExpandir","divExpanded",function(){
    alert('expandiu');
});
```
setCollapseElement(collapseButtonID:String, elementToShowID:String, callback:Function(void)) :[this]
```
// Seta o botão que deve minimizar o banner e a qual div deve ser exibida, executa o callback assim que o botão for clicado.
new Rocket().setExpandElement("btnParaMinimizar","divCollapsed",function(){
    alert('minimizou');
});
```

#### Exemplo
```demo
<script src="https://azure-2mobile.netdna-ssl.com/static/rocket.js"></script>
<script type="text/javascript" id="gwd-init-code">
    (function () {
        new ROCKET().setClickTag("%%CLICKTAG%%").setClickElement("page1");
    })();
</script>
```
