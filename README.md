Metodología para el seguimiento en profundidad de la accesibilidad del sitio web UNIR

1.	Consideraciones previas

Para la elaboración de esta metodología se han utilizado las siguientes herramientas:

•	Cyotek WebCopy v1.9.1.872   para la descarga del sitio web

•	Google Chrome v126.0.6478.62 para la revisión de los requisitos de accesibilidad y criterios de conformidad del sitio web, con las siguientes extensiones y marcadores instalados:

  o	Web Developer Toolbar

  o	HeadingsMap

  o	WCAG - Color contrast checker

  o	WAVE Evaluation Tool

  o	Bookmarklet «Text spacing»

  o	Validador automático de código del W3C

  o	Adobe Acrobat XI Pro para la revisión de la accesibilidad en el documento PDF

Se ha detectado que la página web de la UNIR utiliza el gestor de contenidos WordPress versión 5.9.x, cuyo lenguaje de programación es PHP (WhatCMS, (s.f.)). Dicho gestor de contenidos tiene varias vulnerabilidades por lo que se recomienda actualizarlo a la versión 6.5.x (WordPress, 2024) . Además de corregir vulnerabilidades y bugs, esta versión ha incluido varias mejoras  significativas en términos de accesibilidad en comparación con la versión 5.9.x (WordPress, 2024). Entre ellas cabe destacar:

•	Mejoras en la navegación por teclado y lectores de pantalla: 

  o	Se han corregido problemas que impedían el acceso a los submenús del administrador para usuarios de lectores de pantalla y aquellos que navegan por teclado. 
  
  o	Se ha mejorado el contraste de color en los estados de enfoque del administrador para asegurar una mejor visibilidad para todos los usuarios.
  
•	Editor de bloques:

  o	La lista de visualización de bloques ahora permite renombrar cualquier bloque, facilitando la organización y comprensión del contenido para usuarios con discapacidades cognitivas.
  
  o	Se ha mejorado la funcionalidad de arrastrar y soltar en la vista de lista, eliminando líneas visuales confusas y proporcionando una retroalimentación más clara sobre la ubicación del bloque.
  
•	Control de enlaces:

  o	Se ha mejorado el control de enlaces en el editor, haciendo que sea más fácil agregar y editar enlaces, incluyendo opciones avanzadas como la adición de «nofollow » sin necesidad de extensiones adicionales.
  
•	Preferencias del editor:

  o	El panel de preferencias ha sido rediseñado para incluir secciones de Apariencia y Accesibilidad, mejorando la categorización y accesibilidad de las opciones.
  
•	Biblioteca de fuentes:

  o	Introducción de una biblioteca de fuentes que permite gestionar y controlar la tipografía de forma más accesible y directa, sin necesidad de codificación adicional.
  
•	Vista y filtrado en el editor del sitio:

  o	Nuevas vistas y opciones de filtrado para páginas, patrones y plantillas, proporcionando una representación visual más clara y accesible de los componentes del sitio.
  
En los siguientes apartados se realizará un estudio de cada criterio de conformidad, mostrando las recomendaciones para mejorar la accesibilidad del sitio web de la UNIR, utilizando como base los problemas detectados en el informe de revisión de la accesibilidad (línea base). 
La numeración de los criterios de conformidad que se muestran en los siguientes apartados siguen la numeración marcada por la norma UNE-EN 301549:2022.

2.	Páginas web

La accesibilidad de las páginas web es un aspecto crucial que debe ser atendido para garantizar que todas las personas, independientemente de sus capacidades, puedan acceder a la información y a los servicios en línea de manera efectiva. A continuación, se presentan recomendaciones basadas en los criterios de conformidad de la norma UNE-EN 301549:2022 y por extensión a las WCAG (v2.1) para mejorar la accesibilidad de las páginas web de la UNIR. Siempre que sea posible, se incluirán ejemplos para mejorar su comprensión y aplicabilidad .
Dichas recomendaciones se han clasificado dependiendo el tipo de problema y dentro de cada tipo, del nivel de criticidad que las WCAG han asignado a cada uno de los criterios de conformidad. Por ello, y siguiendo este razonamiento, los primeros problemas que se deberían solventar son los que afectan a todas las páginas web de la UNIR (tipo Global) y que tengan un nivel de criticidad alto (nivel A de las WCAG). 

2.1.	Tipo de problema Global

Dentro de esta sección están los problemas relacionados con los criterios de conformidad que afectan a todas las páginas del sitio web de la UNIR. Por esta razón, deberían ser los primeros problemas en solucionarse.

2.1.1.	Nivel de criticidad Alta

9.1.1.1 Contenido no textual

El contenido no textual, como imágenes, iconos y gráficos, debe tener alternativas textuales adecuadas para que los usuarios que utilizan lectores de pantalla puedan entender la información que se les presenta. A continuación, se desarrollan más detalladamente las recomendaciones y ejemplos para asegurar la accesibilidad del contenido no textual:

•	Imágenes informativas. Las imágenes que contienen información relevante deben tener un atributo «alt» que describa claramente su contenido. Esta práctica es fundamental para que los usuarios de lectores de pantalla puedan comprender la información presentada a través de imágenes.

Ejemplo:

    <img src="logo_unir.png" alt="UNIR La Universidad en Internet">

•	Iconos funcionales. Los iconos que sirven como botones o enlaces deben tener un «alt» descriptivo que indique su función. Esto es especialmente importante para iconos que realizan acciones específicas o llevan a otras páginas.

Ejemplo:

    <img src="icono_whatsapp.png" alt="WhatsApp">
  
•	Imágenes decorativas. Las imágenes decorativas, que no aportan información esencial, deben tener un «alt» vacío (alt="") para que los lectores de pantalla las ignoren. Esto ayuda a evitar distracciones y asegura que los usuarios se centren en el contenido relevante.

Ejemplo:

    <img src="decorativa.png" alt="">
  
•	Diagramas y gráficos. Los diagramas y gráficos deben ir acompañados de descripciones textuales detalladas que expliquen la información representada. Estas descripciones pueden incluirse en el texto alternativo o en un párrafo adyacente.

Ejemplo:

    <img src="grafico_ventas.png" alt="Gráfico de ventas anuales mostrando un incremento del 20% en 2024">
 
•	Uso de «aria-label» y «aria-describedby». En casos donde el atributo «alt» no es suficiente para describir la función de un elemento, se pueden utilizar los atributos «aria-label» y «aria-describedby» para proporcionar descripciones adicionales.

Ejemplo:

    <button aria-label="Cerrar ventana">X</button>

En todo caso, todo el contenido no textual debe disponer del atributo «alt», aunque éste esté vacío.

9.1.3.1 Información y relaciones

La estructura de la información y las relaciones entre los elementos de la página web deben ser claras y lógicas. Esto facilita la navegación y la comprensión del contenido para todos los usuarios, incluidos aquellos que utilizan tecnologías de asistencia. A continuación, se detallan las mejores prácticas para estructurar la información de manera accesible:

•	Encabezados jerárquicos. Utilizar encabezados (\<h1>, \<h2>, etc.) de manera jerárquica y lógica es esencial para crear una estructura clara y navegable. Cada página debe tener un solo encabezado \<h1> que represente el título principal, seguido de \<h2>, \<h3>, y así sucesivamente, sin saltos de nivel.

Ejemplo:

    <h1>Título principal</h1>
    <h2>Subtítulo 1</h2>
    <h3>Subtítulo 1.1</h3>
    <h2>Subtítulo 2</h2>

•	Listas ordenadas y no ordenadas. Utilizar etiquetas de listas (\<ul>, \<ol>, \<li>) para agrupar elementos relacionados facilita la comprensión y la navegación. Las listas deben estar correctamente anidadas y utilizar la etiqueta apropiada según el contexto.

Ejemplo:

    <ul>
      <li>Grado en Ingeniería Informática</li>
      <li>Grado en Logística</li>
      <li>Grado en Ingeniería Química</li>
    </ul>

•	Tablas semánticas. Las tablas de datos deben utilizar etiquetas semánticas (\<table>, \<thead>, \<tbody>, \<tr>, \<th>, \<td>) para definir su estructura y facilitar la navegación. Los encabezados de las tablas (\<th>) deben estar claramente definidos y, si es necesario, asociados con las celdas correspondientes utilizando el atributo «scope».

Ejemplo:

    <table>
      <thead>
        <tr>
          <th scope="col">Año</th>
          <th scope="col">Ventas</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>2023</td>
          <td>100</td>
        </tr>
        <tr>
          <td>2024</td>
          <td>120</td>
        </tr>
      </tbody>
    </table>
	
Si la tabla es compleja, se debe asociar cada celda de datos con la celda de encabezados adecuada. Esto suele hacerse utilizando el atributo «scope» o el atributo «header». El atributo «header» permite realizar asociaciones más complejas permitiendo que una celda de datos disponga de varias celdas de encabezados. 

Ejemplo:

    <table border="3">
      <caption>CALIFICACIONES</caption>
      <thead>
          <tr>
              <th rowspan="2" id="f">Participación en los foros</th>
              <th colspan=“2" id="e">Ejercicios</th>
              <th colspan="3" id="t">Exámenes tipo test</th>
          </tr>
          <tr>
              <th id="e1" headers="e">1</th>
              <th id="e2" headers="e">2</th>
              <th id="t1" headers="t">1</th>
              <th id="t2" headers="t">2</th>
              <th id="tf" headers="t">Final</th>
          </tr>
      </thead>
      <tbody>
          <tr>
              <td headers="f">20%</td>
              <td headers="e e1">15%</td>
              <td headers="e e2">15%</td>
              <td headers="t t1">15%</td>
              <td headers="t t2">15%</td>
              <td headers="t tf">20%</td>
          </tr>
      </tbody>
    </table>

Hay que evitar el uso de tablas para maquetar la información, pero en caso de utilizarlas, no se deben emplear elementos o atributos propios de las tablas de datos (\<th>, \<caption>, «summary», «scope», «headers»).

•	Uso adecuado de «role» y «aria». Los atributos «role» y «aria» pueden utilizarse para proporcionar información adicional sobre la estructura y las relaciones entre los elementos. Por ejemplo, el atributo role="navigation" puede utilizarse para identificar una barra de navegación, y «aria-labelledby» para asociar una sección con su encabezado.
 
Ejemplo:

    <nav role="navigation" aria-labelledby="nav-heading">
      <h2 id="nav-heading">Menú de navegación</h2>
      <ul>
        <li><a href="#inicio">Inicio</a></li>
        <li><a href="#sobre">Sobre nosotros</a></li>
        <li><a href="#contacto">Contacto</a></li>
      </ul>
    </nav>

9.1.4.1 Uso del color

El color no debe ser el único medio para transmitir información. Es esencial complementar el uso del color con textos o indicadores adicionales para asegurar que la información sea accesible para todos los usuarios, incluidos aquellos con deficiencias visuales. A continuación, se presentan recomendaciones para el uso adecuado del color:

•	Indicadores textuales. Siempre que se utilice el color para destacar información, se debe proporcionar una descripción textual que explique su significado. Por ejemplo, en lugar de confiar únicamente en el color rojo para indicar un error, se puede añadir un texto que diga «Error: Este campo es obligatorio».

Ejemplo:

    <p><span style="color: red;">Error: </span>Este campo es obligatorio.</p>

•	Contraste de color. El contraste entre el texto y el fondo debe cumplir con los requisitos mínimos para asegurar la legibilidad. Se recomienda una relación de contraste de al menos 4.5:1 para texto normal y 3:1 para texto grande. Herramientas como el WCAG Color Contrast Checker pueden utilizarse para verificar el contraste.

Ejemplo de CSS:

    body {
        color: #000000;
        background-color: #ffffff;
    }

•	No confiar únicamente en el color. Evitar situaciones en las que el color sea el único medio para transmitir información. Por ejemplo, en gráficos y diagramas, utilizar patrones o texturas adicionales para diferenciar elementos.

9.2.1.1 Teclado

Todos los elementos interactivos de la página web deben ser accesibles mediante el teclado para garantizar que los usuarios que no pueden utilizar un ratón puedan navegar y utilizar la página web de manera efectiva. A continuación, se detallan las mejores prácticas para asegurar la accesibilidad mediante teclado:

•	Navegación con teclado. Asegurarse de que todos los enlaces, botones y campos de formulario sean accesibles y operables con el teclado. Esto se logra asegurando que estos elementos reciban el foco del teclado y puedan ser activados mediante la tecla «Enter» o la barra espaciadora.

Ejemplo:

    <a href="#contenido" tabindex="0">Ir al contenido</a>

•	Orden lógico del foco. Asegurarse de que el orden del foco siga una secuencia lógica e intuitiva. Esto se puede controlar utilizando el atributo «tabindex» para ajustar el orden de tabulación, aunque se recomienda mantener el orden natural del documento siempre que sea posible.

Ejemplo:

    <div tabindex="1">Primer elemento</div>
    <div tabindex="2">Segundo elemento</div>

9.2.4.1 Evitar bloques

Es importante que los usuarios puedan saltar bloques repetitivos, como menús de navegación, para acceder directamente al contenido principal. A continuación, se presentan recomendaciones para implementar esta funcionalidad:

•	Enlaces de salto. Colocar enlaces de salto al contenido principal al inicio de la página para permitir a los usuarios de teclado evitar bloques de contenido repetitivo.

Ejemplo:

    <a href="#maincontent" class="skip-link">Saltar al contenido principal</a>
    <div id="maincontent">...</div>

•	Estilo de los enlaces de salto. Asegurarse de que los enlaces de salto sean visibles cuando reciben el foco del teclado, pero que no interfieran con el diseño visual de la página.

Ejemplo de CSS:

    .skip-link {
        position: absolute;
        top: -40px;
        left: -40px;
        height: 1px;
        width: 1px;
        overflow: hidden;
    }
    .skip-link:focus {
        position: static;
        height: auto;
        width: auto;
        overflow: visible;
    }

9.2.4.3 Orden del foco

El orden del foco debe seguir una secuencia lógica e intuitiva para facilitar la navegación para los usuarios de teclado. A continuación, se presentan recomendaciones para gestionar el orden del foco:

•	Orden natural del documento. Siempre que sea posible, mantener el orden natural del documento asegura una navegación lógica. Los elementos interactivos deben estar dispuestos en el orden en que deben ser navegados.

•	Uso de «tabindex». Utilizar el atributo «tabindex» con cuidado para controlar el orden del foco. Evitar valores positivos de «tabindex» a menos que sea absolutamente necesario, ya que esto puede crear una experiencia de navegación confusa, además de que aumenta la complejidad de mantenimiento y rompe la navegación lógica.

Ejemplo:

    <div tabindex="1">Primer elemento</div>
    <div tabindex="2">Segundo elemento</div>

•	Pruebas de navegación. Realizar pruebas de navegación con el teclado, a través del tabulador, para asegurarse de que el orden del foco sea lógico y que todos los elementos interactivos sean accesibles. Esto puede incluir pruebas internas y la recopilación de comentarios de usuarios reales.

9.2.4.4 Propósito de los enlaces (en contexto)

El propósito de cada enlace debe ser claro a partir de su texto o contexto para que los usuarios sepan exactamente qué esperar al hacer clic en ellos. A continuación, se presentan recomendaciones para asegurar que los enlaces sean descriptivos:

•	Textos de enlace descriptivos. Utilizar textos de enlace claros y descriptivos que indiquen el propósito del enlace. Evitar textos genéricos como «haga clic aquí» o «más información».

Ejemplo:

    <a href="documento.pdf">Descargar informe de accesibilidad</a>

•	Contexto del enlace. Proporcionar contexto adicional alrededor del enlace si es necesario para aclarar su propósito. Esto puede incluir una breve descripción antes del enlace.

Ejemplo:

    <p>Para obtener más detalles sobre nuestras prácticas de accesibilidad, lea el <a href="politica_accesibilidad.pdf">documento completo sobre nuestra política de accesibilidad</a>.</p>

•	Uso de «aria-label». Utilizar el atributo «aria-label» para proporcionar descripciones adicionales cuando el texto del enlace por sí solo no es suficiente.

Ejemplo:

    <a href="documento.pdf" aria-label="Descargar informe de accesibilidad en PDF">Descargar</a>

9.2.4.7 Foco visible

Los elementos interactivos deben tener un indicador de foco visible para que los usuarios que navegan mediante teclado puedan ver claramente qué elemento está seleccionado. A continuación, se presentan recomendaciones para asegurar la visibilidad del foco:

•	Estilo de foco. Utilizar CSS para proporcionar un estilo claro y visible para el foco del teclado en todos los elementos interactivos. Esto puede incluir un borde, un cambio de color de fondo o una sombra. Esto se puede lograr utilizando el «pseudo-elemento :focus».

Ejemplo de CSS:

    a:focus, button:focus {
        outline: 3px solid #ff0000;
    }

•	Pruebas de visibilidad. Realizar pruebas de visibilidad del foco en diferentes navegadores y dispositivos para asegurarse de que el estilo de foco sea consistente y visible en todas las plataformas.

•	Personalización del foco. Permitir a los usuarios personalizar el estilo del foco mediante opciones de accesibilidad en la configuración del sitio web.

9.3.3.2 Etiquetas o instrucciones

Las etiquetas de los formularios deben estar claramente asociadas con sus campos correspondientes para asegurar que las tecnologías de asistencia puedan interpretar correctamente las relaciones. A continuación, se presentan recomendaciones para asegurar la claridad de las etiquetas y las instrucciones:

•	Asociación de etiquetas y campos. Utilizar el atributo «for» en las etiquetas y el atributo id en los campos de formulario para asegurar su asociación. Esto es fundamental para que los lectores de pantalla puedan identificar y describir correctamente cada campo.

Ejemplo:

    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre">

•	Instrucciones claras. Proporcionar instrucciones claras y concisas para cada campo de formulario, indicando qué información se espera y cualquier formato específico requerido.

Ejemplo:

    <label for="email">Correo electrónico:</label>
    <input type="email" id="email" name="email" placeholder="usuario@ejemplo.com">

•	Uso de «aria-describedby». Utilizar el atributo «aria-describedby» para proporcionar información adicional sobre los campos de formulario, como instrucciones o mensajes de error.

Ejemplo:

    <label for="password">Contraseña:</label>
    <input type="password" id="password" name="password" aria-describedby="passwordHelp">
    <small id="passwordHelp">La contraseña debe tener al menos 8 caracteres, incluyendo una letra mayúscula y un número.</small>

9.4.1.1 Procesamiento

El código HTML de la página debe ser procesable sin errores por las tecnologías de asistencia. A continuación, se presentan recomendaciones para asegurar que el código sea limpio y conforme a los estándares:

•	Validación del código. Utilizar herramientas de validación HTML para identificar y corregir errores en el código. W3C Markup Validation Service es una herramienta útil para verificar la conformidad del código HTML.

•	Uso adecuado de etiquetas. Asegurarse de que todas las etiquetas HTML estén correctamente cerradas y anidadas. Esto incluye etiquetas de apertura y cierre en el orden correcto y evitar etiquetas obsoletas.

•	Evitar elementos anidados incorrectamente. Asegurarse de que los elementos HTML no estén anidados de manera incorrecta, ya que esto puede causar problemas de procesamiento para las tecnologías de asistencia.


9.4.1.2 Nombre, función, valor

Los elementos interactivos deben tener atributos «aria» adecuados para que las tecnologías de asistencia puedan interpretarlos correctamente. A continuación, se presentan recomendaciones para asegurar el uso adecuado de los atributos «aria»:

•	Uso de «aria-label». Utilizar el atributo «aria-label» para proporcionar nombres claros y descriptivos a los elementos interactivos cuando el texto visible no es suficiente.

Ejemplo:

    <button aria-label="Enviar formulario">Enviar</button>

•	Uso de «aria-describedby». Utilizar el atributo «aria-describedby» para asociar elementos con descripciones adicionales que proporcionen contexto o instrucciones.

Ejemplo:

    <input type="text" id="nombre" aria-describedby="nombreHelp">
    <small id="nombreHelp">Ingrese su nombre completo.</small>

•	Uso de «role». Utilizar el atributo «role» para definir claramente la función de los elementos personalizados o aquellos que no tienen un equivalente HTML semántico directo.

Ejemplo:

    <div role="button" tabindex="0" aria-pressed="false">Botón personalizado</div>

4.2.1.2.	Nivel de criticidad Medio

9.1.4.3 Contraste (mínimo)

El contraste entre el texto y su fondo debe cumplir con los requisitos mínimos para asegurar que el contenido sea legible para todos los usuarios. A continuación, se presentan recomendaciones para asegurar un contraste adecuado:

•	Verificación del contraste. Utilizar herramientas de verificación de contraste, como el WCAG Color Contrast Checker, para asegurarse de que los colores utilizados en el texto y el fondo cumplan con los requisitos mínimos.

•	Ajuste de colores. Ajustar los colores del texto y el fondo para cumplir con la relación de contraste mínima de 4.5:1 para texto normal y 3:1 para texto grande.

Ejemplo de CSS:

    body {
        color: #000000;
        background-color: #ffffff;
    }

•	Uso de patrones y texturas. En lugar de depender únicamente del color, utilizar patrones y texturas adicionales para diferenciar elementos, especialmente en gráficos y diagramas.

9.1.4.12 Espaciado del texto

El espaciado del texto debe ser ajustable sin pérdida de contenido o funcionalidad. A continuación, se presentan recomendaciones para asegurar que el espaciado del texto sea accesible:

•	CSS para espaciado ajustable. Utilizar CSS para definir el espaciado del texto de manera que los usuarios puedan ajustarlo según sus necesidades sin que el contenido se desborde o se trunque.

Ejemplo de CSS:

    body {
        line-height: 1.5;
        letter-spacing: 0.05em;
        word-spacing: 0.1em;
    }

•	Herramientas de usuario. Proporcionar herramientas en la página que permitan a los usuarios ajustar el espaciado del texto según sus preferencias.

Ejemplo de herramienta:

    <button onclick="document.body.style.lineHeight = '1.5';">Espaciado normal</button>
    <button onclick="document.body.style.lineHeight = '2';">Espaciado amplio</button>

•	Pruebas de reajuste. Realizar pruebas para asegurarse de que el contenido sigue siendo legible y funcional cuando se ajusta el espaciado del texto mediante configuraciones de accesibilidad del navegador o del sistema operativo.

4.2.2.	Tipo de problema Individual 

A continuación, se mostrarán recomendaciones para mejorar la accesibilidad de los criterios de conformidad que afectan a una página web en concreto o a un conjunto reducido de ellas. Se incluirán ejemplos para mejorar su comprensión y aplicabilidad. Al igual que en el anterior apartado, los criterios de conformidad se han clasificado dependiendo del nivel de criticidad que las WCAG le hayan asignado.

4.2.1.3.	Nivel de criticidad Alta

9.2.2.2 Poner en pausa, detener, ocultar

El contenido en movimiento, parpadeante o que se desplaza debe tener controles para pausarlo, detenerlo u ocultarlo. Esto es crucial para evitar distracciones y problemas de accesibilidad para ciertos usuarios. A continuación, se presentan recomendaciones para manejar este tipo de contenido:

•	Controles de pausa y detención. Proporcionar controles visibles y accesibles para que los usuarios puedan pausar, detener u ocultar contenido en movimiento, como carruseles de imágenes o animaciones automáticas.

Ejemplo:

    <div>
        <marquee behavior="scroll" direction="left">Texto en movimiento</marquee>
        <button onclick="document.querySelector('marquee').stop();">Detener</button>
    </div>

•	Configuración de animaciones. Configurar las animaciones para que se detengan automáticamente después de un corto período, o permitir que los usuarios elijan si desean que las animaciones se reproduzcan.

Ejemplo de CSS:

    @keyframes example {
        from {background-color: red;}
        to {background-color: yellow;}
    }
    .animated {
        animation-name: example;
        animation-duration: 5s;
        animation-iteration-count: 1;
    }

9.3.1.1 Idioma de la página

El idioma principal de la página debe estar declarado en el atributo «lang» del elemento \<html> para que los lectores de pantalla puedan leer el contenido con la pronunciación correcta. A continuación, se presentan recomendaciones para declarar el idioma de la página:

•	Declaración del idioma principal. Asegurarse de que el atributo «lang» del elemento \<html> esté configurado correctamente para reflejar el idioma principal del contenido de la página.

Ejemplo:

    <html lang="es">

•	Compatibilidad con lectores de pantalla. Verificar que los lectores de pantalla y otros dispositivos de asistencia interpreten correctamente la configuración del idioma para proporcionar una experiencia de usuario óptima.

4.2.1.4.	Nivel de criticidad Media

9.1.3.5 Identificación del propósito de la entrada

El propósito de los campos de entrada en los formularios debe ser claro y estar bien definido para ayudar a los usuarios a completar los formularios de manera efectiva. A continuación, se presentan recomendaciones para identificar el propósito de los campos de entrada:

•	Etiquetas claras y descriptivas. Proporcionar etiquetas claras y descriptivas para cada campo de formulario para que los usuarios sepan qué información se requiere.

Ejemplo:

    <label for="email">Correo electrónico:</label>
    <input type="email" id="email" name="email">

•	Uso de atributos «autocomplete». Utilizar el atributo «autocomplete» para indicar el propósito de los campos de entrada y permitir que los navegadores sugieran valores automáticamente.

Ejemplo:

    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre" autocomplete="name">

9.1.4.10 Reajuste del texto

El espaciado del texto debe ser ajustable sin pérdida de contenido o funcionalidad. A continuación, se presentan recomendaciones para asegurar que el espaciado del texto sea accesible:

•	CSS para espaciado ajustable. Utilizar CSS para definir el espaciado del texto de manera que los usuarios puedan ajustarlo según sus necesidades sin que el contenido se desborde o se trunque.

Ejemplo de CSS:

    body {
        line-height: 1.5;
        letter-spacing: 0.05em;
        word-spacing: 0.1em;
    }

•	Herramientas de usuario. Proporcionar herramientas en la página que permitan a los usuarios ajustar el espaciado del texto según sus preferencias.

Ejemplo de herramienta:

    <button onclick="document.body.style.lineHeight = '1.5';">Espaciado normal</button>
    <button onclick="document.body.style.lineHeight = '2';">Espaciado amplio</button>

•	Pruebas de reajuste. Realizar pruebas para asegurarse de que el contenido sigue siendo legible y funcional cuando se ajusta el espaciado del texto mediante configuraciones de accesibilidad del navegador o del sistema operativo.

9.2.4.6 Encabezados y etiquetas

Los encabezados y las etiquetas deben ser claros y descriptivos para que los usuarios puedan comprender la estructura y el propósito del contenido de manera efectiva. A continuación, se presentan recomendaciones para asegurar la claridad de los encabezados y etiquetas:

•	Encabezados descriptivos. Utilizar encabezados que sean descriptivos y reflejen el contenido de la sección que representan.

Ejemplo:

    <h1>El cuerpo humano</h1>
    <h2>Anatomía</h2>
    <h3>Músculos</h3>
    <h2>Trastornos</h2>

•	Etiquetas descriptivas. Proporcionar etiquetas descriptivas para los campos de formulario y otros elementos interactivos para que los usuarios comprendan su propósito.

Ejemplo:

    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre">

•	Uso de «aria-label» y «aria-labelledby». Utilizar atributos «aria» para proporcionar descripciones adicionales y asegurar que las tecnologías de asistencia interpreten correctamente el propósito de los elementos.

Ejemplo:

    <button aria-labelledby="submit-label">Enviar</button>
    <span id="submit-label" class="sr-only">Enviar formulario</span>

9.3.1.2 Idioma de las partes

El idioma de cada parte de la página que difiere del idioma principal debe estar declarado para que los lectores de pantalla puedan cambiar la pronunciación según sea necesario. A continuación, se presentan recomendaciones para declarar el idioma de las partes:

•	Declaración del idioma de las partes. Utilizar el atributo «lang» para declarar el idioma de las partes del contenido que difieren del idioma principal de la página.

Ejemplo:

    <p lang="en">This paragraph is in English, <span lang=”es”>pero este es español</span></p>

•	Compatibilidad con lectores de pantalla. Verificar que los lectores de pantalla interpreten correctamente los cambios de idioma y ajusten la pronunciación en consecuencia.

9.3.3.3 Sugerencias ante errores

Proporcionar sugerencias claras y útiles para corregir los errores de entrada en los formularios ayuda a los usuarios a completar las tareas de manera eficiente. A continuación, se presentan recomendaciones para proporcionar sugerencias ante errores:

•	Mensajes de error claros. Proporcionar mensajes de error claros y específicos que indiquen el problema y cómo corregirlo. Evitar mensajes genéricos como «Entrada inválida».

Ejemplo:

    <label for="email">Correo electrónico:</label>
    <input type="email" id="email" name="email" aria-describedby="email-error">
    <span id="email-error" class="error">Ingrese una dirección de correo electrónico válida.</span>

•	Uso de «aria-invalid». Utilizar el atributo «aria-invalid» para indicar que un campo de formulario contiene un valor inválido y proporcionar sugerencias para corregirlo.

Ejemplo:

    <input type="email" id="email" name="email" aria-invalid="true">

•	Instrucciones adicionales. Proporcionar instrucciones adicionales cerca de los campos de formulario para ayudar a los usuarios a entender cómo completar correctamente la información.

Ejemplo:

    <label for="password">Contraseña:</label>
    <input type="password" id="password" name="password" aria-describedby="password-help">
    <small id="password-help">La contraseña debe tener al menos 8 caracteres, incluyendo una letra mayúscula y un número.</small>

9.4.1.3 Mensajes de estado

Los mensajes de estado deben ser programáticamente determinables mediante roles o atributos «aria» para que las tecnologías de asistencia puedan informar a los usuarios sobre los cambios en la interfaz. A continuación, se presentan recomendaciones para manejar los mensajes de estado:

•	Uso de «aria-live». Utilizar el atributo «aria-live» para marcar regiones de la página donde los mensajes de estado pueden cambiar dinámicamente, como notificaciones de éxito o error.

Ejemplo:

    <div aria-live="polite" id="status-message"></div>

•	Roles de alerta. Utilizar roles como «alert» o «status» para indicar que una región de la página contiene mensajes de estado importantes que deben ser anunciados inmediatamente por las tecnologías de asistencia.

Ejemplo:

    <div role="alert">Error: No se pudo enviar el formulario.</div>

•	Actualización de mensajes de estado. Asegurarse de que los mensajes de estado se actualicen correctamente en la interfaz y sean detectados por las tecnologías de asistencia.

Ejemplo de JavaScript:

    document.getElementById('status-message').innerText = 'El formulario se ha enviado correctamente.';

4.3.	Documentos no web

La accesibilidad de los documentos no web, como PDFs y otros formatos, es igualmente importante para asegurar que todos los usuarios puedan acceder y comprender la información presentada. A continuación, se presentan recomendaciones detalladas basadas en los criterios de conformidad de la norma UNE-EN 301549:2022 para mejorar la accesibilidad de estos documentos. Se incluirán ejemplos para mejorar su comprensión y aplicabilidad. Los criterios de conformidad se han clasificado dependiendo del nivel de criticidad que las WCAG le hayan asignado.

Hay que tener en cuenta que la mejor forma de corregir los problemas de accesibilidad que pueda tener un documento es a través del documento de origen, es decir, es más fácil corregir los problemas de accesibilidad en un documento de Microsoft Word o de LibreOffice Writer que hacerlo posteriormente sobre un documento en formato PDF (para ello será necesario disponer de Adobe Acrobat Pro). Si el documento de origen es accesible (se les ha añadido el texto alternativo a las imágenes informativas, se han utilizado correctamente los estilos y las listas, se ha comprobado el contraste del texto, los enlaces, etc.) el documento generado también lo será.
En el caso de Microsoft Word es muy importante que, a la hora de guardar el documento en formato PDF, se marquen las opciones «Crear marcadores» y «Etiquetas de la estructura del documento para accesibilidad».

4.3.1.	Nivel de criticidad Alta

10.1.1.1 Contenido no textual

Al igual que pasa con las páginas web, todos los contenidos no textuales en documentos, como imágenes y gráficos, deben tener descripciones alternativas que sean accesibles para los usuarios que utilizan lectores de pantalla. A continuación, se presentan recomendaciones y ejemplos para asegurar la accesibilidad del contenido no textual en documentos no web:

•	Descripciones alternativas en PDFs. Utilizar software como Adobe Acrobat para agregar texto alternativo a las imágenes en documentos PDF. Seleccionar la imagen, hacer clic con el botón derecho, seleccionar «Propiedades» y luego agregar el texto alternativo en la pestaña «Etiquetas».

•	Descripciones alternativas en Word. En Microsoft Word, agregar texto alternativo a las imágenes seleccionando la imagen, haciendo clic con el botón derecho, eligiendo «Formato de imagen» y luego ingresando el texto alternativo en la pestaña «Texto alternativo».

•	Gráficos y diagramas. Incluir descripciones textuales detalladas de los gráficos y diagramas en el cuerpo del documento para proporcionar contexto adicional y asegurar la comprensión.

101.3.1 Información y relaciones

La estructura del documento debe ser clara y utilizar etiquetas adecuadas para encabezados, listas y tablas. A continuación, se presentan recomendaciones para asegurar una estructura clara en los documentos no web:

•	Encabezados en PDFs. Utilizar estilos de encabezado para los títulos y subtítulos en documentos PDF. Esto se puede hacer en la mayoría de los editores de PDF, como Adobe Acrobat.

•	Encabezados en Word. Utilizar estilos de encabezado (Título 1, Título 2, etc.) en Microsoft Word para estructurar el documento de manera clara.

•	Listas y tablas: Utilizar etiquetas de listas  y tablas en los documentos para asegurar una estructura clara y navegable.

10.2.4.2 Titulado del documento

Cada documento debe tener un título descriptivo, programáticamente determinable. A continuación, se presentan recomendaciones para asegurar un titulado adecuado en documentos no web:

•	Título descriptivo en PDFs. Asegurarse de que los documentos PDF tengan un título claro y descriptivo que refleje el contenido del documento. Esto se puede configurar en las propiedades del documento en Adobe Acrobat.

•	Título descriptivo en Word. En Microsoft Word, asegurarse de que el título del documento esté claro y visible en la primera página del documento.

4.3.2.	Nivel de criticidad Media

10.1.4.3 Contraste (mínimo)

El contraste entre el texto y el fondo debe cumplir con los requisitos mínimos para asegurar que el contenido sea legible para todos los usuarios. A continuación, se presentan recomendaciones para asegurar un contraste adecuado en documentos no web:

•	Verificación del contraste en documentos. Utilizar herramientas de verificación de contraste para asegurarse de que los colores utilizados en el texto y el fondo cumplan con los requisitos mínimos. Esto es especialmente importante en documentos impresos y digitales.

•	Ejemplo de herramienta. Utilizar WCAG Color Contrast Checker para verificar los niveles de contraste en los documentos.

•	Ajuste de colores. Ajustar los colores del texto y el fondo para cumplir con la relación de contraste mínima de 4.5:1 para texto normal y 3:1 para texto grande.

•	Uso de patrones y texturas. En lugar de depender únicamente del color, utilizar patrones y texturas adicionales para diferenciar elementos, especialmente en gráficos y diagramas.

10.3.1.2 Idioma de las partes

El idioma de cada parte del documento que difiere del idioma principal debe estar declarado para que los lectores de pantalla puedan cambiar la pronunciación según sea necesario. A continuación, se presentan recomendaciones para declarar el idioma de las partes en documentos no web:

•	Declaración del idioma de las partes en PDFs. Utilizar las etiquetas de accesibilidad para poder seleccionar la palabra o palabras a etiquetar en otro idioma. Para ello, habrá que seleccionar el idioma del elemento desde las «Propiedades de objeto».

•	Declaración del idioma de las partes en Word. En Microsoft Word, utilizar la opción de idioma para configurar el idioma de las partes del contenido que difieren del idioma principal del documento.

4.4.	Implementación de mejoras

Para implementar estas mejoras en la accesibilidad, se recomienda seguir un enfoque sistemático y continuo:

1.	Auditoría inicial. Realizar una auditoría exhaustiva del sitio web y los documentos utilizando herramientas de accesibilidad para identificar problemas y áreas de mejora.

2.	Priorizar problemas. Clasificar los problemas identificados según tipo y su criticidad y abordar primero los de tipo «Global» y dentro ellos, los más críticos. Esto puede incluir problemas de contenido no textual, estructura de información, contraste de color y accesibilidad mediante teclado.

3.	Corrección y validación. Realizar las correcciones necesarias y validar cada cambio con herramientas de accesibilidad para asegurar la conformidad. Esto incluye pruebas de navegación con teclado, verificación de contraste y uso de lectores de pantalla.

4.	Documentación y formación. Documentar todas las mejoras realizadas y capacitar a los equipos de desarrollo y a los editores sobre las mejores prácticas en accesibilidad. Esto asegura que todos los miembros del equipo estén alineados y puedan mantener los estándares de accesibilidad en el futuro.

5.	Revisión continua. Establecer un proceso de revisión continua para mantener y mejorar la accesibilidad a lo largo del tiempo. Esto puede incluir auditorías periódicas, actualizaciones de contenido y retroalimentación de usuarios.

Siguiendo estas recomendaciones, se puede asegurar que el sitio web de la UNIR y sus documentos serán accesibles para todos los usuarios, cumpliendo con las normas y mejorando significativamente la experiencia del usuario.
