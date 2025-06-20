<div align="center">
  <img src="https://raw.githubusercontent.com/EvolutionAPI/evolution-api/main/docs/logo.png" alt="Evolution API Logo" width="120"/>
  <h1 align="center">Stack de Evolution API para Traefik by DigitAllFran</h1>
  <p>
    <img src="https://img.shields.io/badge/Evolution%20API-v2.x-green?style=for-the-badge" alt="Evolution API"/>
    <img src="https://img.shields.io/badge/Traefik-v3-blueviolet?style=for-the-badge&logo=traefikproxy&logoColor=white" alt="Traefik v3"/>
    <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
    <img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" alt="Redis"/>
    <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
  </p>
</div>

> [!NOTE]
> **Gateway WhatsApp listo para producción**  
> Evolution API desplegada y asegurada tras Traefik, con PostgreSQL y Redis globales, lista para integraciones y automatización.

> [!TIP]
> **Arquitectura y dependencias**
> - **Traefik v3** como proxy inverso ([Stack recomendado](https://github.com/bicibikes15/Traefik))
> - **Bases de datos globales:** PostgreSQL y Redis ([Stack recomendado](https://github.com/bicibikes15/Globals-Databases))
> - **Red Docker externa:** `digitallfran_net`

> [!IMPORTANT]
> **El Ritual de Invocación (Instalación)**
> 1. **Clona el repositorio:**
>    ```
>    git clone https://github.com/bicibikes15/Evolution-API-Stack.git
>    cd Evolution-API-Stack
>    ```
> 2. **Verifica o crea la red externa:**
>    ```
>    docker network create digitallfran_net
>    ```
> 3. **Prepara la base de datos:**
>    ```
>    docker exec -it postgres_global psql -U postgres -c "CREATE DATABASE evolution_api_db;"
>    ```
> 4. **Configura los secretos:**
>    ```
>    cp .env.example .env
>    # Edita .env y rellena todas las variables (credenciales, dominios, etc)
>    ```
> 5. **Despliega Evolution API:**
>    ```
>    docker compose up -d
>    ```

> [!WARNING]
> **Verificación y acceso**  
> Traefik asignará el certificado SSL y expondrá la API en tu subdominio configurado.  
> Accede a `https://<TU_DOMINIO_EVOLUTION_API>` para probar la API.  
> Revisa logs con `docker logs evolution_api` si necesitas debug.

> [!NOTE]
> **¿Todo funcionando?**  
> Si puedes acceder al endpoint y conectar tu bot o integración, ¡listo!  
> Tienes tu gateway WhatsApp seguro y escalable, gestionado por DigitAllFran.

---

<div align="center">
  <a href="https://digitallfran.co" target="_blank">
    <img src="https://digitallfran.co/logo.svg" alt="DigitAllFran Logo" width="90"/><br>
    <b>¿Necesitas soporte, integración a medida o quieres llevar tu automatización al siguiente nivel?</b><br>
    <span style="font-size:1.1em;">
      <strong>¡Visita <u>digitallfran.co</u> y agenda tu consulta!</strong>
    </span>
  </a>
</div>
