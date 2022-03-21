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
drone=[[2000,2,5,200,1],[2500,2.5,6,500,1],[3000,3,7,1000,2],[4000,3.5,8,2000,2],[5000,4,9,3000,2],[10000,5,10,5000,4]]
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
M= rows2[0][1]
def speed(dtype, pload):
    f=pload/drone[dtype-1][2]
    a=[M-P[dtype-1]*f, M-Q[dtype-1]*f, M+Q[dtype-1]*f]
    return a
def energy(w,s,h,dtype):
    return w(A[dtype-1]+s*B[dtype-1]+h*C[dtype-1])

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
