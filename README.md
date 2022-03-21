# blue_yonder_inter_iit
## Code
```
import csv
file = open("Demand.csv")
csvreader = csv.reader(file)
header = next(csvreader)
print(header)
rows = []
for row in csvreader:
    rows.append(row)
print(rows)

file2 = open("Parameters.csv")
csvreader2 = csv.reader(file2)
header2 = next(csvreader2)
print(header2)
rows2 = []
for row in csvreader2:
    rows2.append(row)
print(rows2)
WH=[]
Nofly=[]
RC=[]
P=[]
Q=[]
A=[]
B=[]
C=[]
Count=[]
for x in range(len(rows2)):
    if (rows2[x][3]=="Noflyzone" and rows2[x][0][0]=="X" and rows2[x][0][2]=="1"):
        a=[]
        for i in range(24):
            a.append(rows2[x+i][1])
        Nofly.append(a)
    elif ("WH Location" in rows2[x][3] and "X" in rows2[x][0]):
        WH.append([rows2[x][1],rows2[x+1][1], rows2[x+2][1]])
    elif ("Recharge" in rows2[x][3] and "X" in rows2[x][0]):
        RC.append([rows2[x][1],rows2[x+1][1]])
    elif ("Drone" in rows2[x][3] and "P" in rows2[x][0]):
        P.append([rows2[x][1]])
    elif ("Drone" in rows2[x][3] and "Q" in rows2[x][0]):
        Q.append([rows2[x][1]])
    elif ("Drone" in rows2[x][3] and "A" in rows2[x][0]):
        A.append([rows2[x][1]])
    elif ("Drone" in rows2[x][3] and "B" in rows2[x][0]):
        B.append([rows2[x][1]])
    elif ("Drone" in rows2[x][3] and "Count" in rows2[x][0]):
        Count.append([rows2[x][1]])
    elif ("Drone" in rows2[x][3] and "C" in rows2[x][0]):
        C.append([rows2[x][1]])
print(WH)    
print(RC)
print(P)
print(Q)
print(A)
print(B)
print(C)
print(Count)
print(Nofly)
file.close()
file2.close()
```
