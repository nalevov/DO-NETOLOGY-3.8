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

## 2. Создайте dummy0 интерфейс в Ubuntu. Добавьте несколько статических маршрутов. Проверьте таблицу маршрутизации.

### Решение:
1. Командой sudo modprobe -v dummy numdummies=2 создаем 2 интерфейса
2. Командой sudo ip addr add 192.168.1.150/24 dev dummy0 задаем ip адрес для dummy  интерфейса
3. Командой sudo ip route add 192.168.1.150 dev eth0 прописали статический маршрут 
4. Командой ip -br route проверили таблицу маршрутизации
![image](https://user-images.githubusercontent.com/95496224/183738219-e74c2425-fb1f-4795-8e3c-c78f4046c56a.png)

## 3. Проверьте открытые TCP порты в Ubuntu, какие протоколы и приложения используют эти порты? Приведите несколько примеров.

### Решение:
При помощи команд sudo netstat -lnt или sudo ss -ltn проверяем открытые порты - открыты 53 и 22 порт.
22 порт используется для подкдлючения по протоколу SSH, 53 используется Системой доменных имен (DNS)
Например, для удаленного управления операционной системой мы подключаемся к серверу по прокотолу SSH. 

## 4. Проверьте используемые UDP сокеты в Ubuntu, какие протоколы и приложения используют эти порты?

### Решение:

Проверяем при помощи команд sudo netstat -lnu или sudo ss -lnu. Используются 53 и 68 порты: 53 используется Системой доменных имен (DNS) а 68 клиентом DHCP для получения динимического адреса.




      
