<img width="953" height="34" alt="image" src="https://github.com/user-attachments/assets/ccd84127-c00e-477e-9ddc-3a63e3d097c2" /># Tugas-2-Jarkom-docs

Docs about my CIDR implementation from class assignment.

Three big factor on making this works (= machine from any subnet can ping machines from other subnet):
- Routing
- IP addressing
- Picking the right transmission medium

## Routing

It was stated that there will be main and branch office area. This means there is an additional subnet for routers that connects the previously stated two area. The smallest unit of subnet is by a LAN formed under one room from the office area (eg. subnet A6 consisting of 6 hosts in Server & Admin room). Put these into consideration before doing CIDR subnet calculation. 


| Alias  | Hosts | Subnet Mask      | Incerment  | Network addr  |  Sub. Mask  | 1st usable addr.  | Last usable addr.  | Broadcast addr.  |
| ------ | ----- | ---------------- | ---------- | ------------- | ----------- | ----------------- | ------------------ | ---------------- |
| A1     | 95    | 255.255.255.128  | 128        | 10.31.0.0     | /25         | 10.31.0.1         | 10.31.0.126        | 10.31.0.127      |
| A2     | 45    | 255.255.255.128  | 64         | 10.31.0.128   | /26         | 10.31.0.129       | 10.31.0.190        | 10.31.0.191      |
| ..     | ..    | ..               | ..         | ..            | ..          | ..                | ..                 | ..               |

I will now give you one example of CIDR subnet calculation. Say there is 95 host in one of the main office room. We will now call it subnet "A1". First, find the closest subnet mask that is one level higher than the amount of host the room has, its `255.255.255.128`. Then pick the Network address of this subnet (very important to remember for routing later). 

One of the room on main office area has over 380 hosts. 
