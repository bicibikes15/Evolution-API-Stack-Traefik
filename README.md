# Stack de Evolution API para Traefik by DigitAllFran

Este stack despliega la Evolution API, un gateway no oficial para WhatsApp, y la configura para ser gestionada y asegurada por un ecosistema de servicios preexistente.

## Arquitectura y Dependencias

Esta API requiere un ecosistema funcional para operar.

#### **Prerrequisitos Indispensables:**

1.  **El Guardián (Traefik):** Necesitas una instancia de Traefik v3 funcionando.
    * **Stack Recomendado:** [Stack de Traefik de DigitAllFran](https://github.com/bicibikes15/Traefik)

2.  **El Arsenal (Bases de Datos):** La API requiere PostgreSQL y Redis. Se conectará al:
    * **Stack Global de Bases de Datos de DigitAllFran](https://github.com/bicibikes15/Globals-Databases)

3.  **La Red Compartida:** El estandarte oficial de este ecosistema es `digitallfran_net`.

## El Ritual de Invocación (Instalación)

**1. Clonar el Repositorio**
```bash
git clone [https://github.com/tu-github/Evolution-API-Stack.git](https://github.com/tu-github/Evolution-API-Stack.git)
cd Evolution-API-Stack

2. Verificar la Red Externa

Asegúrate de que la red digitallfran_net existe. Si no, créala:

Bash

docker network create digitallfran_net

3. Preparar la Base de Datos

Crea una base de datos dedicada para la API dentro de tu PostgreSQL global.

Bash

docker exec -it postgres_global psql -U postgres -c "CREATE DATABASE evolution_api_db;"

4. Configurar los Secretos

Crea tu archivo de configuración local a partir de la plantilla.

Bash

cp .env.example .env
Ahora, edita el archivo .env y rellena todas las variables. Asegúrate de que las credenciales de la base de datos coinciden con las de tu stack global.

5. Desplegar la API

Bash

docker compose up -d