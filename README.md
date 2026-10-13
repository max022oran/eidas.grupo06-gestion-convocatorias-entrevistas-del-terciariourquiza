# Gestión de Convocatorias y Entrevistas del Terciario Urquiza — Grupo 6

> Materia: Diseño de Sistemas Web — Analista Funcional de Sistemas  
> Institución: Terciario Urquiza — Rosario  
> Docente: Pedernera Pablo  
> Cuatrimestre: 2.° 2026

## Integrantes

| Nombre | Apellido |
|--------|----------|
| Nahir | Algañaras |
| Ariadna | Bottiroli |
| Máximo | Oranges |
| Diego | Palma |
| Karen | Sánchez |

Datos completos en [integrantes.md](integrantes.md).

## Descripción del proyecto

En muchas instituciones y organizaciones donde se realizan convocatorias (laborales, educativas o de prácticas), el proceso de selección suele ser desordenado y poco eficiente. Los postulantes cargan sus datos, pero luego no existe un seguimiento claro del estado de su postulación, de las entrevistas ni de los resultados finales. Esto genera confusión tanto para los administradores como para los postulantes.

A partir de esta problemática, se propone un sistema web que permita gestionar convocatorias, postulaciones y entrevistas, centralizando toda la información en una única plataforma.

## Caso de estudio

**Bolsa de Trabajo del Terciario Urquiza.** Las empresas publican convocatorias laborales dirigidas a una o más carreras del terciario; los estudiantes y egresados se registran con su correo institucional, cargan su CV y se postulan; las empresas programan entrevistas y registran los resultados; y el administrador de la institución gestiona las cuentas, las carreras y los reportes.

### Actores

| Actor | Qué hace en el sistema |
|-------|------------------------|
| Usuario / Postulante | Se registra con su correo institucional, carga su CV, se postula y sigue el estado de sus postulaciones, entrevistas y resultados. |
| Empresa | Publica, edita y cierra sus convocatorias, ve a sus postulantes, programa entrevistas y carga resultados. Su cuenta la crea el administrador. |
| Administrador | Gestiona usuarios, empresas y carreras, consulta el padrón y los resultados, y genera reportes. |

### Módulos

| Módulo | Contenido |
|--------|-----------|
| Inicio | Acceso al sistema y resumen según el rol. |
| Usuario / Postulante | Registro, CV, gestión de cuentas y roles, alta de empresas y padrón. |
| Carreras | Carreras del terciario y su uso como filtro de convocatorias. |
| Convocatorias | Publicación, consulta, postulación y seguimiento de postulaciones. |
| Entrevistas | Programación, resultados y reportes. |

## Entregas

| Entrega | Descripción | Fecha | Estado |
|---------|-------------|-------|--------|
| EP-01 | Presentación preliminar: stakeholders y requisitos | 26/08/2026 | Entregada |
| EP-02 | Entrega intermedia: historias de usuario y casos de uso | 16/09/2026 | Entregada |
| Final | Versión definitiva: todas las secciones | | En curso |

Las devoluciones del docente de cada entrega están en la carpeta [`feedback/`](feedback/).

## Estructura del repositorio

```
/
├── README.md
├── integrantes.md
├── RECURSOS.md         ← prerrequisitos, cheatsheet de git y recursos
├── DoR.md              ← Definition of Ready: checklist del equipo + evaluación de 3 HU propias
├── slicing.md          ← épica partida en historias verticales (Partes A y B)
├── docs/
│   ├── requisitos.md           ← RF y RNF por módulo
│   ├── historias-de-usuario.md ← HU-01 a HU-20 con criterios de aceptación e INVEST
│   ├── casos-de-uso.md         ← CU-01 a CU-19
│   ├── er-modelo.md            ← entidades, atributos y decisiones de diseño
│   ├── diseño-ui.md            ← justificación de cada wireframe y accesibilidad
│   └── stakeholders.md
├── diagramas/
│   ├── casos-de-uso.puml
│   ├── er.puml
│   └── wireframes/             ← WF-01 a WF-20 en PNG
├── feedback/                   ← devoluciones del docente
└── cuestionario/
```

## Trazabilidad

Cada historia de usuario y cada caso de uso indica los requisitos que cubre (columna "Requisitos relacionados"), y cada wireframe de `diseño-ui.md` indica los casos de uso que representa. Así se puede seguir una funcionalidad desde el requisito hasta la pantalla.

## Instrucciones operativas

- Un integrante del grupo es responsable de subir los cambios al repositorio.
- Mantener los archivos en la carpeta correspondiente según la estructura indicada.
- Los diagramas se entregan en formato PlantUML (`.puml`). Se pueden visualizar en [plantuml.com](https://www.plantuml.com/plantuml/uml/).

