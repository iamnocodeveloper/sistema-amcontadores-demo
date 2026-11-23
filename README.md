# AM Contadores y Abogados — demo del sistema del despacho

Demo navegable (una sola página, sin backend) del **sistema de gestión del despacho**
para **AM Contadores y Abogados**, firma de contadores y abogados en Costa Rica.
WhatsApp del despacho: **+506 7207 2084**.

El objetivo de este demo es **explicar en palabras llanas qué es el sistema**, con un
**recorrido guiado de 7 pasos** que resalta cada parte y la describe sin tecnicismos.

## Qué muestra

- **Entrada**: «Entrar al sistema» y «Ver el recorrido guiado», con una frase que
  explica qué es: «El tablero donde el despacho ve, en una sola pantalla, qué le toca
  a cada cliente y cuándo».
- **Panel del día**: vencimientos que cumplir (hoy y esta semana), atenciones y citas
  de hoy, tareas sin cerrar, cobros del mes y avisos pendientes de enviar.
- **Vencimientos** (la pieza central): calendario del mes con cada obligación ubicada
  por fecha y **coloreada por tipo** (impuesto de ventas · IVA, seguridad social · CCSS,
  declaración anual de renta, trámite legal); lista ordenada por proximidad con cliente,
  obligación, fecha, estado (al día / presentado / por vencer / vencido) y el **aviso
  automático** programado (**7 y 2 días antes**), más la maqueta del mensaje de WhatsApp
  que recibiría el cliente. Las siglas van siempre explicadas al lado.
- **Clientes**: tabla buscable por nombre o cédula con la ficha de cada uno: datos,
  obligaciones que cumple, sus vencimientos, documentos entregados y quién lo atiende
  (contador o abogado).
- **Atenciones y citas**: agenda de la semana por profesional (contadora / abogado),
  con tipo de atención (asesoría contable, revisión de impuestos, consulta legal,
  reunión) y estado (solicitada / agendada / atendida), y la **conversión de una
  consulta nueva en cita** con un clic.
- **Honorarios**: facturación por cliente y concepto, con estado pagado / pendiente
  y el total del mes.
- **Informes**: gráficos propios en SVG/CSS (sin librerías): vencimientos cumplidos
  vs. vencidos, atenciones por mes, clientes por servicio y cobrado vs. pendiente.
- **Web pública** (dentro del demo): presentación del despacho, sus servicios en
  palabras claras y un formulario **«Solicitar asesoría»** que arma el mensaje de
  WhatsApp al **+506 7207 2084** con los datos del negocio y la necesidad.

## Recorrido guiado (7 pasos)

1. Esto es lo que ve al entrar: lo que le toca hoy.
2. Los vencimientos del mes, cada cliente en su fecha.
3. El aviso automático antes de que venza, por WhatsApp.
4. La ficha del cliente con todo lo suyo.
5. Las atenciones y citas del despacho.
6. Los honorarios y quién debe qué.
7. Los informes y la página pública.

Con contador «Paso N de 7», botones Atrás / Siguiente / Salir, teclado (← → Esc) y
**modo automático**.

## Cómo se sirve

Sitio estático. Un `index.html` con CSS y JS en línea (sin dependencias) y un
`Dockerfile` con nginx para servirlo.

```
docker build -t amcontadores-demo .
docker run -p 8080:80 amcontadores-demo
```

## Aviso

Demo de referencia hecho por **Nocodeveloper**. **Los datos son de ejemplo** (clientes,
montos y fechas ficticios). No envía mensajes ni consulta sistemas reales.
