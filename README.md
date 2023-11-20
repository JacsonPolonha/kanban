# kanban

Projeto javascript onde é possível arraastar os cards de uma coluna para outra.

Todos os cards tem a classe "item" e possuem a propriedade "draggable" como "true". Isso significa que a pagina entenderá que estes elementos poderão ser arrastados através do mouse.

No script pegamos os elementos das divs da coluna ("column) com o comando document.querySelectorAll.

Em seguida há dois eventos: "dragstart" e "dragend". O primeiro observa se algum item foi arrastado e adiciona a classe "dragging". O segundo verifica se o item foi solto e remove a classe "dragging".

Essa classe indicará visivelmente que ele está sendo movido e também irá identificar qual item deverá ter sua posição alterada.

Após isso vem um "foreach" para percorrer todas as colunas do quadro. No "foreach" um evento "dragover" verificará se o card que está sendo arrastado está se sobrepondo a uma coluna.

Isso é possível devido a classe "dragging" adicionada ao card quando o movimento de arrasto do mouse se iniciou. A partir da classe e do evento, é possível capturar a posição do card no quadro utilizando a função "getNewPosition".

A função vai capturar todos os outros cards que não possuem a classe "dragging". Após isso será obtido a posição de cada um no quadro e será feita uma validação, para saber se a posição do cartã arrastado émaior que a dos demais.

Em caso afirmativo, o card arrastado vai ocupar o espaço do card ao qual ele está se sobrepondo, movendo os demais para baixo. A outra possibilidade é que o card arrastado ocupe a primeira posção da lista na coluna.