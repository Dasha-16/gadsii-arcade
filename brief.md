# Brief de Producto — UNLaMigo

**Equipo:** Arcade  
**Versión:** 1  
**Repositorio:** https://github.com/gadsii-unlam/gadsii-arcade  
**Fecha:** 24/08/2026

> **Registro de cambios:** primera versión del brief, elaborada en el marco del TP1. No existe una versión anterior con la cual comparar.

---

## Segmento elegido de la comunidad UNLaM y por qué ese

**Segmento:** Estudiantes de la UNLaM que se encuentren activos, cursando una carrera de grado y/o pregrado de cualquier departamento, en cualquier instancia de la carrera, y que asistan presencialmente a la universidad de forma periódica.

**Por qué ese segmento:** el carpooling solo tiene sentido si existen patrones de traslado repetidos que puedan matchearse entre conductores y pasajeros. Por eso se acota a estudiantes activos y cursando (se descartan docentes, personal y aspirantes, que no comparten esa necesidad de traslado académico) y que asistan presencialmente de forma periódica (se descartan quienes cursan de forma virtual o asisten de manera esporádica, como para rendir un final, ya que no generan un trayecto recurrente que otro usuario pueda encontrar o planificar con anticipación).

---

## Producto: nombre, problema, a quién le resuelve

**Nombre:** UNLaMigo

**Problema y a quién le resuelve:**

Una porción significativa de la comunidad universitaria se traslada diariamente al campus en vehículo propio, en la gran mayoría de los casos con un único ocupante. En paralelo, otra porción se traslada en transporte público realizando combinaciones largas.

La propuesta es construir una herramienta que conecte a ambos grupos, de modo que quienes asisten en vehículo propio no modifiquen sus recorridos habituales y puedan ofrecer las plazas disponibles, mientras que quienes se postulan como pasajeros encuentren opciones cercanas a su punto geográfico de partida.

Además de estos dos grupos, otro beneficiario es la propia institución universitaria, ya que disminuye la necesidad de gestionar grandes volúmenes de vehículos en las playas de estacionamiento, sobre todo en los horarios pico.

---

## Funcionalidades core

1. **Publicación de trayectos (conductor):** el conductor carga su trayecto indicando día (puntual o repetido durante la semana), horario y cantidad de cupos/asientos disponibles.
2. **Búsqueda de trayectos cercanos (pasajero):** el pasajero visualiza los trayectos publicados dentro de un radio aproximado de 5 a 10 cuadras de su zona.
3. **Solicitud para unirse a un trayecto (pasajero):** el pasajero envía una solicitud al conductor para formar parte de un trayecto publicado.
4. **Confirmación de la solicitud:** mecanismo por el cual se define si el pasajero queda efectivamente incorporado al trayecto. *Por completar: todavía no está definido si la confirmación la realiza el conductor manualmente, si se asigna automáticamente, u otro criterio.*

---

## Integraciones previstas

- **Mapa con geolocalización en tiempo real:** integración con una API de mapas (ej. Google Maps) para mostrar en tiempo real la ubicación del conductor durante el trayecto, permitiendo al pasajero seguir el viaje.
- **Validación de condición de alumno regular:** el usuario carga su certificado de alumno regular (foto o PDF) al registrarse; el rol Validador revisa y aprueba manualmente la documentación antes de habilitar la cuenta.
- **Validación del vehículo del conductor:** lectura del código QR presente en la cédula verde/azul para autocompletar los datos del vehículo, con revisión y confirmación manual por parte del Validador.

---

## Grupos de usuarios y usuario primario elegido

**Grupos identificados:**
- Conductor
- Pasajero
- Validador

**Usuario primario elegido:** Conductor y Pasajero

**Justificación:** UNLaMigo es un producto de dos lados (conductor y pasajero), donde ambos roles son interdependientes y, en definitiva, la razón de ser del sistema. Aunque, el conductor es el lado más escaso: dispone del recurso (el vehículo y el viaje ya planeado) pero hay que convencerlo de compartirlo, mientras que la demanda de pasajeros tiende a aparecer más fácilmente una vez que existe oferta disponible en una zona y horario.

> ⚠️ La selección del usuario primario es una decisión de diseño y, por ahora, es hipotética: todavía no se validó con usuarios reales. El TP2 confirmará si fue acertada.

---

## Lista de supuestos

1. **Asumimos que los estudiantes tienen acceso a celulares para utilizar la aplicación.**
   *Evidencia:* encuesta breve al segmento relevado, preguntando si posee smartphone propio y sistema operativo.

2. **Asumimos que dispondrán de internet antes, durante y después de concluir el viaje en UNLaMigo.**
   *Evidencia:* encuesta al segmento sobre disponibilidad de datos móviles o Wi-Fi durante el trayecto habitual a la universidad.

3. **Asumimos que los pasajeros potenciales utilizan hoy el transporte público para llegar a la universidad.**
   *Evidencia:* relevamiento (TP2) preguntando el medio de transporte habitual utilizado para llegar al campus.

4. **Asumimos que les resulta incómoda la frecuencia y/o el espacio disponible en ese transporte público.**
   *Evidencia:* entrevistas del TP2 indagando el nivel de satisfacción con el transporte público actual y los motivos de insatisfacción.

5. **Asumimos que los estudiantes están dispuestos a viajar con compañeros que no conocen previamente, siempre que pertenezcan a la comunidad UNLaM.**
   *Evidencia:* pregunta directa en el relevamiento sobre disposición a compartir viaje con otro estudiante de la UNLaM sin conocerlo previamente.

6. **Asumimos que una ganancia económica por combustible es un incentivo suficiente para que el conductor quiera realizar viajes compartidos.**
   *Evidencia:* entrevistas a conductores potenciales (U1/U2/U3 que cumplan ese rol) consultando si aceptarían compartir su viaje a cambio de una compensación por combustible.

7. **Asumimos que existe una coincidencia suficiente de recorridos y horarios entre conductores y pasajeros dentro del mismo segmento como para poder armar viajes compartidos.**
   *Evidencia:* relevamiento de puntos de partida y horarios de ingreso/egreso a la facultad de una muestra del segmento, para verificar superposición geográfica y horaria.

**Supuesto crítico:** el número 7 (coincidencia de recorridos y horarios). Si no existe suficiente superposición geográfica y horaria entre conductores y pasajeros, no hay viajes que armar y el producto pierde su razón de ser, independientemente de que el resto de los supuestos se cumplan.
