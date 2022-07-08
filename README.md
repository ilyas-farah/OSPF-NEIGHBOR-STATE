# OSPF-NEIGHBOR-STATE
OSPF NEIGHBOR STATUS
--------------------

R1
---
int g0/0
ip address 12.1.1.1 255.255.255.0
no shutdown

R2
----
int g0/0
ip address 12.1.1.1 255.255.255.0
no shutdown

create looback R1

R1

int lo1
ip address 1.1.1.1 255.255.255.0
int lo2
ip address 1.10.10.1 255.255.255.0
end


create looback R2

R2

int lo1
ip address 20.0.0.1 255.255.255.0
int lo2
ip address 2.2.2.1 255.255.255.0
end

Interface Mode OSPF
-------------------

R1

int g0/0
ip ospf 1 area 0
end

netwrok
-------
int range lo1-2
ip ospf 1 area 0
end


R2

int g0/0
ip ospf 1 area 0
end

netwrok
-------
int range lo1-2
ip ospf 1 area 0
end

