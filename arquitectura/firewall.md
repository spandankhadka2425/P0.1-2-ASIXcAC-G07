# Firewall davant de S1

## Objectiu

Implementar un firewall al servidor host mitjançant **UFW** per filtrar tràfic
no autoritzat abans que arribi a la infraestructura d'Extagram.

---

## Estat actual del firewall

![firewall](../imagen/firewall-2.png)

## Anàlisi de les regles

### Ports oberts al públic
| Port   | Servei          | Motiu                   |
| ------ | --------------- | ----------------------- |
| 80/tcp | HTTP (nginx S1) | Accés públic a Extagram |

### Ports restringits a admins
| Port     | Servei  | IPs permeses            |
| -------- | ------- | ----------------------- |
| 22/tcp   | SSH     | 192.168.70.10, .20, .22 |
| 3000/tcp | Grafana | 192.168.70.10, .20, .22 |

### Ports bloquejats totalment
| Port     | Servei   | Motiu                               |
| -------- | -------- | ----------------------------------- |
| 3306/tcp | MySQL    | Base de dades no accessible des de fora |
| 3100/tcp | Loki     | Monitoratge no accessible des de fora   |
| 9000/tcp | PHP-FPM  | Serveis interns no exposats             |
| 9200/tcp | (legacy) | Eliminat del projecte (era Elasticsearch) |

---
