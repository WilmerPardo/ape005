# ape005

## Reporte de Pruebas de API (Rick and Morty & JSONPlaceholder)'

Este proyecto permite realizar pruebas de consumo de APIs mediante una interfaz simple creada con HTML, CSS y JavaScript. Se incluyen tres pruebas principales: una petición GET a la API de Rick and Morty, una petición POST a JSONPlaceholder, y una petición POST fallida hacia Rick and Morty para observar el manejo de errores y CORS.

A continuación se detallan los resultados obtenidos al ejecutar `index.html` y probar los botones de acción.

| Método | URL | Código de estado | Tiempo respuesta | Observaciones CORS |
| :--- | :--- | :--- | :--- | :--- |
| **GET** | `https://rickandmortyapi.com/api/character/{id}` | `200 OK` | 939 ms | La API incluye `Access-Control-Allow-Origin: *`, permitiendo que el navegador descargue el JSON y renderice la imagen sin bloqueos. |
| **POST** | `https://jsonplaceholder.typicode.com/posts` | `201 Created` | 832.10 ms | La petición "Preflight" (OPTIONS) fue exitosa. El servidor acepta datos externos y devuelve el ID del nuevo objeto creado. |
| **POST** | `https://rickandmortyapi.com/api/character` | `404` o `500` | 1124.70ms | **Error esperado.** La API es de solo lectura (Read-Only). Aunque el CORS permite la conexión, el servidor rechaza la creación de recursos. |

🧰 Requisitos Previos

Antes de ejecutar este proyecto, asegúrate de contar con lo siguiente:

✔ Navegador web moderno (obligatorio)

Funciona en cualquier navegador actualizado:

Google Chrome

Mozilla Firefox

Microsoft Edge

Opera

No se requiere instalar servidores, frameworks, Node.js ni dependencias externas.

✔ Archivos del proyecto

Debes contar con:

index.html

styles.css

(Opcional) imágenes si las usas en tu diseño

🚀 Cómo ejecutar el programa
1. Descarga o clona el proyecto

Si usas GitHub:

git clone https://github.com/tu-repo/ape005.git


O copia los archivos manualmente en una carpeta local, por ejemplo:

/proyecto-apis/
    index.html
    styles.css

2. Abre el archivo principal

Haz doble clic en:

index.html


El navegador abrirá inmediatamente la interfaz.

No necesitas XAMPP, WAMP, Live Server ni nada adicional, ya que las APIs permiten solicitudes directas desde el navegador.

🕹 Cómo usar la interfaz

En pantalla verás tres botones:

🔵 1. GET Rick (Tarjeta Visual)

Obtiene un personaje aleatorio de la API de Rick and Morty.

Método: GET

Muestra una tarjeta con:

Imagen

Nombre

Estado (Alive/Dead)

Especie

Origen

🟢 2. POST JSONPlaceholder

Envía una estructura JSON simulando la creación de un nuevo recurso.

Método: POST

Envía:

{ "title": "Prueba", "body": "Datos", "userId": 1 }


El servidor responde con un nuevo id.

🔴 3. POST Rick (Forzar Error)

Intenta enviar un POST a la API de Rick and Morty (que es solo lectura).

Devuelve 404 o 500

Permite probar manejo de errores

Útil para observar bloqueos y respuestas CORS

📋 Resultados mostrados por el programa

Cada petición muestra:

✔ Tiempo de respuesta
✔ Código de estado HTTP
✔ Datos JSON o tarjeta visual
✔ Mensaje de error si aplica
✔ Logs detallados en consola:

Abre la consola con:

F12 en Windows

Cmd + Option + I en Mac

Los logs incluyen:

URL usada

Método HTTP

Tiempo total

Estado recibido

🛠 CORS — ¿Necesito activar algo?

No.
Ambas APIs permiten solicitudes desde el navegador:

Rick and Morty API → Access-Control-Allow-Origin: *

JSONPlaceholder → Permite GET y POST sin restricciones

Por lo tanto:

No necesitas backend, proxy, ni servidor local.

📦 Estructura sugerida del proyecto
proyecto-apis/
│── index.html
│── styles.css
└── README.md
