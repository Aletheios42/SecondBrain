**MetaTags:** #_Todo
**Tags:** #SistemasDistribuidos
- - -
Un sistema distribuido es un sistema cuyo estado es compartido por multiple agentes
ejemplos:
- DNS: es una tabla distribuidad de IP -> nombres
- Facebook/ Google para almacenamiento
- Servidores Email (SMTP)
- Red Telefonica
- las luces de trafico
- las redes de trenes
- Aviones (RS232 serial links)

Ventajas: 
	- te permite alinear los intereses de los usuarios con los tuyos a traves de un sistema de incentivos
	- flixibilidad de hardware(entender)
	- latencia (al tener muchos servidores es mas facil que te ouedas conectar a uno cerca)
	- sistema trusless
	- escalable

- - -
# [[Métricas de Servicio]]

- - -

Naming 
RPC
Time
Consensus
storage
SRE

- - - 
## Incompleted List of problems
- crash/crashloop
- server down
- Data corruption
- Query of death
- broken depency
- cascading failurre
- DDos attack
- Heisenbug
- customer reported failure
- data loss
- time travel
- Owned
- operator error
- Certificate espiration
- nor lineal response to change
- hash collition

- - - 
Real systems need to guarantee a high level of availability with all nines in percentage:

99% = 3.65 days of downtime per year

99.9% = 8.76 hours of downtime per year

99.99% = 52.56 minutes of downtime per year

99.999% = 6 minutes of downtime per year
- - -

# [[Mecanismos de Consenso]]


- - - 
## ***Sources:***
https://www.distributedsystemscourse.com/