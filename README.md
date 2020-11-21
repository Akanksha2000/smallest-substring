# smallest-substring with maximum number of distinct characters
Noc = 256
str="abcda"

def mc(str, n): 
    ct = [0] * Noc
    for i in range(n): 
        ct[ord(str[i])] += 1
    md = 0
    for i in range(Noc): 
        if (ct[i] != 0): 
            md += 1    
    return md 
  
def smalsub(str): 
    n = len(str)     
    md = mc(str, n) 
    minlen = n     
    for i in range(n): 
        for j in range(n): 
            subs = str[i:j] 
            sublen = len(subs) 
            sdc = mc(subs,sublen) 
                
            if (sublen < minl and md == sdc): 
                minlen = sublen
    return minlen
l = smalsub(str); 
