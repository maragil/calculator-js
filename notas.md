##JS

```js
const screen = document.querySelector(".screen");
const btns = document.querySelectorAll(".btn");

btns.forEach((button) => {
  button.addEventListener("click", () => {
    const pressBtn = button.textContent; //muestra la información en la screen

    if (button.id === "c") {
      screen.textContent = "0";//al pulsar C no se escriba C, sino q vuelva a ser 0
      return; //termina la F después de hacer el evento(addEventListner) y no sigue por los otros if
    }

    *if (button.id === "delete") {
      if (screen.textContent.length === 1 || screen.textContent === "Error!") {
        screen.textContent = "0";
      } else {
        screen.textContent = screen.textContent.slice(0, -1);//slice: borra la última tecla pulsada (desde la posición de la q se quiere partir 0, la posición de la tecla q se quiere borrar -1 --> arranca borrando desde atrás, y no necesitamos saber cuál es la última posición)
      }
      return; //para q solo haga este if y no ejecute lo q sigue
    }

   *if (button.id === "equal") {
      try { //intenta hacer el eval y sino pasa por el catch
        screen.textContent = eval(screen.textContent); //eval (F de JS): evalúa un conjunto de strings que tengan operaciones matemáticas en un solo string y no en formato nº.
      } catch {
        screen.textContent = "Error!";
      }
      return;
    }

   *if (screen.textContent === "0" || screen.textContent === "Error!") { //para q cuando salga Error!, al volver al pulsar los nºs no se agreguen detrás de la palabra Error!
      screen.textContent = pressBtn;
    } else {
      screen.textContent += pressBtn; //se van añadiendo los nº apretados
    }
  });
});
```

```js
 * if (screen.textContent === "0") //borra el 0 inicial cuando se pulsan otros números  {
      screen.textContent = pressBtn;

//cuando apretamos el btn de borrar, si la pantalla tiene un dígito o el texto error, se reinicie a 0
 * if (button.id === "delete") {
      if (screen.textContent.length === 1 (((((|| screen.textContent === "Error!")))))) {
        screen.textContent = "0";
      } else {
        screen.textContent = screen.textContent.slice(0, -1)
        }}
        //si hay un solo dígito en la pantalla, que el contador vuelva a 0, sino q borre el último dígito

```

##CSS

- Para q un elemento ocupe todo el ancho de la primera columna.

grid-column: 1 / 5

ó

grid-column: 1 / -1;

- Para centrar un contenido dentro del contenedor, da igual usar:

display: grid;
justify-content: center;

que

display: flex;
justify-content: center;
align-items: center;
