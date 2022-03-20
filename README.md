# blue_yonder_inter_iit
## Code
```import csv
file = open("Demand.csv")
csvreader = csv.reader(file)
header = next(csvreader)
#print(header)
rows = []
for row in csvreader:
    rows.append(row)
#print(rows)

file2 = open("Parameters.csv")
csvreader2 = csv.reader(file2)
header2 = next(csvreader2)
#print(header2)
rows2 = []
for row in csvreader2:
    rows2.append(row)
#print(rows2)

file.close()
file2.close()
```
