---
title: Desplegar GitHub Advanced Security en tu empresa
intro: Aprende cómo planear, preparar e implementar un acercamiento gradual para implementar {% data variables.product.prodname_GH_advanced_security %} (GHAS) en tu emrpesa.
product: '{% data reusables.gated-features.advanced-security %}'
redirect_from:
- /admin/advanced-security/deploying-github-advanced-security-in-your-enterprise
miniTocMaxHeadingLevel: 3
versions:
  ghes: '*'
  ghec: '*'
type: how_to
topics:
- Advanced Security
- Code scanning
- Enterprise
- Security
ms.openlocfilehash: 7990891fd4b90127ae5f32aa262d6c096d23acab
ms.sourcegitcommit: dc42bb4a4826b414751ffa9eed38962c3e3fea8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2022
ms.locfileid: "147060758"
---
## <a name="overview-of-the-deployment-process"></a>Resumen del proceso de despliegue

{% data reusables.security.overview-of-phased-approach-for-ghas-rollout %}

Para obtener un resumen de alto nivel de estas distintas fases, vea "[Información general sobre la implementación de {% data variables.product.prodname_GH_advanced_security %}](/admin/advanced-security/overview-of-github-advanced-security-deployment)".

Antes de iniciar la implementación, se recomienda revisar los requisitos previos a fin de instalar GHAS y los procedimientos recomendados para la implementación de GHAS en "[Información general sobre la implementación de {% data variables.product.prodname_GH_advanced_security %}](/admin/advanced-security/overview-of-github-advanced-security-deployment)".

## <a name="-octicon-milestone-aria-labelthe-milestone-icon--phase-0-planning--kickoff"></a>{% octicon "milestone" aria-label="The milestone icon" %} Fase 0: Planificación e inicio

{% note %}

{% octicon "clock" aria-label="Clock" %} **Tiempo estimado**: estimamos que la fase 0 puede durar aproximadamente entre 1 y 4 semanas. Esta rango de tiempo puede variar dependiendo de las necesidades de tu lanzamiento y de las aprobaciones necesarias que pudiera requerir tu compañía en el plan de despliegue.

{% endnote %}

La meta de la fase de planeación e inicio es garantizar que todo tu personal, procesos y tecnologías estén configuradas y listas para implementar la GHAS.

Para ayudarte a lograr una compra de patrocinio de tu patrocinador ejecutivo, te recomendamos preparar y alinear un plan de implementación y metas antes de lanzar la GHAS en tu empresa.

Como parte de una estrategia de implementación gradual, te recomendamos identificar los impactos altos y equipos o aplicaciones críticos que deberían participar para unirse a la GHAS antes del resto de tu empresa.

Si un lanzamiento por fases no es adecuado para su empresa, puede ir directamente a la [fase de proyecto piloto](#--phase-1-pilot-projects).

Si estás trabajando con {% data variables.product.prodname_professional_services %}, durante esta fase, también establecerás un plan para que tus equipos trabajen en conjunto durante el proceso de implementación y despliegue. El equipo de {% data variables.product.prodname_professional_services_team %} puede apoyarte con la creación del plan de implementación gradual y con las metas de acuerdo a tus necesidades.

### <a name="step-1-kickoff-meeting-with--data-variablesproductprodname_professional_services--optional"></a>Paso 1: Junta inicial con {% data variables.product.prodname_professional_services %} (opcional)

Si te diste de alta para los {% data variables.product.prodname_professional_services %}, comenzarás el proceso de implementación y despliegue reuniéndote con tu representante de servicios.

Si aún no te registras para los {% data variables.product.prodname_professional_services %}, puedes continuar con el paso siguiente.

La meta de esta junta es alinear a los dos equipos con la información necesaria para comenzar a crear un plan de implementación y despliegue que funcione de la mejor forma para tu compañía. Como preparación para esta junta, creamos una encuesta que nos ayudará a estar mejor preparados para el debate. Tu representante de servicios te enviará esta encuesta.

Para ayudarte a prepararte para esta junta inicial, revisa estos temas.

-  Alinearte con respecto a cómo {% data variables.product.prodname_professional_services %} y tu compañía podrían trabajar mejor juntos
  - Configurar las expectativas de cómo utilizar las horas/días de servicio compradas de una forma mejor
  - Planes de comunicación/frecuencia de las juntas
  - Roles y responsabilidades
- Revisión de cómo funciona la GHAS con el Ciclo de Vida de Desarrollo de Software (SDLC). Tu representante de {% data variables.product.prodname_professional_services %} te explicará cómo funciona la GHAS.
- Revisión de las mejores prácticas para desplegar la GHAS. Esto se ofrece como un recordatorio si tu equipo así lo desea o si tu empresa no participó en el ejercicio de la prueba de concepto (POC). Esta revisión incluye un debate de tu programa de seguridad de aplicaciones y de su nivel de madurez contra algo como el modelo de madurez de DevSecOps.
-  Alineamiento con los siguientes pasos para tu despliegue de la GHAS. Tu representante de los {% data variables.product.prodname_professional_services %} describirá tus siguientes pasos y el apoyo que puedes esperar de tu sociedad.

Para ayudarte a planear tu estrategia de implementación, también puedes esperar debatir estas preguntas:
  - ¿Cuántos equipos se habilitarán?
  - ¿Cuál es la anatomía de los repositorios de los equipos? (Oferta tecnológica, herramientas actuales, etc).
    - Algunas de estas ya se cubrieron durante el ejercicio de prueba de concepto en caso de que tu compañía haya participado en él. De lo contrario, este es un momento crucial para debatirlo.
   - ¿Qué nivel de adopción esperamos para que sea orgánico, asistido o inorgánico?
   - ¿Cómo se ve la adopción asistida desde una perspectiva de documentación y asignación de recursos?
   - ¿Cómo administrarás la adopción inorgánica en la práctica? (Por ejemplo, utilizando el requerimiento de políticas o los flujos de trabajo administrados de forma central).

### <a name="step-2-internal-kickoff-at-your-company"></a>Paso 2: Inicio interno en tu compañía

Ya sea que tu compañía elija o no el trabajar con los {% data variables.product.prodname_professional_services %}, siempre te recomendamos que tengas tu junta de inicio para alinearte con tu(s) propio(s) equipo(s).

Durante esta junta de inicio, es importante asegurarse de que hay un entendimiento claro de las metas, expectativas y de que exista un plan para seguir con la implementación y el despliegue.

Adicionalmente, este es buen momento para comenzar a pensar en la capacitación y preparaciones para que tu equipo se asegure de que tiene las herramientas y experiencia correctas para apoyar la implementación y el despliegue de la GHAS.

#### <a name="topics-for-your-internal-kickoff-meeting"></a>Temas para tu junta de inicio interna

Te recomendamos que cubras estos temas en la junta interna de inicio en tu compañía en caso de que no lo hayas hecho ya con el mismo grupo en la junta de inicio que tuviste con los {% data variables.product.prodname_professional_services %}.

- ¿Cuáles son tus métricas de éxito de negocios y cómo planeas medirlas y reportarlas?
  - Si estas no se han identificado, por favor, defínelas. Si ya se definieron, comunícalas y habla sobre cómo planeas proporcionar las actualizaciones del progreso impulsado por los datos.
- Revise cómo funciona GHAS en el SDLC (Ciclo de vida de desarrollo de software) y cómo se espera que este funcione en su compañía.
- Revisa las mejores prácticas en caso de que tu compañía no haya participado en el ejercicio de prueba de concepto (o haz una recapitulación en caso de que tu equipo considere que lo necesita en esta revisión).
  - ¿Cómo es que este programa se compara o contrasta con tu Programa de Seguridad de Aplicaciones?
- Debata y acuerde cómo trabajará su equipo interno de la mejor forma durante el lanzamiento y la implementación.
  - Alinéate con los planes de comunicación y con la frecuencia de las juntas para tu equipo interno
  - Revisa las tareas para completar la implementación y el despliegue definiendo los roles y responsabilidades. Ya describimos la mayoría de las tareas en este artículo, pero tu compañía podría requerir algunas adicionales que no se hayan incluido.
  - Considera establecer un "Programa de campeones" para la habilitación gradual
  - Comienza a debatir los tiempos para completar las tareas
- Comienza a trabajar en los enfoques ideales de implementación que serían los mejores para tu compañía. Esto incluirá el entendimiento de algunos elementos importantes:
  - ¿Cuántos equipos se habilitarán? Parte de esto podría haberse cubierto ya durante el ejercicio de POC (Prueba de Concepto) en caso de que tu compañía haya participado en él. De lo contrario, este es un momento crucial para debatirlo.
  - De las aplicaciones que se identificaron para la implementación inicial, ¿cuántas se crearon en una tecnología compatible con la GHAS?
  - ¿Cuánta preparación organizacional se requiere? Para más información, vea "[Fase 2](#--phase-2-organizational-buy-in--rollout-preparation)".

### <a name="step-3-prepare-your-rollout--implementation-plan-and-goals"></a>Paso 3: Preparar el plan y los objetivos del lanzamiento y la implementación

Antes de seguir con el(los) proyecto(s) piloto para la primera fase de la implementación, es crucial garantizar que hay un plan de implementación y metas de negocio establecidos para el cómo quiere proceder tu compañía.

Si estás trabajando con los {% data variables.product.prodname_professional_services %}, estos pueden jugar un rol significativo en la creación de este plan.

Si estás trabajando de forma independiente, esta sección describe algunas cosas que debes asegurar se incluyan en tu plan conforme te preparas para seguir con él.

Planes para cambios de proceso (en caso de necesitarse) y capacitación para los miembros del equipo conforme se necesiten:
  - Tareas de equipo documentadas para los roles y responsabilidades. Para obtener más información sobre los permisos necesarios para cada característica, vea "[Roles de repositorio para una organización](/organizations/managing-access-to-your-organizations-repositories/repository-roles-for-an-organization#access-requirements-for-security-features)".
  - Plan documentado de tareas y líneas de tiempo/marcos de tiempo en donde son posibles. Esto debería incluir cambios de infraestructura, cambios de proceso/capacitación y todas las fases posteriores a la habilitación de GHAS, permitiendo marcos de trabajo para las remediaciones y ajustes de configuración conforme sea necesario. Para obtener más información, vea debajo "[Fase 1: Proyectos piloto](/admin/advanced-security/deploying-github-advanced-security-in-your-enterprise#--phase-1-pilot-projects)".
  - Plan priorizado para el cual los equipos/proyectos tendrán habilitada la GHAS primero y planes posteriores para los cuales los proyectos/equipos vendrán en las siguientes fases
  - Métricas de éxito con base en las metas de negocio. Este será un punto de referencia crucial que seguirá al (los) proyecto(s) piloto para obtener participación para la implementación completa.

{% note %}

**Nota**: Para garantizar que la concientización, adopción y aceptación venga de todos los grupos de su compañía, es importante tener expectativas realistas sobre el tiempo e impacto de la implementación en la infraestructura, procesos y flujos de trabajo de desarrollo diarios de esta. Para obtener una implementación más fácil y exitosa, asegúrate de que tus equipos de desarrollo y seguridad entiendan el impacto de la GHAS.

{% endnote %}

{% ifversion ghes %}

En el caso de los clientes de {% data variables.product.prodname_ghe_server %}, para ayudar a asegurarte de que tu instancia es compatible con la implementación y despliegue de la GHAS, revisa lo siguiente:

- Si bien no es necesario mejorar a GHES 3.0, debes mejorar a esta versión o a una superior para beneficiarte de las combinaciones de características, tales como el escaneo de código y las {% data variables.product.prodname_actions %}. Para más información, vea "[Actualización de {% data variables.product.prodname_ghe_server %}](/admin/enterprise-management/updating-the-virtual-machine-and-physical-resources/upgrading-github-enterprise-server)".

- En una configuración de alta disponibilidad, un aparato secundario {% data variables.product.prodname_ghe_server %} totalmente redundante se mantiene en sincronización con el aparato principal mediante la replicación de todos los almacenes de datos importantes. Para obtener más información sobre cómo configurar la alta disponibilidad, vea "[Configuración de alta disponibilidad](/admin/enterprise-management/configuring-high-availability)".

- Para ayudar a apoyar con cualquier debate con respecto a los cambios potenciales a la configuración de tu compañía, puedes revisar el resumen de sistema de {% data variables.product.prodname_ghe_server %}. Para más información, vea "[Información general del sistema](/admin/overview/system-overview)".

{% endif %}

### <a name="step-4-establish-a-baseline-of-organizational-insights"></a>Paso 4: Establecer una línea base para las perspectivas organizacionales

Conforme tu compañía se prepara para comenzar tu(s) proyecto(s) piloto, es crucial asegurarse de que estableciste una línea base para donde tu empresa se encuentra actualmente y de que tienes métricas de éxito claras con las cuales medirás tu(s) proyecto(s) piloto.

Es probable que su compañía tenga objetivos de negocio clave que necesitarán medirse, pero hay otras métricas que podemos identificar para ayudarle a medir el éxito de su piloto.

Como punto de partida, algunas de estas métricas podrían incluir:
  - El tiempo promedio para remediar las vulnerabilidades de GHAS frente a las herramientas y prácticas anteriores que utilizaron los proyectos pilotos o los equipos.
  - Los hallazgos de la integración del escaneo de código para las X aplicaciones más críticas.
  - La cantidad de aplicaciones que tienen SAST (Pruebas de seguridad de aplicación estática) integrado contra antes de la participación.

Si participaste en el ejercicio de POC antes de comprar la GHAS, estos objetivos podrían parecerte familiares. Estos criterios de éxito incluyen diversos objetivos para seguir los roles de alto nivel:
  - Equipos de administración y de implementación
  - Seguridad / CISO (Director de Seguridad Informática)
  - Equipos de desarrollo de aplicaciones

Si quiere ir un paso más allá, puede ver cómo utilizar el Modelo de Madurez de DevSecOps de OWASP (DSOMM) para trabajar y llegar al nivel de madurez 1. Existen cuatro criterios de evaluación principales en el DSOMM:

- **Profundidad estática**: nivel de exhaustividad del examen de código estático que realiza en la canalización de CI de AppSec.
- **Profundidad dinámica**: nivel de exhaustividad del examen dinámico que se ejecuta en la canalización de CI de AppSec.
- **Intensidad**: la frecuencia de programación de los exámenes de seguridad que se ejecutan en la canalización de CI de AppSec.
- **Consolidación**: el flujo de trabajo de corrección para controlar los resultados y la integridad del proceso.

Para obtener más información sobre este enfoque y cómo implementarlo en GHAS, puede descargar las notas del producto "[Alcance de la madurez en DevSecOps con GitHub](https://resources.github.com/whitepapers/achieving-devsecops-maturity-github/)".

Con base en las metas ampliadas y niveles de madurez actuales de DevSecOps de tu compañía, podemos ayudarte a determinar la mejor forma de medir el progreso y éxito de tu piloto.

## <a name="-octicon-milestone-aria-labelthe-milestone-icon---phase-1-pilot-projects"></a>{% octicon "milestone" aria-label="The milestone icon" %}  Fase1: Proyecto(s) piloto

{% note %}

{% octicon "clock" aria-label="Clock" %} **Tiempo estimado**: estimamos que la fase 1 puede durar aproximadamente entre 2 semanas y más de 3 meses. Este rango puede variar ampliamente dependiendo de la complejidad de los sistemas o infraestructura de tu compañía, los procesos internos para administrar/aprobar estos cambios, así como de si se necesitan cambios más grandes de procesos organizacionales para avanzar con la GHAS.

{% endnote %}

Para comenzar a habilitar la GHAS en toda su compañía, le recomendamos comenzar con algunos proyectos o equipos de alto impacto para llevar a cabo un lanzamiento inicial piloto. Esto permitirá que un grupo inicial dentro de su compañía se familiarice con GHAS y cree bases sólidas en ella antes de implementarla en el resto de su compañía.

Antes de que comiences tu(s) proyecto(s) piloto, te recomendamos que programes juntas de control para tu(s) equipo(s), tales como una junta inicial, una revisión de punto medio y una sesión de conclusión cuando se complete el piloto. Estas juntas de control te ayudarán a realizar los ajustes conforme sean necesarios y garantizar así que tu(s) equipo(s) está(n) listo(s) y cuenta(n) con el apoyo para completar el piloto con éxito.

Estos pasos te ayudarán a habilitar la GHAS en tu empresa, comenzar a utilizar sus características y revisar tus resultados.

Si estás trabajando con los {% data variables.product.prodname_professional_services %}, estos pueden proporcionarte ayuda adicional en este proceso mediante sesiones de integración, talleres de GHAS y solución de problemas, conforme lo requieras.

### <a name="step-1-ghas-set-up--installation"></a>Paso 1: Instalar y configurar GHAS

{% ifversion ghes %}

Si aún no ha habilitado GHAS para la instancia de {% data variables.product.prodname_ghe_server %}, vea "[Habilitación de seguridad avanzada de GitHub para su empresa](/admin/advanced-security/enabling-github-advanced-security-for-your-enterprise)".

{% endif %}

Necesitas habilitar la GHAS para cada proyecto piloto, ya sea habilitando la característica de la GHAS en cada repositorio o en todos ellos en todas las organizaciones que participen en el proyecto. Para más información, vea "[Administración de la configuración de seguridad y análisis del repositorio](/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-security-and-analysis-settings-for-your-repository)" o "[Administración de la configuración de seguridad y análisis para la organización](/organizations/keeping-your-organization-secure/managing-security-and-analysis-settings-for-your-organization)".

La mayoría de las configuraciones e instalaciones de la GHAS se centran en habilitar y configurar el escaneo de código en tu empresa y en tus repositorios.

El escaneo de código te permite analizar el código en un repositorio de {% data variables.product.prodname_dotcom %} para encontrar las vulnerabilidades de seguridad y los errores de código. El escaneo de código puede utilizarse para encontrar, clasificar y priorizar las correcciones de los problemas existentes en tu código, así como para prevenir que los desarrolladores introduzcan problemas nuevos que de otra forma pudiesen llegar al ambiente productivo. Para obtener más información, vea "[Acerca de los análisis de código](/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning)".

### <a name="step-2-set-up--data-variablesproductprodname_code_scanning_capc-"></a>Paso 2: Configuración de {% data variables.product.prodname_code_scanning_capc %}

{% ifversion ghes %}

Para habilitar {% data variables.product.prodname_code_scanning %} en la instancia de {% data variables.product.prodname_ghe_server %}, vea "[Configuración del examen de código para el dispositivo](/admin/advanced-security/configuring-code-scanning-for-your-appliance)".

{% endif %}

Para configurar el examen de código, debe decidir si ejecutará el análisis de código con [{% data variables.product.prodname_actions %}](#using-github-actions-for-code-scanning) o con su propio [sistema de CI de terceros](#using-a-third-party-ci-system-with-the-codeql-cli-for-code-scanning).

#### <a name="using--data-variablesproductprodname_actions--for--data-variablesproductprodname_code_scanning-"></a>Utilizar las {% data variables.product.prodname_actions %} para el {% data variables.product.prodname_code_scanning %}

{% ifversion ghes %}

Para configurar el examen de código con {% data variables.product.prodname_actions %} para {% data variables.product.prodname_ghe_server %}, necesitará aprovisionar uno o varios ejecutores de {% data variables.product.prodname_actions %} en su entorno. Para obtener más información, vea "[Configuración de un ejecutor autohospedado](/admin/advanced-security/configuring-code-scanning-for-your-appliance#running-code-scanning-using-github-actions)".

{% endif %}

En el caso de {% data variables.product.prodname_ghe_cloud %}, puede empezar a crear un flujo de trabajo de {% data variables.product.prodname_actions %} mediante la [acción CodeQL](https://github.com/github/codeql-action/) para ejecutar el examen de código en un repositorio. {% data variables.product.prodname_code_scanning_capc %} usa [ejecutores hospedados en GitHub](/actions/using-github-hosted-runners/about-github-hosted-runners) de manera predeterminada, pero esto se puede personalizar si planea hospedar su propio ejecutor con sus propias especificaciones de hardware. Para más información, consulte [Seguridad del ejecutor autohospedado con repositorios públicos](/actions/hosting-your-own-runners).

Para obtener más información sobre las {% data variables.product.prodname_actions %}, consulta las siguientes secciones:
  - "[Más información sobre las Acciones de GitHub](/actions/learn-github-actions)"
  - "[Descripción de las Acciones de GitHub](/actions/learn-github-actions/understanding-github-actions)"
  - "[Eventos que desencadenan flujos de trabajo](/actions/learn-github-actions/events-that-trigger-workflows)"
  - "[Hoja de datos de patrones de filtro](/actions/learn-github-actions/workflow-syntax-for-github-actions#filter-pattern-cheat-sheet)"

#### <a name="using-a-third-party-ci-system-with-the-codeql-cli-for--data-variablesproductprodname_code_scanning-"></a>Utilizar un sistema de IC de terceros con el CLI de CodeQL para el {% data variables.product.prodname_code_scanning %}

Si no estás utilizando {% data variables.product.prodname_actions %} y tienes tu propio sistema de integración continua, puedes utilizar el CLI de CodeQL para realizar el escaneo de código de CodeQL en un sistema de IC de terceros.

Para más información, consulte:
  - "[Acerca del análisis de código de CodeQL en el sistema de CI](/code-security/code-scanning/using-codeql-code-scanning-with-your-existing-ci-system/about-codeql-code-scanning-in-your-ci-system)"

### <a name="step-3-enable--data-variablesproductprodname_code_scanning_capc--in-repositories"></a>Paso 3: Habilitar el {% data variables.product.prodname_code_scanning_capc %} en los repositorios

Si estás utilizando un enfoque gradual para implementar la GHAS, te recomendamos habilitar el {% data variables.product.prodname_code_scanning %} de repositorio en repositorio como parte de tu plan de implementación. Para obtener más información, vea "[Configuración del examen de código para un repositorio](/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/setting-up-code-scanning-for-a-repository)".

Si no estás planeando un enfoque de implementación gradual y quieres habilitar el escaneo de código para muchos repositorios, puede que quieras hacer un script del proceso.

Para obtener un ejemplo de script que abre solicitudes de incorporación de cambios para agregar un flujo de trabajo de {% data variables.product.prodname_actions %} a varios repositorios, vea el repositorio [`jhutchings1/Create-ActionsPRs`](https://github.com/jhutchings1/Create-ActionsPRs) para obtener un ejemplo mediante PowerShell, o bien [`nickliffen/ghas-enablement`](https://github.com/NickLiffen/ghas-enablement) para equipos que no tienen PowerShell y, en su lugar, quieren usar NodeJS.

### <a name="step-4-run-code-scans-and-review-your-results"></a>Paso 4: Ejecutar los escaneos de código y revisar tus resultados

Si ya tiene el examen de código habilitado en los repositorios necesarios, está a punto para ayudar a sus equipos de desarrollo a entender cómo ejecutar los exámenes de código y los informes, ver estos informes y procesar los resultados.

#### <a name="-data-variablesproductprodname_code_scanning_capc-"></a>{% data variables.product.prodname_code_scanning_capc %}

Con el examen de código, puede encontrar vulnerabilidades y errores en el código de su proyecto en GitHub, así como ver, clasificar, entender y resolver las alertas de {% data variables.product.prodname_code_scanning %} relacionadas.

Cuando el examen de código identifica un problema en una solicitud de incorporación de cambios, puede revisar el código resaltado y resolver la alerta. Para más información, vea "[Evaluación de prioridades de alertas de {% data variables.product.prodname_code_scanning %} en solicitudes de incorporación de cambios](/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/triaging-code-scanning-alerts-in-pull-requests)".

Si tiene permiso de escritura en un repositorio, puede administrar las alertas de examen de código para este. Con el permiso de escritura en un repositorio, {% ifversion delete-code-scanning-alerts %}puedes ver, corregir, descartar o eliminar alertas {% else %}puedes ver, corregir o descartar alertas{% endif %} en el caso de posibles vulnerabilidades o errores en el código del repositorio. Para obtener más información, consulte "[Administrar alertas de análisis de código para el repositorio](/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/managing-code-scanning-alerts-for-your-repository)".

#### <a name="generate-reports-of--data-variablesproductprodname_code_scanning--alerts"></a>Generar reportes de las alertas del {% data variables.product.prodname_code_scanning %}

Si te gustaría crear un reporte de las alertas del escaneo de código, puedes utilizar la API de {% data variables.product.prodname_code_scanning_capc %}. Para obtener más información, vea la [API "{% data variables.product.prodname_code_scanning_capc %}](/rest/reference/code-scanning)".

Para obtener un ejemplo de cómo usar la API {% data variables.product.prodname_code_scanning_capc %}, vea el repositorio [`get-code-scanning-alerts-in-org-sample`](https://github.com/jhutchings1/get-code-scanning-alerts-in-org-sample).

### <a name="step-5-configure--data-variablesproductprodname_code_scanning_capc--to-fine-tune-your-results"></a>Paso 5: Configurar el {% data variables.product.prodname_code_scanning_capc %} para ajustar tus resultados

Cuando ejecutas los escaneos de código iniciales, podrías no encontrar resultados o que se te devuelva una cantidad inusual de ellos. Es posible que quieras ajustar qué se debe resaltar en los escaneos futuros.

Para más información, vea "[Configuración del análisis de código](/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/configuring-code-scanning)".

Si tu compañía quiere utilizar otras herramientas de análisis de código de terceros con el escaneo de código de GitHub, puedes utilizar acciones para que ejecuten esas herramientas dentro de GitHub. Como alternativa, puedes cargar al escaneo de código los resultados que se generen con las herramientas de terceros como archivos SARIF. Para obtener más información, vea "[Integración con el examen de código](/code-security/code-scanning/integrating-with-code-scanning)".

### <a name="step-6-set-up-secret-scanning"></a>Paso 6: Configurar el escaneo de secretos

GitHub escanea los repositorios para los tipos de secreto conocidos, para prevenir el uso fraudulento de secretos que se confirmaron por accidente.

{% ifversion ghes %}

A fin de habilitar el examen de secretos para la instancia de {% data variables.product.prodname_ghe_server %}, vea "[Configuración del examen de secretos para el dispositivo](/admin/advanced-security/configuring-secret-scanning-for-your-appliance)".

{% endif %}

Necesitas habilitar el escaneo de secretos para cada proyecto piloto, ya sea habilitando la característica para cada repositorio o para todos los repositorios en cualquier organización que participe en el proyecto. Para más información, vea "[Administración de la configuración de seguridad y análisis del repositorio](/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-security-and-analysis-settings-for-your-repository)" o "[Administración de la configuración de seguridad y análisis para la organización](/organizations/keeping-your-organization-secure/managing-security-and-analysis-settings-for-your-organization)".

Para obtener información sobre cómo ver y cerrar alertas de secretos insertados en el repositorio, vea "[Administración de alertas del examen de secretos](/code-security/secret-scanning/managing-alerts-from-secret-scanning)".

### <a name="step-7-set-up-dependency-management"></a>Paso 7: Configurar la administración de dependencias

GitHub te permite evitar utilizar software de terceros que contenga vulnerabilidades conocidas. Proporcionamos las siguientes herramientas para actualizar las dependencias vulnerables{% ifversion GH-advisory-db-supports-malware %} y quitar el malware{% endif %}.

| Herramienta de administración de dependencias | Descripción |
|----|----|
| Alertas del dependabot | Puedes rastrear las dependencias de tu repositorio y recibir alertas de Dependabot cuando tu empresa detecte dependencias vulnerables. Para más información, vea "[Acerca de {% data variables.product.prodname_dependabot_alerts %}](/code-security/supply-chain-security/managing-vulnerabilities-in-your-projects-dependencies/about-alerts-for-vulnerable-dependencies)". |
| Gráfica de dependencias | La gráfica de dependencias es un resumen de los archivos de bloqueo y de manifiesto que se almacenan en un repositorio. Te muestra los ecosistemas y paquetes de los cuales depende tu base de código (sus dependencias) y los repositorios y paquetes que dependen de tu proyecto (sus dependencias). Para más información, vea "[Acerca del gráfico de dependencias](/code-security/supply-chain-security/understanding-your-software-supply-chain/about-the-dependency-graph)". |{% ifversion ghes or ghec %}
| Revisión de dependencias | Si una solicitud de cambios contiene cambios a las dependencias, puedes ver un resumen de lo que ha cambiado y si es que existen vulnerabilidades conocidas en cualquiera de estas dependencias. Para obtener más información, vea "[Acerca de la revisión de dependencias](/code-security/supply-chain-security/understanding-your-software-supply-chain/about-dependency-review)" o "[Revisión de los cambios de dependencia en una solicitud de incorporación de cambios](/github/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/reviewing-dependency-changes-in-a-pull-request)". | {% endif %} {% ifversion ghec or ghes > 3.2 %}
| Actualziaciones de seguridad del dependabot | El dependabot puede corregir las dependencias vulnerables levantando solicitudes de cambios con actualizaciones de seguridad. Para obtener más información, vea "[Acerca de las actualizaciones de seguridad de Dependabot](/code-security/supply-chain-security/managing-vulnerabilities-in-your-projects-dependencies/about-dependabot-security-updates)". |
| Actualizaciones de versión del dependabot | El dependabot puede utilizarse para mantener actualizados los paquetes que utilizas a su versión más reciente. Para obtener más información, vea "[Acerca de las actualizaciones de versiones de Dependabot](/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/about-dependabot-version-updates)". | {% endif %}

{% data reusables.dependabot.beta-security-and-version-updates-onboarding %}

### <a name="step-8-establish-a-remediation-process"></a>Paso 8: Establecer un proceso de remediación

Una vez que tu(s) equipo(s) haya(n) podido ejecutar escaneos, identificar vulnerabilidades y dependencias y pueda(n) consumir los resultados de cada característica de seguridad, el siguiente paso será asegurarse de que puedan remediar las vulnerabilidades identificadas dentro de su proceso de desarrollo normal sin involucrar a tu equipo de seguridad.

Esto significa que los equipos de desarrollo entienden el cómo utilizar las características de GHAS a lo largo del proceso de desarrollo, pueden ejecutar escaneos, leer reportes, consumir los resultados y solucionar las vulnerabilidades dentro de sus flujos de trabajo de desarrollo normales sin la necesidad de tener una fase de seguridad por separado al final del desarrollo o sin tener la necesidad de involucrar a su equipo de seguridad para entender los resultados/reportes.

### <a name="step-9-set-up-custom-analysis-if-needed"></a>Paso 9: configurar el análisis personalizado en caso de ser necesario

El análisis personalizado es un uso más profundo y opcional del escaneo de código cuando se requieren consultas personalizadas de CodeQL más allá del conjunto de consultas predeterminadas (y de comunidad) disponibles. Es raro que se requieran consultas personalizadas.

Las consultas personalizadas se utilizan para identificar alertas de seguridad personalizadas o para ayudar a que los desarrolladores sigan estándares de codificación al detectar algunos patrones de código.

Si a tu compañía le interesa escribir consultas de CodeQL personalizadas, hay ciertos requisitos que esta debería cumplir.

Si tu equipo puede proporcionar algunos ejemplos de vulnerabilidades existentes que te gustaría encontrar a través del CodeQL, por favor, informa de esto al equipo de GitHub y podemos programar una sesión de introducción para revisar lo básico del lenguaje y debatir sobre cómo abordar alguno de tus problemas. Si quieres cubrir el CodeQL con más detalle, entonces te ofrecemos opciones de participación adicionales para cubrir más temas para habilitar a tu equipo para crear sus propias consultas.

Puede obtener más información acerca de las [consultas de CodeQL](https://codeql.github.com/docs/writing-codeql-queries/codeql-queries/) en nuestra [documentación de CodeQL](https://codeql.github.com/docs/codeql-overview/) o ponerse en contacto con su equipo o representante comercial de {% data variables.product.prodname_professional_services %}.

### <a name="step-10-create--maintain-documentation"></a>Paso 10: Crear y mantener la documentación

Durante toda la fase piloto, es esencial crear y mantener documentación interna de alta calidad sobre los cambios de infraestructura y procesos que se realicen en tu compañía, así como las lecciones desde el proceso piloto y cambios de configuración que se hagan conforme tu(s) equipo(s) progrese(n) a lo largo de la implementación y de su proceso.

El tener una documentación completa y extensiva ayuda a que las fases restantes de tu implementación sean más un proceso repetible.
Una buena documentación garantiza que los equipos nuevos puedan integrarse consistentemente a través del proceso de implementación, así como cuando los miembros nuevos se unen a tu(s) equipo(s).

Una buena documentación no finaliza cuando se completa la implementación y el despliegue. La documentación más útil se actualiza activamente y evoluciona conforme tus equipos expanden su experiencia utilizando la GHAS y conforme crecen sus necesidades.

Adicionalmente a tu documentación, te recomendamos que tu compañía proporcione canales claros para que tu(s) equipo(s) tengan apoyo y orientación durante toda la implementación, despliegue y más allá. Dependiendo del nivel de cambio que necesite tomar tu compañía para apoyar la implementación y despliegue de la GHAS, el tener equipos con buen soporte te ayudará a adoptar exitosamente el flujo de trabajo diario de tu equipo de desarrollo.

## <a name="-octicon-milestone-aria-labelthe-milestone-icon---phase-2-organizational-buy-in--rollout-preparation"></a>{% octicon "milestone" aria-label="The milestone icon" %} Fase 2: Participación de la organización y preparación para el lanzamiento

{% note %}

{% octicon "clock" aria-label="Clock" %} **Tiempo estimado**: estimamos que la fase 2 puede durar aproximadamente entre 1 semana y más de 1 mes. Este rango puede variar ampliamente dependiendo de los procesos de aprobación interna de tu compañía.

{% endnote %}

Una de las metas principales de esta fase es garantizar que tengas la participación organizacional para hacer el despliegue total de la GHAS con éxito.

Durante esta fase, tu compañía revisará los resultados del (los) proyecto(s) piloto para determinar si este tuvo éxito, los ajustes que podrías necesitar hacer y si la compañía está lista para seguir con la implementación.

Dependiendo del proceso de aprobación de tu compañía, podría necesitarse la participación organizacional de tu patrocinador ejecutivo para seguir adelante. En la mayoría de los casos, se necesita la participación organizacional de tu(s) equipo(s) para seguir utilizando el valor de la GHAS para tu compañía.

Antes de continuar con la siguiente fase de implementación de la GHAS más ampliamente en tu compañía, a menudo se realizan modificaciones al plan de implementación actual con base en las enseñanzas del piloto.

También debería hacerse cualquier cambio que pudiera impactar la documentación para asegurarse de que está actualizada para una implementación contínua.

También te recomendamos considerar un plan de capacitación de cualquier equipo o miembros de este, a los cuales se les presentará la GHAS en las siguientes fases de tu implementación, en caso de que no lo hayas hecho ya.

### <a name="step-1-organize-results"></a>Paso 1: Organizar los resultados

Al finalizar la Fase 1, tu(s) equipo(s) deberá(n) tener {% ifversion ghes %} GHAS habilitado en tu instancia de {% data variables.product.prodname_ghe_server %} y haber{% endif %} podido utilizar todas las características clave de GHAS con éxito, potencialmente con algunos cambios de configuración para optimizar los resultados. Si tu compañía definió métricas de éxito claras en la fase 0, deberías poder medirte contra ellas para determinar el éxito de tu piloto.

Es importante volver a revisar tus métricas base al preparar tus resultados para garantizar que se puede demostrar un progreso incremental con base en las métricas que recolectaste del piloto contra tus metas de negocio originales. Si necesitas ayuda con esta información, GitHub puede ayudarte asegurándose de que tu compañía tenga las métricas correctas para medir tu progreso contra ellas. Para obtener más información sobre la ayuda disponible, vea "[Servicios y soporte técnico de GitHub](/admin/advanced-security/overview-of-github-advanced-security-deployment#github-services-and-support)".

### <a name="step-2-secure-organizational-buy-in"></a>Paso 2: Participación organizacional segura

La participación organizacional variará dependiendo de diversos factores, incluyendo el tamaño de tu compañía, el proceso de aprobación o incluso el nivel de los cambios que se requieren para implementar la GHAS, para mencionar algunos.

En el caso de algunas compañías, el asegurar la participación consta de una junta única, pero para otras, este proceso puede llevar más tiempo (potencialmente, semanas o meses). La participación puede requerir de aprobaciones de tu patrocinador ejecutivo o de adoptar la GHAS en los flujos de trabajo diarios de tu equipo.

La duración de esta etapa depende enteramente de tu compañía y de qué tan rápido te gustaría proceder. Te recomendamos buscar apoyo o servicios de GitHub en medida de lo posible para ayudarte a responder tus dudas y proporcionar recomendaciones que pudieras necesitar para apoyar este proceso. Para obtener más información sobre la ayuda disponible, vea "[Servicios y soporte técnico de GitHub](/admin/advanced-security/overview-of-github-advanced-security-deployment#github-services-and-support)".

### <a name="step-3-revise-and-update-documentation"></a>Paso 3: Revisar y actualizar la documentación

Revisa los resultados y hallazgos de tu(s) proyecto(s) piloto y las necesidades de los equipos restantes en tu compañía. Actualiza/revisa tu documentación con base en tu análisis de hallazgos y necesidades.

Descubrimos que es esencial garantizar que tu documentación esté actualizada antes de seguir con la implementación para el resto de la empresa de tu compañía.

### <a name="step-4-prepare-a-full-rollout-plan-for-your-company"></a>Paso 4: Prepara un plan de implementación integral para tu compañía

Con base en lo que aprendiste de tu(s) proyecto(s) piloto, actualiza el plan de implementación que diseñaste en la fase 0. Para prepararte para la implementación en tu compañía, considera cualquier capacitación que pudieran necesitar tus equipos, tal como aquella para la GHAS, cambios en los procesos o para la migración, en caso de que tu empresa se esté migrando a GitHub.

## <a name="-octicon-milestone-aria-labelthe-milestone-icon---phase-3-full-organizational-rollout--change-management"></a>{% octicon "milestone" aria-label="The milestone icon" %} Fase 3: Lanzamiento completo de la organización y administración de cambios

{% note %}

{% octicon "clock" aria-label="Clock" %} **Tiempo estimado**: estimamos que la fase 3 puede durar entre 2 semanas y varios meses. Este rango puede variar mucho, en función del tamaño de su compañía, la cantidad de repositorios o equipos, el nivel de cambios que el lanzamiento de GHAS requerirá para su compañía, etc.

{% endnote %}

Una vez que tu compañía se haya alineado con los resultados y hallazgos de tu(s) proyecto(s) piloto y que se hayan completado todos los pasos de la Fase 2, podrás proseguir con la implementación integral a tu compañía con base en tu plan.

### <a name="step-1-evaluate-your-rollout-as-you-go"></a>Paso 1: Evaluar tu implementación conforme avanzas con ella

Si estás utilizando un enfoque gradual para implementar la GHAS, te recomendamos hacer una pequeña pausa y completar una pequeña evaluación después de implementar la GHAS en un segmento diferente de tu compañía para garantizar que la implementación avanza sin problemas. Tu evaluación puede asegurarse de que los equipos se encuentren habilitados y capacitados de forma adecuada, que cualquier tipo de necesidad de configuración especial para la GHAS se haya cubierto y que los planes y la documentación puedan ajustarse conforme sea necesario.

### <a name="step-2-set-up-any-needed-training"></a>Paso 2: Configurar cualquier capacitación necesaria

Cuando implementes la GHAS para cualquier equipo más allá de aquellos del proyecto piloto, es importante garantizar que se les capacite o de que existan recursos de capacitación disponibles para proporcionar apoyo adicional cuando se necesite.

Estas son las áreas principales en donde vemos que las compañías necesitan más apoyo:
  - capacitación sobre la GHAS
  - capacitación para los clientes que son nuevos en GitHub
  - cpacitación sobre cómo migrarse a GitHub

Nuestro equipo de {% data variables.product.prodname_professional_services_team %} proporciona servicios de capacitación diversos, campamentos intensivos y consejos generales para ayudarte a apoyar a tu(s) equipo(s) a lo largo del proceso de implementación y despliegue. Para obtener más información, vea "[Servicios y soporte técnico de GitHub](/admin/advanced-security/overview-of-github-advanced-security-deployment#github-services-and-support)".

Para ayudarte a apoyar a tus equipos, aquí tienes una recapitulación de la documentación relevante de GitHub.

Para encontrar documentación sobre cómo habilitar la GHAS, consulta:
  - "[Habilitación de características de seguridad avanzadas](/get-started/learning-about-github/about-github-advanced-security)"
  - "[Administración de la configuración de seguridad y análisis de la organización](/organizations/keeping-your-organization-secure/managing-security-and-analysis-settings-for-your-organization)"
  - "[Administración de la configuración de seguridad y análisis para el repositorio](/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-security-and-analysis-settings-for-your-repository)"

Para encontrar documentación sobre cómo migrarse a GitHub, consulta:
  - "[Importación de código fuente a GitHub](/github/importing-your-projects-to-github/importing-source-code-to-github)"

Para encontrar documentación sobre cómo iniciar con GitHub, consulta:
  - "[introducción](/get-started)"

### <a name="step-3-help-your-company-manage-change"></a>Paso 3: Ayudar a que tu compañía administre el cambio

En el paso 4 de la fase 2, te recomendamos que actualices el plan de implementación inicial con base en tu aprendizaje del (los) proyecto(s) piloto. Asegúrate de seguir actualizando tu plan conforme implementas cualquier cambio organizacional necesario para implementar la GHAS en tu compañía exitosamente.

Las implementaciones exitosas de la GHAS y la adopción de las mejores prácticas en los flujos de trabajo diarios dependerán de la garantía de que tus equipos entienden el porqué es necesario incluir la seguridad en su trabajo.

### <a name="step-4-continued-customization"></a>Paso 4: Personalización continua

La configuración y personalización de la GHAS no pueden considerarse completadas una vez que se implementan en la empresa de tu compañía. Se debe seguir teniendo cambios de configuración personalizada con el paso del tiempo para garantizar que la GHAS sigue apoyando las necesidades cambiantes de tu compañía.

Conforme tu equipo se hace más experimentado y hábil con la GHAS al pasar el tiempo, esto creará oportunidades adicionales para que exista una personalización subsecuente.
