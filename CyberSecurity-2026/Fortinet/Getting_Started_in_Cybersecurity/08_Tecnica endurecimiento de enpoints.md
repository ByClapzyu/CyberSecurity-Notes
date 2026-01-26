
# Módulo: Seguridad de Endpoints

##  Introducción

El auge del Internet de las Cosas (IoT) ha aumentado exponencialmente el número de endpoints que deben protegerse. Una red es tan segura como su endpoint más vulnerable.

Las estrategias se dividen en cuatro pilares principales:

1. **Controles Administrativos:** Políticas humanas (Contraseñas, Restricciones, Privilegio Mínimo).
    
2. **Mantenimiento:** Higiene digital (Actualizaciones, Parches, Copias de seguridad).
    
3. **Protección Local:** Endurecimiento del sistema (Cifrado, DLP, Arranque seguro).
    
4. **Monitoreo:** Vigilancia activa (EPP, IDS, EDR).
    

---

## Controles Administrativos

**Principio de Privilegio Mínimo (PoLP):** Es la regla de seguridad más básica y efectiva. Consiste en permitir a los usuarios y procesos únicamente el acceso y los permisos estrictamente necesarios para desempeñar sus funciones, y nada más.

**Gestión de Políticas:** Tener una vista amplia y descendente para diseñar la seguridad ayuda a determinar políticas de red efectivas.

---

## Seguridad del Sistema Operativo y Arranque

**El Riesgo:** Han surgido amenazas que atacan el firmware y los procesos de arranque (antes de que cargue el antivirus).

**Protección Física y BIOS:**

- Es crucial proteger físicamente los dispositivos para evitar accesos no autorizados.
    
- **Bloqueo de BIOS:** Se debe configurar una contraseña en la BIOS para evitar que un atacante cambie la secuencia de arranque (ej. arrancar desde una USB con malware).
    

**UEFI vs. BIOS (Firmware):**

- Conocer cómo carga el OS es vital.
    
- **UEFI (Unified Extensible Firmware Interface):** Es la evolución de la BIOS.
    
- **Secure Boot (Arranque Seguro):** Es una de las funciones más importantes de UEFI. Restringe el firmware para que **solo cargue software/sistemas operativos firmados y aprobados**, evitando rootkits de arranque.
    

**Estandarización del OS:** Mantener una lista fija de sistemas operativos de confianza y estandarizados en la empresa facilita la administración y asegura que solo versiones seguras accedan a la red.

---

## Cifrado de Datos y Discos

Los dispositivos portátiles (laptops, celulares) son de alto riesgo por robo o pérdida. Si no están cifrados, ver el historial de navegación o caché DNS puede revelar información confidencial de la arquitectura de la red corporativa.

### Tipos de Cifrado

**A. Cifrado de Disco Completo (FDE - Full Disk Encryption):**

- Es una solución basada en **Software**.
    
- El sistema operativo se encarga de cifrar todo el disco.
    
- Ejemplo: BitLocker.
    

**B. Unidad de Autocifrado (SED - Self-Encrypting Drive):**

- Es una solución basada en **Hardware**.
    
- El disco duro tiene un módulo integrado que maneja automáticamente el cifrado y descifrado.
    
- **Ventaja:** La labor criptográfica la hace el disco, no el procesador (CPU) de la computadora, mejorando el rendimiento.
    

**C. TPM (Trusted Platform Module):**

- Es un chip de **Hardware** de seguridad en la placa madre.
    
- Almacena claves criptográficas, certificados y contraseñas de forma segura, separada del disco duro. Ayuda a verificar la integridad del sistema.
    

---

##  Prevención de Pérdida de Datos (DLP)

El software DLP (Data Loss Prevention) vigila la exfiltración de información.

**Funciones:**

- Detecta si alguien intenta copiar información confidencial (ej. números de tarjetas, planos).
    
- Bloquea la transferencia o registra el incidente.
    
- **Control de Periféricos:** Puede impedir el uso de memorias USB o discos externos no autorizados.
    

---

## Mantenimiento: Parches y Respaldos

**Actualizaciones y Parches:**

- Es la forma más sencilla y eficaz de reducir el riesgo.
    
- Cerrar vulnerabilidades conocidas impide que las herramientas de los atacantes funcionen.
    
- **Desafío:** La diversidad de dispositivos (BYOD) y equipos heredados (Legacy) dificulta la estandarización de parches.
    

**Copias de Seguridad (Backups):**

- Es fundamental para la recuperación ante desastres y la mitigación de ataques de **Ransomware**.
    
- **Problema en IoT:** Muchos dispositivos IoT no tienen función de respaldo.
    
- **Solución IoT:** Tener equipos de reserva (hardware spare) configurados para sustituir rápidamente a los dañados.

## Técnicas de Endurecimiento por Dispotivo

|**Dispositivo**|**Técnicas de Protección Recomendadas**|
|---|---|
|**Teléfono Inteligente**|1. EPP (Plataforma de Protección de Endpoints)<br><br>  <br><br>2. Actualización de Parches<br><br>  <br><br>3. Cifrado de disco completo (suele venir activo por defecto)|
|**Servidor**|1. EPP<br><br>  <br><br>2. Cifrado de disco completo<br><br>  <br><br>3. Actualización de Parches rigurosa|
|**Cámaras Inalámbricas (IoT)**|**Aislamiento de Red:** Al no soportar agentes de seguridad, deben estar en una VLAN separada sin acceso a la red principal.|
|**Refrigerador Inteligente (IoT)**|**Aislamiento de Red:** Igual que las cámaras, son dispositivos inseguros que deben segregarse.|


**Glosario de Monitoreo:**

- **EPP (Endpoint Protection Platform):** Antivirus de nueva generación. Prevención.
    
- **EDR (Endpoint Detection and Response):** Detecta ataques complejos en tiempo real y permite responder (investigar, aislar).
    
- **IDS (Intrusion Detection System):** Detecta intrusiones basándose en firmas o anomalías.