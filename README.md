# DO-NETOLOGY-3.8

## 1. Подключитесь к публичному маршрутизатору в интернет. Найдите маршрут к вашему публичному IP

### Решение:
1. Выполняем команду telnet route-views.routeviews.org 
2. Имя пользователя rviews
3. Выполняем команду show ip route 90.154.71.108
4. Получаем: 
```
  Routing entry for 90.154.70.0/23
  Known via "bgp 6447", distance 20, metric 0
  Tag 2497, type external
  Last update from 202.232.0.2 1w4d ago
  Routing Descriptor Blocks:
  * 202.232.0.2, from 202.232.0.2, 1w4d ago
      Route metric is 0, traffic share count is 1
      AS Hops 3
      Route tag 2497
      MPLS label: none
 ```
 5. Вводим команду show bgp 90.154.71.108
 6. Получаем:
 ```
  BGP routing table entry for 90.154.70.0/23, version 2369168020
  Paths: (23 available, best #22, table default)
  Not advertised to any peer
  ```
 7. Получается на выбор предоставляется 23 варианта маршрута, № 22 предпочтительный
  ```
  Refresh Epoch 3
  2497 12389 42610
    202.232.0.2 from 202.232.0.2 (58.138.96.254)
      Origin IGP, localpref 100, valid, external, best
      path 7FE02F391370 RPKI State not found
      rx pathid: 0, tx pathid: 0x0
 ```
      
      
