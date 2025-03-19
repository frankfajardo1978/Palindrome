# PALINDROME
Creación de un Palindromo

## PASO 1 Creacion del entorno HTML
![image](https://github.com/user-attachments/assets/fdcf18d0-bb7f-4ddc-9656-2f59e6c5c33e)



### Aqui incluyo estas lineas:

```<!DOCTYPE html>```  -- Lo defino como HTML5

```<html lang="en">``` -- Selecciono como idioma base de mi pagina "ingles"

## PASO 2 Creacion del cuerpo de la pagina y entorno
![image](https://github.com/user-attachments/assets/76155527-5395-43fe-93c1-c34088f5f414)


### Dentro de mi bloque <head> incluyo lo siguiente, tarbajado bajo CSS:

```<meta charset="UTF-8">```  -- el formato UTF-8 lo coloco para que me permita todo tipo de caracteres especiales

```<meta name="viewport" content="width=device-width, initial-scale=1.0">``` aqui adapto la pagina para que se vea en formato de moviles

```<title>Palindrome Checker</title>``` aqui defino el título de la pestaña del navegador

### Creacion de mi body

```font-family: Arial, sans-serif;``` -- establezco el tipo de letras que quiero manejar

```text-align: center;``` - el alineamiento del texto va al centro

```margin: 50px;``` 

```background-color: #1e88e5;``` establezco el color basado en los codigos de paleta, en mi caso escoji el azul ya que me gusta mucho para mi entorno

### Creacion del container

```background: white;``` -- aqui selecciono el fondo de mi objeto en color blanco

```padding: 20px;``` 

```border-radius: 20px;``` aqui le doy una curvatura a los bordes

```box-shadow: 10px 10px 10px black;``` quiero que mi bloque resalte por tanto le coloco sombras negras y le coloco 10 pixelespara que resalten mas

```display: inline-block;```

### Creacion de text-input y check-btn // aqui defino todos los parametros visuales (margen, padding y se aumenta el tamaño del texto para una mejor apariencia)

```margin: 10px;```

```padding: 10px;```

```font-size: 16px;```

## PASO 3 Creacion del objeto de Palindromo
![image](https://github.com/user-attachments/assets/f3214ff9-4ab5-4800-b6c0-6b835bcbcb41)


### aqui se encierra dentro de otro body los siguientes codigos que van a dar forma al objeto del Palindrome checker

```<h1>Palindrome Checker</h1>``` -- titulo de la pagina 

```<input type="text" id="text-input" placeholder="Enter text">``` -- selecciono el metodo input y que solicite ingresar el texto string

```<button id="check-btn">Check</button>``` -- boton que va a activar el reconocimiento el string

```<p id="result"></p>``` -- parrafo que va a mostrar el resultado


## PASO 4 Creacion de una funcion que limpia el texto con javascript
![image](https://github.com/user-attachments/assets/1c64f570-f8b5-4308-88a1-a58b8564ff1e) 

esta funcion limpia el texto ingresado eliminando caracteres especiales y trasnformandolos en minusculas






    



       
 
</head>
<body>
    <div id="container">
        <h1>Palindrome Checker</h1>
        <input type="text" id="text-input" placeholder="Enter text">
        <button id="check-btn">Check</button>
        <p id="result"></p>
    </div>

    <script>
        function cleanText(text) {
            return text.replace(/[^a-zA-Z0-9]/g, "").toLowerCase();
        }

        function palindrome(str) {
            const cleaned = cleanText(str);
            const reversed = cleaned.split("").reverse().join("");
            return cleaned === reversed;
        }

        document.getElementById("check-btn").addEventListener("click", function() {
            const inputField = document.getElementById("text-input");
            const resultField = document.getElementById("result");
            let text = inputField.value;

            if (!text) {
                alert("Please input a value");
                return;
            }

            if (palindrome(text)) {
                resultField.textContent = `${text} is a palindrome.`;
            } else {
                resultField.textContent = `${text} is not a palindrome.`;
            }
        });
    </script>
</body>
</html>
