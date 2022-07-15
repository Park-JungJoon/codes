# Antismashoutput function counting
<pre>
<code>
from collections import defaultdict
func = ['cyclic-lactone-autoinducer', 'betalactone', 'NRPS-like', 'lanthipeptide-class-ii', 'PKS-like', 'RRE-containing', 'RaS-RiPP', 'fatty_acid', 'saccharide', 'lanthipeptide-class-iii', 'arylpolyene', 'ladderane', 'butyrolactone', 'hglE-KS', 'lanthipeptide-class-iv', 'T3PKS', 'LAP', 'RiPP-like', 'lanthipeptide-class-i', 'furan', 'terpene', 'T1PKS', 'halogenated', 'phosphonate', 'sactipeptide', 'NRPS', 'transAT-PKS', 'lanthipeptide-class-v', 'thiopeptide', 'lassopeptide', 'phenazine', 'ranthipeptide']
dic = defaultdict(int)
for fun in func:
    dic[fun] = 0
with open("C:/Users/jungj/Desktop/antismash_table.txt") as f:
    lines= f.readlines()
    ls = []
    for line in lines:
        line = line.rstrip()
        ls.append(line.split('\t')[1])
    for i in range(len(ls)):
        for n in func:
            if n in ls[i]:
                dic[n] += 1
count = 0
print('|function|count|')
print('|-|-|')
for k in dic.keys():
    print('|'+k+'|'+str(dic[k])+'|')
</code>
</pre>
