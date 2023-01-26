# custom-countdown
Proyecto que permite establecer una cuenta atrás.
-Mobile responsive
-Utilizaremos LOCALSTORAGE para grabarla y que continue funcionando aún cuando abandonemos la página.
# Recursos que utilizamos:
[Pixabay Stock Videos](https://pixabay.com/videos/) Para obtener un video de fondo
[Video Compression Tool](https://www.youcompress.com/) Para reducir aún más el tamaño del vídeo que nos hemos bajado

# Capturar evento
Al final del script tenemos el addEventListener:
countdownForm.addEventListener("submit", updateCountdown);

que llama a la función previamente definida:
function updateCountdown(e) {

el parámetro e hace referencia al evento, y desde dentro de la función le podemos acceder:
    e.preventDefault();

e.preventDefault() ---> El comportamiento por defecto de una form, es enviar los datos al servidor con el botón submit. Como en este caso no los enviamos a ningún sitio, automáticamente se recarga la página. Para evitarlo, utilizamos este método.

    countdownTitle = e.srcElement[0].value;
    countdownDate = e.srcElement[1].value;
Los campos de la form están en el evento en forma de array. Aquí recogemos el título de la cuenta atrás y su fecha de finalización.

# setInterval
Lo utilizo para actualizar la cuenta a cada segundo
   setInterval(actualizarCuentaAtras, tiempo)

# localStorage
A la hora de guardar con localStorage utilizaremos localStorage.setItem.
setItem recibe como parámetros dos strings: uno identifica o describe el valor que queremos guardar, el otro es el valor en si. Como en este caso se trata de un objeto, previo a enviarlo necesitamos utilizar JSON.stringify.
Cuando recuperemos el valor de localStorage, seguiremos el camino inverso: obtenemos un string que hay que convertir en un objeto. Para hacerlo, JSON.parse
