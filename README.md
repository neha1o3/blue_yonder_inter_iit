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

file.close()
```
