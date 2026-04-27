# Trabajo Practico: Calculadora de Descuentos Encadenados

**Materia:** Programacion III  
**Grupo:** 13

## Ramas del proyecto

- 🔹 **rama_fede** → [usuario](https://github.com/FedericoMarcenac)
- 🔹 **rama_ulises** → [usuario](https://github.com/ulisesfossati)
- 🔹 **rama_nacho** → [usuario](http://github.com/nachoalvarado78)
- 🔹 **rama_gonzalo** → [usuario](https://github.com/Gon-arg)
- 🔹 **rama_celina** → [usuario](https://github.com/CeliV)

## De que trata el proyecto

Hicimos una app que sirve para calcular descuentos. Pero no un solo descuento, sino "descuentos encadenados", o sea, cuando le aplicas un descuento a un precio, y al resultado que te da le bajas otro porcentaje mas, y asi.

Le dimos una estetica parecida a una calculadora analogica, con un visor arriba y las teclas abajo.

## Tecnologias utilizadas

- HTML5
- CSS3 (Flexbox)
- JavaScript (DOM, eventos y validaciones)
- Git & GitHub

## Uso de Git y GitHub

- Se trabajo con ramas individuales por integrante.
- Cada miembro del grupo realizo al menos un commit.
- Se utilizaron Pull Requests para integrar los cambios al proyecto principal.

## Que se puede hacer en la pagina

- Podes poner el precio inicial del producto en el primer campito.
- Con el boton Agregar descuento podes ir agregando varios campos para poner mas porcentajes de descuento.
- Si pones cosas raras, como un numero negativo, una letra o lo dejas vacio, la pagina te avisa del error en rojo.
- Cuando le das al boton Calcular, te saca la cuenta final y te muestra en un texto paso por paso cuanto fuiste ahorrando con cada porcentaje.
- Arriba en la pantalla ves el precio total y el ahorro neto.
- El boton Limpiar borra todo de golpe para volver a probar con otro calculo.

## Archivos y carpetas del trabajo

- `index.html`: La maquetacion en HTML para armar todo el codigo.
- `css/index.css`: Usamos CSS aca para darle todo el diseño usando Flexbox, asi centramos los elementos y le damos un aspecto moderno. Las demas carpetas adentro son componentes que fuimos usando.
- `js/script.js`: Toda la logica en JavaScript para que los botones reaccionen y hagan las sumas y restas de porcentaje.
- `assets/img/fondo.png`: Guardamos la imagen de fondo de la calculadora.

## Estructura del proyecto

```text
proyecto/
│
├── index.html
├── README.md
│
├── /assets
│   ├── /favicon
│   └── /img
│       └── fondo.png
│
├── /css
│   ├── index.css
│   └── /components
│       ├── carta.css
│       ├── boton.css
│       └── resultados.css
│
└── /js
    └── script.js
```

## Funciones que usamos

Ademas de las que vamos a explicar abajo, en nuestro codigo tambien usamos estas funciones para que ande todo:

- `agregarDescuento()`: Crea un campo de input extra visualmente en el HTML cada vez que le das click a Agregar descuento.
- `renumerar()`: Se asegura de que los textos "Descuento 1", "Descuento 2" se mantengan en orden por si el usuario decide borrar uno del medio.
- `calcular()`: Es la funcion matematica mas grande. Agarra los datos, cuenta los descuentos uno encima del otro y muestra todo en pantalla.
- `limpiar()`: Deja todos los campos vacios y reinicia la calculadora.

## Explicacion de estilos CSS

**`:hover`**  
Se aplica cuando el usuario pasa el mouse por encima de un boton, cambiando su color para dar feedback visual.

**`:focus`**  
Se aplica cuando el usuario hace click en un input, cambiando el borde a azul para indicar que esta activo.

## Explicacion de codigo extra

Como nos pidieron explicar que hace alguna funcion, elegimos estas dos que usamos en el proyecto:

### renumerar()

**Descripcion:**  
Renumera los labels de los campos de descuento cuando el usuario elimina uno del medio.

```javascript
function renumerar() {
  const cartas = contenedor.querySelectorAll(".carta");
  cartas.forEach((c, i) => {
    const label = c.querySelector("label");
    if (label) label.textContent = `Descuento ${i + 1} %`;
  });
  contador = cartas.length;
}
```

**Parametros:**  
No recibe parametros.

**Explicacion:**  
Selecciona todas las cartas del contenedor con `querySelectorAll`, las recorre con `forEach` y actualiza el texto de cada `label` para que queden numeradas en orden. Finalmente actualiza el contador global con la cantidad actual de cartas.

---

### fmt(n)

**Descripcion:**  
Formatea un numero para mostrarlo con el formato de moneda argentina.

```javascript
function fmt(n) {
  return n.toLocaleString("es-AR", { minimumFractionDigits: 2, maximumFractionDigits: 2 });
}
```

**Parametros:**  
- `n` (`number`): el numero que se quiere formatear.

**Valor de retorno:**  
Devuelve un `string` con el numero formateado.

**Que hace linea por linea:**

- **Linea 1:** Creamos una funcion que le pusimos nombre `fmt`, de formato, que espera recibir algo que llamamos `n`. En nuestro caso, ese valor representa un monto de dinero.
- **Linea 2:** Usamos la palabra clave `return` para devolver el resultado modificado. Lo que hace `.toLocaleString("es-AR")` es forzar a que ese numero se escriba de la forma en que lo escribimos en Argentina. Lo que esta entre llaves, `{ minimumFractionDigits: 2, maximumFractionDigits: 2 }`, sirve para dejar exactamente 2 decimales, asi los centavos siempre se muestran correctamente.
- **Linea 3:** Se cierra la funcion.

## Como se usa

### Opcion 1: Abrir el proyecto manualmente

Se descarga todo el proyecto y se abre el archivo `index.html` con cualquier navegador web.

No hace falta instalar nada extra, porque es una pagina hecha con HTML, CSS y JavaScript puro.

### Opcion 2: Clonar el repositorio con Git

Tambien se puede descargar el proyecto usando Git desde la terminal.

Para eso, se copia y se pega este comando en la terminal:

```bash
git clone https://github.com/FedericoMarcenac/ParcialGrupo13Programacionlll
```

Despues de clonar el repositorio, se entra a la carpeta del proyecto con este comando:

```bash
cd ParcialGrupo13Programacionlll
```

Una vez adentro de la carpeta, se abre el archivo `index.html` con cualquier navegador web.

