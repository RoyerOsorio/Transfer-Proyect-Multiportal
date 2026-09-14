# Multiportal de Reembolsos — Contexto Integral de Negocio

> Documento de transferencia de conocimiento para comprender el dominio de **Reembolsos Médicos**.
>
> **Alcance:** exclusivamente negocio. Este documento describe propósito, actores, conceptos, reglas, responsabilidades, decisiones, procesos, variabilidad y lenguaje del dominio. No prescribe soluciones de implementación.

---

## 1. Resumen ejecutivo

El dominio del **Multiportal de Reembolsos** administra el ciclo de vida completo de una solicitud de reembolso por gastos médicos u odontológicos, desde su presentación hasta su resolución definitiva, pago cuando procede y cierre.

El problema fundamental que resuelve el negocio es:

> **Determinar, de manera objetiva, trazable y auditable, si un gasto realizado por una persona cubierta genera derecho a un reembolso conforme a las condiciones aplicables y, cuando existe ese derecho, determinar el importe reconocido y cumplir la obligación económica correspondiente.**

El concepto central es el **Reclamo (Solicitud de Reembolso)**. Alrededor de él convergen:

- la persona que solicita el reembolso;
- la persona que recibió la atención;
- la póliza aplicable;
- las coberturas y beneficios;
- los gastos reclamados;
- los documentos de soporte;
- la información médica u odontológica;
- la validación administrativa;
- las evaluaciones de cobertura;
- las decisiones de negocio;
- el reembolso autorizado;
- la información bancaria cuando corresponde;
- el pago;
- y el cierre del expediente.

Todas las decisiones relevantes deben poder explicarse a partir de los hechos del caso, las condiciones contractuales y las reglas de negocio vigentes.

---

## 2. Origen y problema de negocio

El negocio de reembolsos proviene de capacidades que históricamente se encuentran distribuidas entre varios sistemas y procesos. Existen diferencias funcionales y operativas entre clientes, coberturas y tipos de atención.

Esta fragmentación produce problemas como:

- duplicidad funcional;
- diferencias operativas entre clientes;
- conocimiento disperso;
- dependencia del conocimiento de personas específicas;
- dificultad para evolucionar reglas y procesos;
- proliferación de excepciones;
- crecimiento de configuraciones particulares;
- complejidad para mantener una visión consistente del ciclo completo del reembolso.

La intención empresarial es consolidar el conocimiento y las capacidades del negocio bajo un modelo común, sin eliminar la variabilidad legítima entre clientes.

---

## 3. Objetivo del negocio

El negocio debe poder administrar una solicitud desde su nacimiento hasta uno de sus resultados finales:

1. **Reembolso procedente**, seguido del cumplimiento de la obligación económica.
2. **Reembolso parcialmente procedente**, cuando solamente una parte de los conceptos o importes reclamados es reconocida.
3. **Reembolso no procedente**, cuando las condiciones aplicables no generan derecho al pago.
4. **Cierre sin pago**, cuando el resultado del expediente no genera una obligación económica.

El objetivo no es simplemente “pagar solicitudes”. Antes del pago existe un proceso de determinación de derechos.

Por ello, conceptualmente:

**Gasto reclamado → verificación de condiciones → evaluación → decisión → derecho económico → pago**

El pago es una consecuencia de una decisión favorable; no constituye por sí mismo la decisión de cobertura.

---

## 4. Principios fundamentales del dominio

### 4.1 El Reclamo es el eje del expediente

El **Reclamo** representa formalmente la solicitud de reembolso presentada al negocio.

Es el expediente alrededor del cual se relacionan:

- solicitante;
- beneficiario;
- póliza;
- gastos reclamados;
- documentos;
- evaluaciones;
- decisiones;
- reembolso;
- pago.

### 4.2 Reclamar un gasto no implica tener derecho al reembolso

La existencia de un Reclamo expresa una solicitud.

El derecho económico solamente nace después de comprobar las condiciones que correspondan y emitir las decisiones necesarias.

### 4.3 La Póliza establece el marco contractual

La **Póliza (Póliza)** establece el marco bajo el cual debe analizarse el Reclamo.

La existencia de una póliza por sí sola no implica que cualquier gasto sea reembolsable. Deben considerarse también:

- vigencia;
- persona cubierta;
- cobertura;
- beneficio;
- condiciones;
- límites;
- restricciones;
- exclusiones;
- requisitos;
- reglas aplicables al caso.

### 4.4 Las decisiones deben estar sustentadas

Una decisión de negocio debe derivarse de evidencia y reglas identificables.

El negocio debe poder explicar:

- qué se evaluó;
- con qué información;
- bajo qué condiciones;
- qué regla fue relevante;
- cuál fue el resultado;
- y qué consecuencia produjo.

### 4.5 El expediente debe ser trazable

Debe existir continuidad conceptual entre:

**Reclamo → Póliza → Cobertura/Beneficio → evidencia → evaluación → decisión → Reembolso → Pago**

### 4.6 La variabilidad por cliente es parte del negocio

No todos los clientes operan exactamente igual.

Pueden variar:

- coberturas;
- documentos;
- reglas;
- etapas;
- validaciones;
- procesos de dictamen;
- requisitos bancarios;
- mecanismos operativos de pago.

La variabilidad debe considerarse una característica empresarial legítima, no una excepción accidental.

---

## 5. Conceptos fundamentales

## 5.1 Reclamo

Solicitud formal mediante la cual se reclama el reembolso de uno o más gastos.

El Reclamo:

- pertenece a un expediente identificable;
- está asociado con la persona que ejerce la solicitud;
- se analiza bajo una Póliza aplicable;
- contiene uno o más conceptos reclamados;
- acumula evidencia;
- recibe evaluaciones y decisiones;
- puede generar un Reembolso;
- puede culminar en un Pago.

---

## 5.2 Ítem del Reclamo

Unidad individual de gasto o concepto dentro de un Reclamo.

Un Reclamo puede contener varios Ítems del Reclamo.

Los Ítems del Reclamo permiten que diferentes conceptos dentro de una misma solicitud sean evaluados independientemente. Por ello, un Reclamo puede terminar con resultados mixtos:

- conceptos aceptados;
- conceptos parcialmente reconocidos;
- conceptos rechazados.

La resolución económica global del Reclamo se obtiene a partir de las decisiones sobre las unidades que lo componen.

---

## 5.3 Póliza

Acuerdo contractual que establece el marco de derechos y restricciones aplicable al Afiliado y sus dependientes cubiertos.

La Póliza es una fuente de autoridad para determinar si el gasto reclamado puede generar un derecho de reembolso.

---

## 5.4 Afiliado

Persona cubierta dentro de la relación contractual.

El Afiliado origina el derecho potencial derivado de la Póliza.

Dependiendo del caso, puede actuar también como:

- titular;
- beneficiario;
- reclamante.

Estos roles no deben asumirse como equivalentes en todos los casos.

---

## 5.5 Dependiente

Persona vinculada al Afiliado que puede encontrarse cubierta conforme a las condiciones aplicables.

Un dependiente puede ser el beneficiario de la atención aunque otra persona sea quien presente o administre el Reclamo.

---

## 5.6 Reclamante

Persona que ejerce formalmente la solicitud de reembolso.

El Reclamante y el beneficiario pueden ser personas distintas.

---

## 5.7 Beneficiario

Persona respecto de la cual se originó el gasto médico u odontológico reclamado.

Puede ser:

- el propio titular;
- un Afiliado;
- un Dependiente.

---

## 5.8 Cobertura

La **Cobertura** define qué categoría de riesgo, atención, tratamiento o gasto puede ser reconocida bajo determinadas condiciones.

Una Póliza puede ofrecer múltiples coberturas.

La evaluación de un Reclamo puede involucrar una o más coberturas relevantes.

---

## 5.9 Beneficio

El **Beneficio** representa el derecho o prestación económica definida dentro del marco contractual.

La cobertura responde principalmente a **qué tipo de situación está protegida**.

El beneficio ayuda a determinar **qué derecho económico corresponde bajo esa protección y bajo qué condiciones**.

---

## 5.10 Documento de Soporte

Documento o evidencia presentada para demostrar hechos relevantes del Reclamo.

Dependiendo de la cobertura y del cliente pueden requerirse documentos diferentes.

Los documentos pueden servir para comprobar, entre otros:

- identidad;
- atención recibida;
- gasto;
- diagnóstico;
- procedimiento;
- prescripción;
- relación con el beneficiario;
- información necesaria para evaluar cobertura;
- información necesaria para realizar el pago.

Un documento puede:

- ser aceptado;
- requerir corrección;
- resultar insuficiente;
- ser rechazado;
- provocar una solicitud de información adicional.

---

## 5.11 Diagnóstico

Información clínica que describe la condición o motivo médico relacionado con la atención.

Puede ser relevante para determinar la procedencia de ciertos conceptos o coberturas.

---

## 5.12 Procedimiento Médico

Procedimiento, tratamiento o intervención relacionada con el gasto reclamado.

Puede ser objeto de evaluación respecto de:

- pertinencia;
- relación con el diagnóstico;
- cobertura;
- restricciones;
- monto reconocido.

---

## 5.13 Elegibilidad

Determinación acerca de si la persona y las condiciones básicas del caso permiten continuar con la evaluación del derecho reclamado.

La elegibilidad no equivale automáticamente a aprobación de cobertura.

Una persona puede ser elegible y aun así un concepto específico resultar no cubierto.

---

## 5.14 Decisión de Cobertura

Determinación formal sobre la procedencia de una cobertura o concepto reclamado.

Puede concluir, según las reglas aplicables, que el concepto:

- procede;
- procede parcialmente;
- no procede;
- requiere información adicional antes de poder resolverse.

La Decisión de Cobertura es una de las decisiones centrales del dominio.

---

## 5.15 Reembolso

Derecho económico reconocido como consecuencia de una resolución favorable total o parcial.

Debe distinguirse entre:

- **importe reclamado**: lo que solicita el Reclamante;
- **importe reconocido/autorizado**: lo que el negocio determina que corresponde;
- **importe pagado**: lo efectivamente cumplido mediante el Pago.

Estos importes no necesariamente son iguales.

---

## 5.16 Pago

Cumplimiento económico de un Reembolso previamente autorizado.

El Pago no decide si el gasto estaba cubierto. Materializa una obligación ya reconocida.

---

## 6. Participantes y actores del negocio

Los roles pueden variar según la organización o cliente, pero conceptualmente existen las siguientes responsabilidades.

### Asegurado / Reclamante

Presenta la solicitud y da seguimiento al trámite.

Puede proporcionar:

- información del caso;
- documentos;
- correcciones;
- información complementaria;
- datos necesarios para el pago.

### Beneficiario

Persona para la cual se solicita el reconocimiento del gasto.

No necesariamente es quien presenta el Reclamo ni quien recibe el pago.

### Titular de la Póliza

Titular de la relación contractual correspondiente.

Su papel debe distinguirse del beneficiario y del Reclamante.

### Representante del Dependiente

Persona que actúa en representación de un dependiente cuando el proceso lo requiere.

### Proveedor Médico

Profesional o institución relacionada con la atención médica u odontológica que origina evidencia relevante para el expediente.

### Dictaminador Administrativo / Analista de Reclamos

Responsable de revisar la integridad y suficiencia administrativa del expediente.

Puede:

- aceptar documentación;
- solicitar correcciones;
- identificar faltantes;
- rechazar evidencia inválida;
- canalizar el expediente hacia la evaluación correspondiente.

### Médico Dictaminador / Revisor Médico

Responsable del análisis especializado de naturaleza médica.

Puede:

- analizar diagnósticos;
- revisar procedimientos;
- evaluar conceptos;
- reconocer o rechazar importes conforme a las condiciones aplicables;
- solicitar información adicional.

### Odontólogo Dictaminador

Cumple una función equivalente para asuntos odontológicos, considerando información propia del dominio dental, como el odontograma cuando resulte necesario.

### Validador Bancario

Interviene cuando las reglas del cliente exigen verificar la información bancaria antes del pago.

### Operador de Pagos

Gestiona las actividades necesarias para cumplir la obligación económica reconocida.

### Administrador del Negocio

Mantiene las definiciones empresariales configurables necesarias para operar, tales como:

- clientes;
- grupos;
- subgrupos;
- coberturas;
- requisitos documentales;
- parámetros y reglas operativas.

### Empleador

Organización que puede participar en la relación empresarial y contractual, especialmente en esquemas colectivos.

### Compañía Aseguradora

Entidad responsable del marco asegurador y de las obligaciones derivadas de las condiciones aplicables.

---

## 7. Organización empresarial por cliente, grupo y subgrupo

El negocio contempla diferencias entre organizaciones.

Una organización cliente puede definir estructuras internas de **grupos y subgrupos** con condiciones diferentes.

Estas estructuras pueden influir en:

- coberturas disponibles;
- requisitos;
- documentos;
- reglas;
- flujo;
- validaciones;
- condiciones económicas.

Por ello, las condiciones aplicables a un Reclamo no deben inferirse únicamente del tipo genérico de gasto. Deben determinarse dentro del contexto empresarial y contractual correspondiente.

La combinación de **grupo + subgrupo + cobertura**, junto con su vigencia y reglas asociadas, puede determinar qué configuración empresarial resulta aplicable al caso.

---

## 8. Capacidades del negocio

Las principales capacidades identificadas son:

### Administración de clientes

Gestionar las organizaciones para las cuales se opera el negocio de reembolsos.

### Administración de grupos y subgrupos

Representar subdivisiones empresariales con condiciones particulares.

### Administración de coberturas

Definir las coberturas disponibles y sus condiciones.

### Configuración documental

Determinar qué evidencia es necesaria para cada escenario.

### Administración de pólizas

Gestionar las relaciones contractuales, certificados y personas cubiertas.

### Administración de beneficiarios

Mantener las relaciones entre titulares, Afiliados y Dependientes.

### Captura de solicitudes

Formalizar un nuevo Reclamo.

### Recepción y corrección documental

Incorporar evidencia y permitir subsanar información insuficiente.

### Validación administrativa

Determinar si el expediente cuenta con los requisitos necesarios para avanzar.

### Verificación de elegibilidad

Determinar si las condiciones básicas contractuales y personales permiten evaluar el derecho reclamado.

### Evaluación de cobertura

Analizar cada concepto relevante frente a las condiciones aplicables.

### Dictamen médico

Resolver aspectos que requieren juicio especializado médico.

### Dictamen odontológico

Resolver aspectos que requieren juicio especializado dental.

### Determinación del beneficio

Establecer el efecto económico derivado de las coberturas procedentes.

### Autorización del reembolso

Formalizar el derecho económico reconocido.

### Validación bancaria

Comprobar los datos bancarios cuando las reglas aplicables lo exijan.

### Gestión del pago

Cumplir la obligación económica autorizada.

### Cierre

Concluir el expediente una vez que todas las decisiones y consecuencias necesarias hayan sido resueltas.

### Reportería y seguimiento

Permitir la comprensión operativa y ejecutiva de los Reclamos y sus resultados.

---

## 9. Flujo integral del negocio

El flujo esencial puede entenderse de la siguiente forma.

### Etapa 1 — Preparación del marco empresarial

Antes de recibir Reclamos deben existir las definiciones que determinan cómo opera el negocio:

1. cliente;
2. grupos y subgrupos;
3. coberturas;
4. requisitos;
5. reglas;
6. pólizas;
7. Afiliados y Dependientes.

### Etapa 2 — Nacimiento del Reclamo

El Reclamante presenta una solicitud.

Se identifican:

- quién reclama;
- para quién se reclama;
- qué gastos se reclaman;
- qué evidencia se presenta;
- cuál es el contexto contractual relevante.

### Etapa 3 — Validación de información

Se revisa que la información necesaria esté presente y sea utilizable.

Si existen faltantes o inconsistencias, el expediente puede requerir corrección o información adicional.

### Etapa 4 — Identificación de Póliza y elegibilidad

Se determina el marco contractual aplicable y si la persona/caso reúne las condiciones necesarias para continuar.

### Etapa 5 — Identificación de coberturas relevantes

Los gastos reclamados se relacionan con las coberturas que potencialmente podrían aplicar.

### Etapa 6 — Evaluación de Ítems del Reclamo

Los conceptos reclamados son evaluados.

Diferentes Ítems del Reclamo pueden requerir diferentes análisis y producir decisiones distintas.

Cuando varias evaluaciones son independientes, pueden avanzar conceptualmente sin que una decisión favorable en una cobertura implique automáticamente una decisión favorable en otra.

### Etapa 7 — Dictamen especializado

Cuando el tipo de gasto lo exige, interviene un especialista médico u odontológico.

Puede:

- reconocer el concepto;
- reconocerlo parcialmente;
- rechazarlo;
- solicitar información adicional.

### Etapa 8 — Resolución de excepciones y faltantes

Cuando la información es insuficiente, el Reclamo puede quedar pendiente hasta recibir lo necesario.

No debe emitirse una decisión definitiva favorable o desfavorable cuando una regla exige evidencia que todavía no ha sido resuelta.

### Etapa 9 — Consolidación de decisiones

Antes de determinar el resultado económico final deben estar resueltas las evaluaciones necesarias del Reclamo.

Existe una **barrera conceptual de consolidación**: el negocio no debe tratar el Reclamo como económicamente resuelto mientras existan decisiones obligatorias pendientes.

### Etapa 10 — Determinación del Reembolso

Las decisiones favorables y parciales se traducen en el importe reconocido conforme a las reglas aplicables.

### Etapa 11 — Validación bancaria, cuando aplique

Algunos clientes requieren validación de la cuenta antes de cumplir el pago.

Esta etapa es condicional.

### Etapa 12 — Pago

Cuando existe un Reembolso autorizado y se satisfacen las condiciones previas al pago, se cumple la obligación económica.

El modelo de negocio contempla el **pago a nivel del Reclamo** como resultado económico consolidado, aunque su importe derive de múltiples decisiones sobre los conceptos reclamados.

### Etapa 13 — Cierre

El Reclamo puede cerrarse cuando:

- las evaluaciones necesarias están resueltas;
- existe una decisión final;
- las consecuencias económicas correspondientes fueron atendidas;
- no existen actividades obligatorias pendientes.

---

## 10. Naturaleza de las evaluaciones de cobertura

Una característica importante del negocio es que un mismo Reclamo puede involucrar más de una evaluación.

Cada evaluación debe conservar su significado propio.

Ejemplo conceptual:

Un Reclamo contiene tres Ítems del Reclamo:

- gasto A;
- gasto B;
- gasto C.

Después de la evaluación:

- A puede ser reconocido completamente;
- B puede ser reconocido parcialmente;
- C puede ser rechazado.

El resultado del Reclamo no debe reducir estas decisiones a un simple “aprobado/rechazado” sin conservar el detalle.

El importe reembolsable final surge de las decisiones válidas sobre los conceptos reclamados.

---

## 11. Decisiones fundamentales del negocio

El dominio gira alrededor de decisiones explícitas.

### ¿Existe un Reclamo válido?

Determina si la solicitud puede ser reconocida como expediente de negocio.

### ¿Qué Póliza aplica?

Identifica el marco contractual bajo el cual se evaluará.

### ¿La persona es elegible?

Determina si la persona y el caso reúnen las condiciones básicas.

### ¿La información es suficiente?

Determina si puede emitirse una evaluación responsable.

### ¿Qué Cobertura aplica?

Identifica qué protección contractual debe evaluarse.

### ¿El gasto procede?

Determina si un Ítem del Reclamo cumple las condiciones correspondientes.

### ¿Qué importe procede?

Determina el importe reconocido cuando no coincide necesariamente con lo reclamado.

### ¿Se requiere evaluación especializada?

Determina si el caso necesita intervención médica, odontológica u otra revisión empresarial.

### ¿Se requiere información adicional?

Suspende una decisión definitiva hasta contar con evidencia suficiente.

### ¿Existe derecho a Reembolso?

Consolida las decisiones que generan una obligación económica.

### ¿Puede realizarse el Pago?

Comprueba que las condiciones posteriores a la autorización estén satisfechas.

### ¿Puede cerrarse el Reclamo?

Determina si el expediente ha alcanzado una condición terminal válida.

---

## 12. Invariantes y reglas estructurales

Las siguientes condiciones expresan reglas conceptuales que deben preservarse.

### 12.1 Un Pago requiere un Reembolso autorizado

No debe existir pago sin una obligación económica previamente reconocida.

### 12.2 Un Reembolso depende de decisiones de cobertura

No debe existir derecho económico sin una decisión que justifique su procedencia.

### 12.3 Una Decisión de Cobertura requiere un Reclamo evaluable

La decisión debe referirse a un expediente y a hechos identificables.

### 12.4 Un Reclamo debe evaluarse bajo condiciones aplicables

Las decisiones no pueden emitirse desconectadas de la Póliza, Cobertura, Beneficio y Reglas de Negocio correspondientes.

### 12.5 Los importes deben conservar su significado

Debe distinguirse entre:

- reclamado;
- reconocido;
- pagado.

### 12.6 La ausencia de información puede impedir una decisión definitiva

Cuando la evidencia requerida es insuficiente, debe resolverse el faltante antes de emitir una decisión que dependa de esa información.

### 12.7 Las decisiones independientes no deben contaminarse

El rechazo de un Ítem del Reclamo o Cobertura no implica necesariamente el rechazo de los demás.

### 12.8 El resultado económico requiere consolidación

El Reclamo no debe avanzar al cumplimiento económico final mientras existan evaluaciones obligatorias pendientes.

### 12.9 El Pago corresponde al resultado económico consolidado del Reclamo

Aunque múltiples conceptos contribuyan al importe final, el negocio mantiene la obligación de pago vinculada al Reclamo y a su resultado autorizado.

### 12.10 Las reglas deben interpretarse según su vigencia

Cuando las condiciones empresariales cambian, debe utilizarse la versión que corresponda al caso conforme a las reglas de efectividad del negocio.

### 12.11 Las decisiones y movimientos relevantes deben ser trazables

El negocio debe conservar el significado de:

- quién realizó una acción;
- qué decisión se tomó;
- cuándo;
- sobre qué elemento;
- con qué fundamento empresarial;
- y qué consecuencia produjo.

---

## 13. Estados conceptuales del Reclamo

Los nombres operativos exactos pueden variar, pero el ciclo conceptual distingue situaciones como:

- registrado;
- en validación;
- pendiente de información;
- listo para evaluación;
- en evaluación;
- parcialmente resuelto;
- pendiente de consolidación;
- resuelto favorablemente;
- resuelto parcialmente;
- rechazado;
- pendiente de condiciones de pago;
- autorizado para pago;
- pagado;
- cerrado.

El estado del Reclamo debe representar una realidad empresarial y no ocultar decisiones pendientes.

---

## 14. Estados conceptuales de una evaluación

Una evaluación individual puede encontrarse, conceptualmente, en situaciones como:

- pendiente;
- en análisis;
- pendiente de información;
- procedente;
- parcialmente procedente;
- no procedente.

El Reclamo y sus evaluaciones tienen ciclos relacionados, pero no idénticos.

---

## 15. Eventos empresariales relevantes

El negocio reconoce acontecimientos significativos durante el ciclo de vida, por ejemplo:

- Reclamo presentado;
- Reclamo registrado;
- documento recibido;
- documento aceptado;
- corrección solicitada;
- información adicional solicitada;
- información adicional recibida;
- Póliza identificada;
- elegibilidad verificada;
- Cobertura identificada;
- evaluación iniciada;
- evaluación médica realizada;
- evaluación odontológica realizada;
- Decisión de Cobertura emitida;
- Ítem del Reclamo aprobado;
- Ítem del Reclamo parcialmente aprobado;
- Ítem del Reclamo rechazado;
- evaluaciones requeridas completadas;
- Reembolso determinado;
- Reembolso autorizado;
- información bancaria validada;
- Pago realizado;
- Pago fallido o pendiente de resolución;
- Reclamo cerrado.

Un evento expresa **algo que ya ocurrió en el negocio**.

---

## 16. Documentación y evidencia

La documentación no es uniforme para todos los casos.

Los requisitos pueden depender de:

- cliente;
- grupo;
- subgrupo;
- cobertura;
- tipo de atención;
- tipo de Reclamo;
- naturaleza del gasto;
- evaluación especializada requerida.

El proceso documental debe admitir:

1. recepción;
2. revisión;
3. aceptación;
4. rechazo;
5. corrección;
6. complementación.

La documentación tiene valor probatorio: permite justificar decisiones posteriores.

---

## 17. Evaluación médica y odontológica

No todos los Reclamos requieren el mismo tipo de dictamen.

### Evaluación médica

Puede considerar:

- diagnóstico;
- procedimiento;
- relación entre diagnóstico y tratamiento;
- documentación clínica;
- procedencia del concepto;
- restricciones;
- importe reconocido.

### Evaluación odontológica

Comparte principios con la evaluación médica, pero puede requerir evidencia especializada propia del ámbito dental, como odontogramas u otros elementos clínicos específicos.

La existencia de especialistas diferentes refleja una diferencia real de conocimiento de negocio.

---

## 18. Validación bancaria

La validación bancaria es una etapa **opcional y condicionada por las reglas del cliente**.

Su finalidad es comprobar que la información necesaria para realizar el pago satisface las condiciones requeridas.

No determina cobertura.

Debe mantenerse conceptualmente separada de la decisión sobre si el gasto genera derecho a reembolso.

---

## 19. Pago y cierre

Una vez reconocido el Reembolso, el negocio debe cumplir la obligación económica.

Debe distinguirse claramente entre:

- **decisión favorable**;
- **autorización del importe**;
- **cumplimiento mediante Pago**.

Un Reclamo favorable todavía puede encontrarse pendiente de pago.

Asimismo, un problema durante el cumplimiento del pago no transforma retroactivamente una decisión de cobertura favorable en un rechazo.

El cierre representa que el expediente ya no tiene obligaciones empresariales pendientes dentro de su ciclo normal.

---

## 20. Variabilidad empresarial

La variabilidad es uno de los aspectos más importantes del dominio.

### Puede variar por cliente

- flujo;
- documentación;
- coberturas;
- validaciones;
- reglas;
- proceso de pago.

### Puede variar por grupo o subgrupo

Diferentes poblaciones dentro del mismo cliente pueden tener condiciones distintas.

### Puede variar por Cobertura

Una cobertura médica puede exigir un conjunto de requisitos diferente de una cobertura dental.

### Puede variar por tipo de evaluación

Algunos casos requieren revisión administrativa únicamente; otros requieren dictamen especializado.

### Puede variar por vigencia

Las condiciones pueden cambiar con el tiempo.

Por ello, dos Reclamos aparentemente similares pueden producir resultados diferentes si fueron evaluados bajo condiciones empresariales distintas.

---

## 21. Casos conceptuales importantes

### Caso A — Reembolso totalmente procedente

1. Se presenta el Reclamo.
2. La información es suficiente.
3. La persona es elegible.
4. La Cobertura aplica.
5. Los Ítems del Reclamo son procedentes.
6. Se determina el importe reconocido.
7. Se autoriza el Reembolso.
8. Se satisfacen las condiciones de pago.
9. Se realiza el Pago.
10. Se cierra el Reclamo.

### Caso B — Reembolso parcialmente procedente

1. El Reclamo contiene varios conceptos.
2. Algunos cumplen las condiciones.
3. Otros no.
4. Se conservan las decisiones individuales.
5. El Reembolso refleja solamente los importes reconocidos.
6. Se realiza el Pago correspondiente.
7. El expediente se cierra conservando la explicación de los conceptos no reconocidos.

### Caso C — Información insuficiente

1. Se recibe el Reclamo.
2. Durante la revisión se detecta evidencia faltante.
3. Se solicita información adicional.
4. El expediente permanece pendiente.
5. Se recibe la evidencia.
6. Continúa la evaluación.

### Caso D — No procedencia

1. El Reclamo es presentado correctamente.
2. Se identifica la Póliza.
3. Se evalúa el concepto.
4. Una condición, restricción o exclusión aplicable impide reconocer el gasto.
5. Se emite una decisión no procedente.
6. Si no existen otros conceptos favorables, no nace un Reembolso.
7. El Reclamo se cierra con la justificación correspondiente.

### Caso E — Resultados paralelos

1. Un Reclamo contiene múltiples Ítems del Reclamo.
2. Diferentes conceptos son evaluados de manera independiente.
3. Algunas evaluaciones terminan antes que otras.
4. El Reclamo todavía no se considera económicamente consolidado mientras existan decisiones obligatorias pendientes.
5. Una vez resueltas todas, se determina el resultado final.

---

## 22. Relaciones conceptuales principales

Las relaciones fundamentales pueden resumirse así:

- una **Póliza** cubre a uno o más **Afiliados** conforme a sus condiciones;
- un **Afiliado** puede estar relacionado con **Dependientes**;
- un **Reclamante** presenta un **Reclamo**;
- un **Reclamo** corresponde a un beneficiario y referencia una **Póliza** aplicable;
- un **Reclamo** contiene uno o más **Ítems del Reclamo**;
- un **Reclamo** reúne **Documentos de Soporte**;
- un **Ítem del Reclamo** puede relacionarse con diagnóstico, procedimiento y cobertura;
- una **Decisión de Cobertura** resulta de evaluar el Reclamo o sus conceptos;
- las decisiones favorables determinan un **Reembolso**;
- un **Reembolso** autorizado se cumple mediante un **Pago**.

Estas relaciones representan hechos del negocio.

---

## 23. Separación de responsabilidades empresariales

El dominio puede comprenderse mediante cinco grandes grupos conceptuales.

### Contractuales

- Póliza
- Cobertura
- Beneficio

Definen derechos, restricciones y condiciones.

### Participantes

- Afiliado
- Dependiente
- Reclamante
- Titular de la Póliza
- Proveedor Médico
- Empleador
- Compañía Aseguradora

Representan quién participa y en qué calidad.

### Operativos

- Reclamo
- Ítem del Reclamo
- Documento de Soporte

Representan el expediente y sus elementos de trabajo.

### Decisionales

- Elegibilidad
- Decisión de Cobertura
- decisiones administrativas;
- decisiones especializadas;
- Reembolso.

Transforman hechos, evidencia y reglas en resultados empresariales.

### Financieros

- Pago

Materializan las obligaciones económicas reconocidas.

---

## 24. Autoridad de negocio

Dentro del dominio existen distintas fuentes de autoridad.

### Autoridad contractual

Póliza, Cobertura y Beneficio establecen qué derechos y restricciones existen.

### Autoridad de configuración empresarial

Las definiciones aplicables por cliente, grupo, subgrupo y cobertura determinan requisitos y comportamiento permitido.

### Autoridad administrativa

Determina suficiencia documental y cumplimiento de requisitos operativos.

### Autoridad especializada

Los dictaminadores médicos u odontológicos resuelven aspectos que requieren conocimiento profesional.

### Autoridad decisional

Las decisiones formalizadas determinan el resultado reconocido por el negocio.

### Autoridad económica

El Reembolso expresa la obligación económica autorizada; el Pago expresa su cumplimiento.

Ninguna de estas responsabilidades debe confundirse con otra.

---

## 25. Trazabilidad y auditabilidad

La trazabilidad es una necesidad esencial del negocio.

Para cualquier Reclamo debería ser posible reconstruir conceptualmente:

1. quién presentó la solicitud;
2. quién fue el beneficiario;
3. qué Póliza se utilizó;
4. qué condiciones estaban vigentes;
5. qué Ítems del Reclamo fueron reclamados;
6. qué documentos fueron aportados;
7. qué información faltó y fue solicitada;
8. quién realizó cada evaluación;
9. qué decisiones fueron emitidas;
10. qué conceptos fueron aceptados, parcialmente reconocidos o rechazados;
11. qué importes fueron reclamados;
12. qué importes fueron reconocidos;
13. qué Reembolso fue autorizado;
14. qué Pago se realizó;
15. cuál fue el resultado final del expediente.

La trazabilidad no es únicamente histórica: permite explicar y defender las decisiones del negocio.

---

## 26. Riesgos empresariales

Los principales riesgos identificados son:

- crecimiento continuo de reglas específicas por cliente;
- proliferación de excepciones;
- aumento de configuraciones particulares;
- complejidad creciente de los flujos;
- cambios frecuentes en reglas operativas;
- inconsistencias entre procesos equivalentes;
- pérdida del significado común de los conceptos;
- decisiones difíciles de explicar;
- dependencia excesiva del conocimiento tácito de especialistas.

Por ello, el dominio necesita mantener un lenguaje consistente y responsabilidades empresariales claramente delimitadas.

---

## 27. Lenguaje ubicuo mínimo

| Término | Significado empresarial |
|---|---|
| Reclamo | Solicitud formal de reembolso y expediente central del proceso. |
| Ítem del Reclamo | Concepto individual de gasto reclamado dentro de un Reclamo. |
| Reclamante | Persona que presenta o ejerce la solicitud. |
| Beneficiario | Persona que recibió la atención o respecto de la cual se originó el gasto. |
| Afiliado | Persona cubierta conforme a la relación contractual. |
| Dependiente | Persona relacionada con un Afiliado que puede estar cubierta. |
| Póliza | Marco contractual aplicable al Reclamo. |
| Cobertura | Protección aplicable a una categoría de riesgo, atención o gasto. |
| Beneficio | Derecho o prestación económica definida bajo determinadas condiciones. |
| Documento de Soporte | Evidencia documental utilizada para sustentar hechos del Reclamo. |
| Diagnóstico | Condición o motivo clínico relacionado con la atención. |
| Procedimiento Médico | Procedimiento o tratamiento relacionado con el gasto reclamado. |
| Elegibilidad | Determinación de que la persona/caso reúne condiciones básicas para evaluación. |
| Decisión de Cobertura | Determinación sobre la procedencia total, parcial o negativa de una cobertura o concepto. |
| Reembolso | Derecho económico reconocido después de una decisión favorable. |
| Pago | Cumplimiento económico del Reembolso autorizado. |
| Regla de Negocio | Condición empresarial que gobierna una decisión o comportamiento. |
| Decisión de Negocio | Determinación explícita que modifica el curso o resultado del expediente. |
| Evento de Negocio | Hecho empresarial relevante que ya ocurrió. |
| Estado de Negocio | Condición significativa en la que se encuentra un concepto durante su ciclo de vida. |

---

## 28. Distinciones semánticas críticas

### Reclamo ≠ Reembolso

El Reclamo es la solicitud.

El Reembolso es el derecho económico reconocido como resultado de evaluarla.

### Reembolso ≠ Pago

El Reembolso representa la obligación reconocida.

El Pago representa su cumplimiento.

### Reclamante ≠ Beneficiario

El Reclamante presenta la solicitud.

El Beneficiario es la persona respecto de la cual se originó el gasto.

Pueden coincidir, pero no necesariamente.

### Elegibilidad ≠ Decisión de Cobertura

La elegibilidad permite determinar que el caso puede ser considerado dentro del marco correspondiente.

La Decisión de Cobertura determina la procedencia de un concepto o cobertura concreta.

### Cobertura ≠ Beneficio

Cobertura expresa qué situación o categoría se encuentra protegida.

Beneficio expresa la prestación o derecho derivado de esa protección.

### Importe Reclamado ≠ Importe Aprobado ≠ Importe Pagado

Lo solicitado, lo reconocido y lo efectivamente pagado son conceptos distintos.

### Validación Administrativa ≠ Decisión Médica

La validación administrativa comprueba requisitos y suficiencia documental.

El dictamen médico u odontológico resuelve cuestiones especializadas.

### Decisión de Cobertura ≠ Validación Bancaria

La cobertura determina si existe derecho.

La validación bancaria verifica condiciones necesarias para ejecutar el pago cuando corresponda.

---

## 29. Modelo mental compacto

Claude puede utilizar el siguiente modelo mental para razonar sobre cualquier escenario del proyecto:

1. **Existe una persona cubierta dentro de un marco contractual.**
2. **Ocurre un gasto médico u odontológico.**
3. **Una persona presenta un Reclamo para solicitar su reembolso.**
4. **El Reclamo contiene uno o más Ítems del Reclamo y evidencia.**
5. **El negocio identifica la Póliza y las condiciones aplicables.**
6. **Comprueba elegibilidad y suficiencia de información.**
7. **Evalúa cada concepto contra las Coberturas, Beneficios y Reglas de Negocio relevantes.**
8. **Cuando es necesario, intervienen especialistas.**
9. **Cada evaluación produce una decisión explicable.**
10. **Las decisiones requeridas se consolidan.**
11. **Las decisiones favorables generan un Reembolso por el importe reconocido.**
12. **Se satisfacen las condiciones previas al pago, incluida validación bancaria cuando corresponda.**
13. **El Reembolso se cumple mediante Pago.**
14. **El Reclamo se cierra conservando la trazabilidad completa de lo ocurrido.**

---

## 30. Regla de interpretación para futuras conversaciones

Cuando se analice este proyecto, debe preservarse siempre la perspectiva del negocio:

- primero identificar el hecho empresarial;
- después identificar al actor;
- después identificar la regla o condición aplicable;
- después identificar la decisión;
- después identificar la consecuencia;
- y finalmente comprobar que el resultado sea trazable hasta el Reclamo y su contexto contractual.

Ante una ambigüedad, debe preferirse el significado definido por este dominio sobre significados genéricos de palabras como “reclamo”, “cobertura”, “aprobación”, “reembolso” o “pago”.

La pregunta central del dominio siempre es:

> **¿Existe, conforme al marco contractual, la evidencia y las reglas aplicables, un derecho de reembolso por el gasto reclamado; cuál es el importe reconocido y qué debe ocurrir para dar por cumplida y cerrada esa obligación?**

---

# Fin del contexto de negocio
