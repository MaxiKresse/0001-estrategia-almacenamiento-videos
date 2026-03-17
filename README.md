# 0001-estrategia-almacenamiento-videos

**Fecha:** 17 de marzo 2026

## 1. Contexto
La empresa "EducaMás" está desarrollando una plataforma de cursos online. El equipo de desarrollo se encuentra debatiendo sobre la estrategia de almacenamiento y distribución de los videos de los cursos, evaluando dos alternativas:
* **Opción A:** Almacenamiento en la nube con CDN (ej. AWS S3 o Google Cloud Storage combinado con una CDN).
* **Opción B:** Almacenamiento en servidores propios de la empresa.


Para tomar la decision, se han evaluado los siguente factores del proyecto:
* **a. Volumen estimado de videos:** Se esperan 500 horas de video en el primer año.
* **b. Trafico esperado:** se esperan 10000 usuarios concurrentes.
* **c. Presupuesto:** Contamos con un presupuesto limitado para adquisicion de infraestructura fisica inicial.
* **d. Requisito:de rendimiento** Es critico mantener una baja latencia en la reproduccion de los videso para asegurar una buena experiencia del estudiante.
* **e. Requisitos de seguridad:** Los videos deber estar protegidos contra descargas no autorizadas(pirateria).
* **f. Conocimiento tecnicos del equipo:** El equipo tiene experiencia gestionando servidores tradicionales, pero poca experiencia configurando y administrando CDNs.

## 2. Decision 
Se elige la **Opcion A: Almacenamiento en la nueba con CDN**

**Justificacion:**
Al contar con un presupuesto limitado para infraestructura, la Opcion A nos permite un modelo de pago por uso, evitando la costosa compra inicial de servidores fisicos que requeriria la Opcion B para soportar 10000 usuarios concurrentes. Ademas, el uso de una CDN es la forma mas viable de garantizar la baja latencia en la en la reproduccion que exige el negocio, distribuyendo la carga de manera eficiente. Aunque el equipo tiene poca experiencia con CDNs, los beneficios en escalabilidad y ahorra inicial superan la curva de aprendizaje necesaria.

## 3. Consecuencias
* **a. Impacto en el desarrollo:** Se requerirá integrar con la API del proveedor de la nube y configurar la CDN para asegurar la entrega y la protección contra descargas.
* **b. Impacto en el mantenimiento:** El mantenimiento físico de la infraestructura será responsabilidad del proveedor de la nube, liberando tiempo para nuestro equipo.
* **c. Impacto en los costos:** Se incurrirá en costos operativos mensuales de almacenamiento y transferencia de datos, pero se evitarán los grandes costos de hardware y mantenimiento de servidores propios.
* **d. Riesgos:** Se genera dependencia de un proveedor externo y existe un posible aumento de costos a largo plazo si el tráfico de estudiantes crece considerablemente.

## 4. Estado
Aceptado 

