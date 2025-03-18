# Palindrome
Creación de un Palindromo

## PASO 1 CREACION DEL ENTORNO HTML
![image](https://github.com/user-attachments/assets/d306dc3a-dae1-49a4-970a-8356306e4a4e)


### Aqui incluyo estas lineas:

```<!DOCTYPE html>```  -- Lo defino como HTML5

```<html lang="en">``` -- Selecciono como idioma base de mi pagina "ingles"

## PASO 2 Aqui creo el cuerpo de mi pagina y voy moldeando mi entorno
![image](https://github.com/user-attachments/assets/695fb6ac-36a7-4628-9f88-f3f548ee0a30)

### Dentro de mi bloque <head> icluyo lo siguiente, tarbajado bajo CSS:
```<meta charset="UTF-8">```  -- el formato UTF-8 lo coloco para que me permita todo tipo de caracteres especiales

```<meta name="viewport" content="width=device-width, initial-scale=1.0">``` aqui adapto la paginapara que se vea en formato de moviles

```<title>Palindrome Checker</title>``` aqui defino el título de la pestaña del navegador

### Creacion de <body>

```font-family: Arial, sans-serif;``` -- establezco el tipo de letras que quiero manejar

```text-align: center;``` - el alineamiento del texto va al centro

```margin: 50px;``` 

```background-color: #1e88e5;``` establezco el color basado en los codigos de paleta, en mi caso escoji el azul ya que me gusta mucho para mi entorno



       
 
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
