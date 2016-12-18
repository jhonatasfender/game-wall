# game-wall
This game and that I was having problems to understand the logic of preventing the player could not utrapassar an object, decide to put here to be able to help the guys who have the same doubt that I

## 1. My first logic

* In this first part I put the logic to work only with a brick and going to the left, and the data is fixed.
```javascript
  if(keyCode == 37 && (square.x < 10 || square.x > 20 || square.y < 10 || square.y > 20)) {
    square.x = square.x - 1;
    keyCode = null;
  }
```
* Now the next step is to prevent the hero or character from crossing the two obstacles placed on the screen, we will put it statically soon we will try to do it dynamically.
```javascript
  var stroke = [
    {x: 10,y: 10,w: 10,h: 10},
    {x: 10,y: 50,w: 10,h: 10}
  ];
```
<h6>Good now and create a mapping the bricks and then we will create a brick wall</h6>

* Remembering that I have put for now only to the left.
<h6>Remembering that I have put for now only to the left. And another thing I did not yet set up the logic to find the area of the character, I used with squares so that it could not complicate. It's something my first logic I'm learning.</h6>
  1. Step.
  
    ```javascript
    function c(i){
      return square.x < stroke[i].x || square.x > stroke[i].x + stroke[i].w || 
             square.y < stroke[i].y || square.y > stroke[i].y + stroke[i].h;
     }
    ```
    <h6>
    This condition is responsible for finding the area of the square according to the map generated above. This is the basic logic to find the area of a brick or a brick wall, with this we can find, I basically did in JavaScript using Canvas and to find a point to the other I have to add the x axis and the x axis more The dimension of x that is the width the same thing goes for the y axis adding the dimension y that is the height
    </h6>

    
* Then I created another function that runs through the bricks I created and checks if the other square is near it.
```javascript
function d(){
  var b;
  for (var i = 0; i < stroke.length; i++) {
    if(c(i) === false){
      return false;
    }
  }
  return true;
}
```
* Depois chamei essa função colocando dentro da variável o valor booleano que a função me retornou, depois disso eu coloco na verificação se é verdadeiro caso seja eu deixo ir para esquerda, caso não seja eu impeço de ir para esquerda.  
```javascript
b = d();
if(keyCode == 37 && d()) {
  square.x = square.x - 1;
  keyCode = null;
  b = true;
}
```

<h3 style="color: red">Warning: do not care about the names of the functions what I want to pass here is only the logici that I was with difficulties and I want to share with you readers.</h3>


