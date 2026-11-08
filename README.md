# Rutas del homelab

Página interactiva que muestra, paso a paso, cómo viajan los paquetes por mi red de casa. En cada paso el paquete se mueve por el esquema y al lado aparece qué lleva en cada capa: Ethernet, IP, UDP o TCP y la aplicación.

Las IP, los puertos, los registros DNS y las reglas son los reales de mi laboratorio (Proxmox VE con Docker en un LXC, Pi-hole, Nginx Proxy Manager, Tailscale y Wazuh).

## Recorridos

| Recorrido | Qué enseña |
|---|---|
| Nombre local | El PC pregunta por `homarr.lan` y el Pi-hole responde con sus registros locales, sin salir de casa |
| Bloqueo y DNS externo | Un dominio de anuncios recibe `0.0.0.0`; uno normal se reenvía a 8.8.8.8 a través del NAT del router |
| Web por el proxy | Saludo TCP en tres pasos, cabecera `Host` y Nginx Proxy Manager eligiendo el servicio |
| Acceso remoto | Desde el móvil en 4G por Tailscale: HTTP cifrado dentro de WireGuard, sin abrir puertos |
| Alerta en el SOC | Evento 4625 de Windows → agente de Wazuh → reglas 60122 y 60204 (MITRE T1110) |

## Cómo usarla

Ábrela en el navegador. Se puede reproducir, pausar, ir paso a paso (flechas del teclado y espacio) y cambiar la velocidad. Pasando el ratón por un equipo se ve su ficha.

Es un único `index.html`, sin dependencias ni compilación.

## Créditos

La idea de visualizar protocolos así viene de Protocol Explorer, de Dilum Sanjaya. Esta versión está hecha desde cero sobre mi propia red.

Iván Pérez Martínez · 2.º ASIR
