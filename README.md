# Repositorio Semántico de Trabajos de Grado, Prevención de Duplicidad Temática y Asistente de Estado del Arte
1. Resumen y Propósito del Proyecto
ITP-TesisRAG es una plataforma web orientada a la gestión y consulta inteligente de los trabajos de grado del Instituto Tecnológico del Putumayo (ITP).
El sistema permitirá almacenar trabajos de grado y realizar búsquedas mediante inteligencia artificial y búsqueda semántica, permitiendo encontrar documentos relacionados aunque no utilicen exactamente las mismas palabras.
Además, el sistema contará con un mecanismo para detectar similitudes entre temas de investigación, ayudando a identificar posibles duplicidades antes de registrar un nuevo proyecto de grado.
Finalmente, incorporará un asistente basado en RAG (Retrieval-Augmented Generation) que podrá consultar los trabajos almacenados para ayudar a los estudiantes en la construcción del estado del arte, proporcionando información relacionada con investigaciones anteriores.
________________________________________
2. Stack Tecnológico y Versiones
El proyecto estará dividido en Frontend, Backend y Base de Datos.
Frontend
•	React
•	Vite
Backend
•	Node.js
•	NestJS
Base de datos
•	PostgreSQL o MySQL
•	Extensión o servicio de almacenamiento vectorial para las representaciones semánticas.
Inteligencia Artificial
•	Modelo de lenguaje mediante API.
•	RAG para recuperar información relevante antes de generar una respuesta.
Herramientas
•	Antigravity IDE
•	Git
•	GitHub
•	Postman
•	Vercel para despliegue del Frontend, si aplica.
________________________________________
3. Arquitectura y Estructura de Carpetas
El proyecto utilizará una arquitectura modular, separando claramente la interfaz de usuario, la lógica del servidor y la persistencia de información.
Frontend: contiene la interfaz con la que interactúan estudiantes, docentes y administradores.
Backend: contiene la lógica del sistema, autenticación, gestión de trabajos de grado, búsquedas, generación de embeddings y funcionamiento del asistente RAG.
Base de datos: almacena usuarios, trabajos de grado, autores, categorías, documentos y datos necesarios para las búsquedas semánticas.
ProyectoDiplomado/
│
├── Frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── hooks/
│   │   └── assets/
│   ├── public/
│   ├── package.json
│   └── vite.config.js
│
├── Backend/
│   ├── src/
│   │   ├── modules/
│   │   │   ├── usuarios/
│   │   │   ├── trabajos/
│   │   │   ├── busqueda/
│   │   │   └── asistente/
│   │   ├── database/
│   │   ├── common/
│   │   └── main.ts
│   ├── package.json
│   └── .env
│
└── README.md
________________________________________
4. Comandos de Desarrollo y Verificación
Frontend
Instalar dependencias:
npm install
Ejecutar el servidor de desarrollo:
npm run dev
Construir el proyecto:
npm run build
Backend
Instalar dependencias:
npm install
Ejecutar en desarrollo:
npm run start:dev
Construir:
npm run build
Git
Consultar estado:
git status
Guardar cambios:
git add .
git commit -m "Descripción del cambio"
Subir cambios:
git push origin main
________________________________________
5. Estándares y Convenciones de Frontend
El Frontend deberá mantener una estructura organizada y componentes reutilizables.
Se utilizarán componentes independientes para elementos como:
•	Barra de navegación.
•	Inicio de sesión.
•	Registro de trabajos de grado.
•	Buscador semántico.
•	Visualización de resultados.
•	Perfil del usuario.
•	Panel administrativo.
•	Chat del asistente RAG.
Se recomienda utilizar nombres descriptivos para componentes y mantener separada la lógica de presentación de la lógica de comunicación con el Backend.
________________________________________
6. Estándares y Convenciones de Backend y API
El Backend utilizará una arquitectura modular basada en NestJS.
Las rutas de la API seguirán una estructura REST.
Ejemplos:
GET    
POST   
PUT    
DELETE 
________________________________________
7. Base de Datos y Persistencia
La base de datos almacenará la información relacionada con los trabajos de grado y sus autores.
Entre las principales entidades estarán:
•	Usuario
•	TrabajoGrado
•	Autor
•	ProgramaAcademico
•	Categoria
•	Documento
Un trabajo de grado podrá estar relacionado con uno o varios autores.
Por ejemplo, si un estudiante busca:
"Aplicaciones de inteligencia artificial para mejorar la educación"
________________________________________
8. Seguridad, Autenticación y Secretos
El sistema deberá implementar autenticación y autorización para controlar el acceso de los usuarios.
Se podrán manejar diferentes roles:
•	Estudiante
•	Docente
•	Administrador
Las contraseñas no deberán almacenarse directamente en la base de datos, sino utilizando mecanismos seguros de hash.
Las claves de APIs y demás credenciales deberán mantenerse en variables de entorno:
.env
Por ejemplo:
DATABASE_URL=...
API_KEY=...
JWT_SECRET=...
El archivo .env no deberá subirse al repositorio público.
________________________________________
9. Validaciones y Manejo de Errores
El sistema deberá validar la información enviada por los usuarios antes de almacenarla.
Por ejemplo, al registrar un trabajo de grado se deberá verificar:
•	Título obligatorio.
•	Autores válidos.
•	Programa académico.
•	Descripción o resumen.
•	Documento en formato permitido.
•	Información correctamente estructurada.
También se deberán manejar errores de forma uniforme.
________________________________________
10. Protocolo y Restricciones del Agente
El asistente de IA de ITP-TesisRAG deberá utilizar la información recuperada desde el repositorio para generar sus respuestas.
El agente deberá:
•	Consultar primero los documentos relevantes. 
•	Evitar inventar información que no se encuentre respaldada. 
•	Indicar cuando no exista suficiente información. 
•	Utilizar las fuentes recuperadas para construir las respuestas. 
•	Ayudar en la búsqueda y organización del estado del arte. 
•	Detectar trabajos potencialmente relacionados con un nuevo tema. 
•	No modificar información de la base de datos sin autorización. 
•	Mantener separadas las funciones de consulta y administración.

El sistema deberá priorizar la trazabilidad de la información, permitiendo conocer qué trabajos o documentos fueron utilizados como referencia para una respuesta del asistente.
________________________________________




ITP-HelpDesk TI
Mesa de Ayuda Inteligente con Diagnóstico Automático de Fallas de Hardware y Red en Aulas de Cómputo
1. Resumen y Propósito del Proyecto
ITP-HelpDesk TI es una plataforma web destinada a gestionar y solucionar de manera organizada los problemas tecnológicos que se presentan en las aulas de cómputo del Instituto Tecnológico del Putumayo (ITP).
El sistema permitirá que estudiantes, docentes y personal autorizado puedan reportar fallas de hardware, software o red, indicando el aula, equipo afectado y descripción del problema.
Además, contará con un módulo inteligente capaz de analizar la información del reporte y sugerir posibles causas y soluciones, ayudando al personal de soporte técnico a diagnosticar las fallas de manera más rápida.
El sistema también permitirá realizar seguimiento a los casos, asignar técnicos, cambiar estados y consultar el historial de problemas.
________________________________________
2. Stack Tecnológico y Versiones
El proyecto estará dividido principalmente en Frontend, Backend y Base de Datos.
Frontend
•	React
•	Vite
Backend
•	Node.js
•	NestJS
Base de datos
•	MySQL 
La base de datos almacenará información relacionada con usuarios, equipos, aulas, reportes, técnicos, diagnósticos y soluciones.
Inteligencia Artificial
•	API de un modelo de lenguaje.
•	Sistema de análisis de los reportes.
•	Base de conocimiento con problemas y soluciones frecuentes.
•	Asistente para sugerir posibles diagnósticos.
•	Antigravity
Herramientas
•	Antigravity IDE
•	Git
•	GitHub
•	Postman
•	Vercel para despliegue del Frontend, si aplica.
________________________________________
3. Arquitectura y Estructura de Carpetas
El proyecto utilizará una arquitectura modular que permitirá separar la interfaz de usuario, la lógica del servidor y la gestión de los datos.
ProyectoDiplomado/
│
├── Frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── hooks/
│   │   └── assets/
│   ├── public/
│   ├── package.json
│   └── vite.config.js
│
├── Backend/
│   ├── src/
│   │   ├── modules/
│   │   │   ├── usuarios/
│   │   │   ├── aulas/
│   │   │   ├── equipos/
│   │   │   ├── tickets/
│   │   │   ├── diagnostico/
│   │   │   └── soluciones/
│   │   ├── database/
│   │   ├── common/
│   │   └── main.ts
│   ├── package.json
│   └── .env
│
└── README.md
Responsabilidad de las carpetas
Frontend: contiene las interfaces utilizadas para crear reportes, consultar tickets y administrar los casos.
Backend: contiene la lógica para gestionar usuarios, equipos, aulas, tickets, diagnósticos y comunicación con la IA.
Base de datos: almacena la información de los equipos, reportes, usuarios, técnicos, diagnósticos y soluciones.
________________________________________
4. Comandos de Desarrollo y Verificación
Frontend
Instalar dependencias:
npm install
Ejecutar el proyecto:
npm run dev
Construir el proyecto:
npm run build
Backend
Instalar dependencias:
npm install
Ejecutar en modo desarrollo:
npm run start:dev
Construir:
npm run build
Git
Consultar los cambios:
git status
Agregar los archivos:
git add .
Crear un commit:
git commit -m "Implementa mesa de ayuda TI"
Subir los cambios:
git push origin main
________________________________________
5. Estándares y Convenciones de Frontend
El Frontend estará compuesto por componentes reutilizables y páginas independientes.
Entre las principales interfaces estarán:
•	Inicio de sesión.
•	Panel principal.
•	Crear reporte.
•	Lista de tickets.
•	Detalle del ticket.
•	Diagnóstico inteligente.
•	Gestión de equipos.
•	Gestión de aulas.
•	Panel del técnico.
•	Panel administrativo.
•	Historial de fallas.
La interfaz deberá mantener un diseño sencillo para que los usuarios puedan reportar una falla rápidamente.
________________________________________
6. Estándares y Convenciones de Backend y API
El Backend utilizará una arquitectura modular basada en NestJS.
Las rutas principales podrán ser:
Usuarios
GET    
POST   
PUT   
DELETE 
El endpoint de diagnóstico recibirá la descripción de la falla y podrá devolver posibles causas y recomendaciones.
________________________________________
7. Base de Datos y Persistencia
La base de datos almacenará toda la información necesaria para administrar la mesa de ayuda.
Las principales entidades podrían ser:
•	Usuario
•	Rol
•	Aula
•	Equipo
•	Ticket
•	Técnico
•	Diagnóstico
•	Solución
•	HistorialTicket
Por ejemplo, un aula puede tener varios equipos:
AULA 01
│
├── PC-001
├── PC-002
├── PC-003
├── PC-004
└── PC-005
Cada equipo puede tener múltiples reportes durante su vida útil.
Los tickets podrán manejar diferentes estados:
Pendiente
    ↓
Asignado
    ↓
En revisión
    ↓
Solucionado
    ↓
Cerrado
________________________________________
8. Seguridad, Autenticación y Secretos
El sistema contará con autenticación para controlar el acceso de los diferentes usuarios.
Se podrán definir roles como:
•	Estudiante
•	Docente
•	Técnico TI
•	Administrador
Cada rol tendrá diferentes permisos.
Por ejemplo:
Estudiante/Docente:
•	Crear reportes.
•	Consultar sus reportes.
•	Ver el estado de sus tickets.
Técnico:
•	Consultar tickets asignados.
•	Registrar diagnósticos.
•	Registrar soluciones.
•	Cambiar estados.
Administrador:
•	Gestionar usuarios.
•	Gestionar aulas.
•	Gestionar equipos.
•	Consultar estadísticas.
Las claves y credenciales de servicios externos deberán almacenarse mediante variables de entorno:
.env
Ejemplo:
DATABASE_URL=...
API_KEY=...
JWT_SECRET=...
El archivo .env deberá estar incluido en .gitignore para evitar subir información privada al repositorio.
________________________________________
9. Validaciones y Manejo de Errores
El sistema deberá validar los datos antes de crear un reporte.
Por ejemplo:
•	El aula debe existir.
•	El equipo debe estar registrado.
•	La descripción de la falla debe ser obligatoria.
•	El usuario debe estar autenticado.
•	El ticket debe tener un estado válido.
También se deberán controlar errores relacionados con:
•	Equipo inexistente.
•	Aula inexistente.
•	Usuario no autorizado.
•	Error de conexión con la base de datos.
•	Error al comunicarse con el servicio de IA.
Ejemplo de respuesta:
{
  "statusCode": 400,
  "message": "La descripción de la falla es obligatoria"
}
________________________________________
10. Protocolo y Restricciones del Agente
El asistente inteligente tendrá como función principal ayudar a identificar posibles causas de las fallas reportadas.
Por ejemplo, si un usuario registra:
"El computador enciende pero no muestra imagen."
El sistema podría analizar el reporte y sugerir posibles causas como:
•	Problema con el cable de video.
•	Problema con el monitor.
•	Problema de conexión del equipo.
•	Posible falla del hardware.
El agente deberá:
•	Analizar la información proporcionada en el ticket.
•	Consultar la base de conocimiento disponible.
•	Proponer posibles causas.
•	Sugerir procedimientos básicos de diagnóstico.
•	Indicar cuando no tenga suficiente información.
•	No afirmar que un diagnóstico es definitivo cuando solo es una sugerencia.
•	Registrar el diagnóstico generado para facilitar el seguimiento.
•	No modificar tickets automáticamente sin autorización.
El diagnóstico generado por IA deberá ser considerado una recomendación para el técnico, no un reemplazo de la revisión técnica.
________________________________________
📌 Funcionamiento general
              USUARIO
                 │
                 ▼
        ┌─────────────────┐
        │ Crear reporte   │
        │ de una falla    │
        └────────┬────────┘
                 │
                 ▼
        ┌─────────────────┐
        │     TICKET      │
        └────────┬────────┘
                 │
                 ▼
        ┌─────────────────┐
        │ Diagnóstico IA  │
        └────────┬────────┘
                 │
          ┌──────┴──────┐
          ▼             ▼
     Posibles       Soluciones
      causas        sugeridas
          │             │
          └──────┬──────┘
                 ▼
        ┌─────────────────┐
        │   Técnico TI    │
        └────────┬────────┘
                 │
                 ▼
        ┌─────────────────┐
        │ Reparación /    │
        │ solución        │
        └────────┬────────┘
                 │
                 ▼
             CERRADO

