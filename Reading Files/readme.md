### File reading

```py
with open('example.txt', 'r') as reader :
    f = reader.readlines()
print(f)

for line in f : 
   new_line=line.strip('\n')
   print(new_line)
   
# For printing in lines.

```

