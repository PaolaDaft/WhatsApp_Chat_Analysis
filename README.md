# 📱 Análisis de un chat de WhatsApp 🙊  

En este proyecto podrás encontraras el análisis que realice de una conversación con uno de mis amigos. El notebook incluido en el repo abarca la limpieza y transformación de la data, el análisis exploratorio y la visualización de algunas estadísticas como:

<br>
    🤔 Emojis más usados en la conversación.<br>
    📊 Días más activos del chat.<br>
    📊 Horas en las que está más activo el chat.<br>
    ☁️ Word Cloud de palabras más usadas  en el chat.
<br></br>

## Primeros pasos
Para hacer tu propio análisis de cualquiera de tus chat haz los siguientes pasos:
<details>
  <summary>📱 Descarga e importa el archivo .txt de tus chats </summary>
    <ol>
    <li> Ve a la chat que quieras analizar, ya sea de un contacto o de un grupo<img src="https://private-user-images.githubusercontent.com/68626833/311441917-3613f578-4627-4b4c-950e-fb9d9b7b7591.jpeg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDk5OTMyOTYsIm5iZiI6MTcwOTk5Mjk5NiwicGF0aCI6Ii82ODYyNjgzMy8zMTE0NDE5MTctMzYxM2Y1NzgtNDYyNy00YjRjLTk1MGUtZmI5ZDliN2I3NTkxLmpwZWc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMzA5JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDMwOVQxNDAzMTZaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1iZWVlZjUxZTVhM2QyN2Y2MmJjYzAzNzk3NGNhYTNhYjQzOTRkYWI2NzcxMzI3YjFjYmEwMTc5NzY5NGUzNzdkJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.vKVcjhHRdLWeI6DBNMu-yz8pdUpKanp9TB8YS0DBkhA" width="150" alt="Competencias" />
    <li>Selecciona la opción <em>sin archivos</em><img src="https://private-user-images.githubusercontent.com/68626833/311441916-f6c4e9cb-c674-45ae-92a1-d71e4896005b.jpeg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDk5OTMyOTYsIm5iZiI6MTcwOTk5Mjk5NiwicGF0aCI6Ii82ODYyNjgzMy8zMTE0NDE5MTYtZjZjNGU5Y2ItYzY3NC00NWFlLTkyYTEtZDcxZTQ4OTYwMDViLmpwZWc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMzA5JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDMwOVQxNDAzMTZaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT05NWMzZmZjZjQxZTRkMDdmMzZhNTkyMWQyZDNjNDU0NzMzYTEzYWY3MzJmNWJiYzViM2Y1ZGJhZjhiNTJiZDdlJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.DxX3lN8BWehGxtO1J96t2LZeo--Sf4ReS0iWwjTdhnE" width="150" alt="Competencias" />
    <li>Por ultimo selecciona un contacto o a ti mismo para enviar el arvicho y asi poder descargarlo por WhatsApp Web   <img src="https://private-user-images.githubusercontent.com/68626833/311441914-ed16cb88-4460-4e47-a1e8-afe021dba12e.jpeg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDk5OTMyOTYsIm5iZiI6MTcwOTk5Mjk5NiwicGF0aCI6Ii82ODYyNjgzMy8zMTE0NDE5MTQtZWQxNmNiODgtNDQ2MC00ZTQ3LWExZTgtYWZlMDIxZGJhMTJlLmpwZWc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMzA5JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDMwOVQxNDAzMTZaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT01NTA0MzhlNzQxZDIyNDEzNTk4MmEyNGVlZTA0MGYyZTQ2MzljYjY1ZTBjNDM0MTkyYjU2ZWEyNTIxMWFiZjBiJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.YMQxWkQypuSjPVJ7wu-HrzQdY0LayCuywl312D3d66s" width="150" alt="Competencias" />


  </ol>
</details>

<details>
  <summary>🗂️ Te dejo la documentación de las librerías usadas en el proyecto. </summary>
  <lu>
    <li> <a href="https://docs.python.org/es/3/library/re.html#regular-expression-objects)
  [This link](http://example.net/">Re, para expresiones regulares</a>
    <li> <a href="https://carpedm20.github.io/emoji/docs/">Emoji</a> 
  </lu>
</details>