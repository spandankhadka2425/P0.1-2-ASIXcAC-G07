# Documentación del WAF Implementado

## ¿Qué WAF hemos elegido?
Hemos implementado **ModSecurity** como nuestro WAF (Web Application Firewall).

---

## ¿Qué es un WAF?
Un **WAF** es como un guarda de seguridad para nuestra aplicación web. Se coloca delante del servidor y analiza todas las peticiones antes de que lleguen a nuestra aplicación.

### ¿Qué hace?
- Filtra peticiones maliciosas
- Bloquea ataques antes de que lleguen a nuestra web
- Registra intentos de ataque

---

## ¿Por qué elegimos ModSecurity?

| Característica | ¿Por qué nos gusta? |
|----------------|---------------------|
| Gratuito | No cuesta dinero |
| Open Source | Podemos ver y modificar el código |
| Popular | Lo usa mucha gente, fácil encontrar ayuda |
| Actualizado | Se mantiene al día con nuevos ataques |
| Reglas OWASP | Protege contra los ataques más comunes |

---

[Redes] → [S1 con ModSecurity] → [Resto de servidores(s2,s3,s4,s5,s6)]