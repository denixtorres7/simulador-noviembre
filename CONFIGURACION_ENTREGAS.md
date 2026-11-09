# Versión 3.1 — Guía docente

## Modo progresivo

Abre `index.html?modulo=nomina` para mostrar únicamente Nómina, `index.html?modulo=costos` para Costos operativos, `index.html?modulo=productos` para Costo de diseño, `index.html?modulo=audiovisual`, `index.html?modulo=proyecto`, `index.html?modulo=pi` o `index.html?modulo=contratos`. El enlace `index.html` muestra la aplicación completa, con navegación. `index.html?modulo=informeFinal` abre el informe final.

La navegación queda oculta en modo individual, pero **no constituye control de acceso**. No se duplican calculadoras.

## Vista previa, archivos y datos

Cada módulo dispone de controles centrales para visualizar el PDF, descargarlo y descargar un JSON de la actividad. El informe PDF usa el generador compartido de la aplicación y su nombre sigue el esquema Agencia_Apellidos_Modulo.pdf. La fecha aparece en el pie. Los JSON individuales de la versión 3.1 usan el esquema `svc.activity.v1`; la importación desde Inicio acepta estos archivos y actualiza solo las claves incluidas. Se recomienda servir el simulador desde un origen web HTTPS, no desde `file://`, para que el almacenamiento compartido entre módulos sea fiable.

El informe final reúne los registros guardados y la información visible de los módulos. Debe revisarse cuidadosamente: **todavía no está validada la fidelidad editorial de todos los informes respecto del PDF de Costos operativos**. Los cálculos originales no se han modificado.

## Envíos a base de datos

El botón **Enviar actividad** se incorpora a la interfaz, pero **permanece sin conexión operativa** hasta configurar un servicio de recepción docente seguro. No se simula una confirmación ni se descuentan intentos localmente. El servicio deberá validar identidad, comprobar el JSON y el PDF, guardar ambos de manera atómica, conservar versiones y aplicar en el servidor el límite de **dos envíos confirmados por actividad** y **dos para el informe final**.

El código de interfaz busca la dirección del servicio en la clave `svc-teacher-endpoint-v1` de `localStorage`. No se proporciona un servidor ni se recomienda publicar un endpoint sin autenticación. Para uso con estudiantes se requiere configuración y pruebas de recepción reales, control de acceso y privacidad, y prueba de límites de entrega.

## Estado de pruebas

Se comprueba sintaxis de JavaScript y estructura del ZIP. Las pruebas interactivas de navegación, exportación PDF, importación de datos y recepción remota siguen pendientes en un navegador con origen HTTPS. La v3.1 es una versión de revisión, no de despliegue.
