# Gyaszos_EIGRP
## ospfv2 sokkal jobb by the way | only ospfv kein gooning for eigrp |

__forras:__ https://szit.hu/doku.php?id=oktatas:halozat:cisco:eigrp




```bash 
R1(config)# router eigrp 1

R1(config-router)# eigrp rotuer-id 1.1.1.1
R2(config-router)# eigrp rotuer-id 2.2.2.2
R1(config-router)# network 192.168.10.0 0.0.0.255
R1(config-router)# network 172.16.0.0 0.0.255.255
R1(config-router)# network 192.168.10.8 255.255.255.252
R1# show running-config | section eigrp 1

```
# Alapértelmezett útvonal
## Ha szeretnénk terjeszteni az EIGRP forgalomirányítókon a statikus útvonalakt, az alapértelmezett útvonallal együtt, akkor a következő parancsot használjuk:
```bash 
R1(config-router)# redistribute static
```








Passzív interfész
Ha vannak interfészek, amelyekhez nem kapcsolódik EIGRP forgalomirányító, akkor az passzívvá tehetjük a következő paranccsal:

passive-interface <interfész>
Példa:
```bash 
R1(config-router)#passive-interface fastEthernet 0/0
```
Összegzés
Hegy egy EIGRP forgalomirányító hátár-forgalomirányító, akkor az alapértelmezetten automatikus összegzést használ. A határ-forgalomirányító több interfésszel osztály alapú hálózatokkal és/vagy különböző hosszúságú alhálózati maszkokkal. Ez problémát okozhat az EIGRP VLSM, CIDR és a nem-folytonos hálózatok esetén, ezért kiszoktuk kapcsolni a no auto-summary paranccsal.

```bash 
R1(config-router)# no auto-summary
```
A no auto-summary nagyon hasznos az EIGRP képességei számára, a változó hosszúságú és a nem folytonos alhálózatok esetén. Ennek ellenére, néha szeretnénk a forgalomirányító táblánkat összegzéssel optimalizálni. Ebben az esetben az ip summary-address parancsot használhatod egy interfészen.


```bash 
R1# show ip eigrp neighbor
R1# show ip eigrp topology
R1# show running-config
R1# show ip protocols
R1# show ip route
```
