# Fase 1: Migración de Windows a Linux Mint

Esta sección documenta la fase inicial de transición hacia un ecosistema basado en Linux, detallando las razones del cambio, la preparación del entorno y el proceso de instalación limpia.

## 1. Justificación del Cambio

El cambio a Linux Mint responde a la necesidad de contar con un entorno de trabajo más estable, seguro y orientado al desarrollo de software, sin sacrificar la capacidad de ejecutar videojuegos modernos.

*   **Rendimiento y Control:** Mayor autonomía sobre los procesos del sistema y menor consumo de recursos en reposo (idle).
*   **Entorno de Desarrollo Nativo:** Simplificación de flujos de trabajo con Python, Git, Docker y terminales POSIX reales.
*   **Privacidad:** Reducción drástica de la telemetría asociada a sistemas operativos propietarios.

## 2. Inventario y Evaluación de Hardware

*Añade aquí las especificaciones clave de tu equipo para tenerlas de referencia técnica en el futuro:*

*   **CPU:** [Ej. AMD Ryzen 5 / Intel Core i5]
*   **RAM:** [Ej. 16 GB DDR4]
*   **GPU:** [Ej. NVIDIA GTX 1650 / AMD Radeon Vega 8] *(Crucial para la sección de Gaming Ops)*
*   **Almacenamiento:** [Ej. SSD NVMe 500GB]
*   **Arquitectura de red:** Adaptador Wi-Fi (Verificar compatibilidad de drivers privativos).

## 3. Estrategia de Respaldo (Backup)

Antes de alterar la tabla de particiones, se ejecutó un protocolo de respaldo estricto:

1.  **Archivos Personales y de Universidad:** Copia de seguridad en disco duro externo y sincronización en la nube.
2.  **Partidas Guardadas (Savegames):** Respaldo de partidas locales de juegos que no cuentan con Steam Cloud.
3.  **Configuraciones Clave:** Exportación de marcadores del navegador y credenciales locales esenciales.

## 4. Creación del Medio de Instalación (Live USB)

*   **Distribución Elegida:** Linux Mint (Edición Cinnamon).
*   **Herramienta de Flasheo:** Se utilizó [Rufus / BalenaEtcher / Ventoy] desde Windows para crear el pendrive booteable.
*   **Validación:** Se verificó la suma de comprobación (SHA256) de la ISO original para asegurar su integridad.

## 5. Proceso de Instalación

Se optó por una **[Instalación Limpia (Single Boot) / Instalación con Arranque Dual (Dual Boot)]** para priorizar el rendimiento del sistema de archivos `ext4`/`btrfs`.

1.  Acceso a la UEFI/BIOS y desactivación temporal de *Secure Boot* (si fuese necesario para drivers de GPU).
2.  Ejecución de la sesión Live USB de Linux Mint.
3.  Configuración del particionado:
    *   `/boot/efi`: (Partición del sistema EFI).
    *   `/`: (Raíz del sistema, ext4).
    *   `/home`: (Partición separada para datos y configuraciones personales, facilitando reinstalaciones futuras).
4.  Creación de usuario principal (Aion) y asignación de privilegios de administrador (`sudo`).

## 6. Primer Arranque y Actualizaciones Críticas

1.  **Actualización del Sistema:** Ejecución del Gestor de Actualizaciones (Update Manager) para aplicar parches de seguridad y actualizar el kernel.
2.  **Instalación de Controladores:**
    *   Apertura del "Administrador de Controladores" (Driver Manager).
    *   Instalación del microcódigo del procesador.
    *   Instalación de drivers privativos (ej. NVIDIA o adaptadores Wi-Fi específicos).

---
*Próximo paso: [Configuración del Sistema y Desarrollo](02-sistema.md)*
