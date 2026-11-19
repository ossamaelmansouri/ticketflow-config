# ticketflow-config

Configuration centralisée de TicketFlow, lue par `config-server` (TP3 du module Architecture microservices).

**Auteur : Ossama Elmansouri**

| Fichier | Lu par |
|---|---|
| `application.yml` | toutes les applications clientes (propriétés partagées : Eureka) |
| `customer-service.yml` | customer-service (port 8081, Actuator refresh, `ticketflow.message`) |
| `customer-service-dev.yml` | customer-service avec le profil `dev` |
| `api-gateway.yml` | api-gateway (port 8080, route `lb://customer-service`) |
| `event-service.yml`, `booking-service.yml` | TP4 et TP5 (port, délais OpenFeign, circuit breaker) |

Lancement de config-server (dépôt applicatif : github.com/ossamaelmansouri/Ticketflow) :

```bash
export CONFIG_GIT_URI=https://github.com/ossamaelmansouri/ticketflow-config.git
./mvnw -pl services/config-server spring-boot:run
```

Aucun secret n'est stocké dans ce dépôt.
