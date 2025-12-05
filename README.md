def count_melted_ice(tunnel):

    tunnel = list(tunnel)  
    tm = 0
    mr = True
    
    while mr:
        mr = False
        n = len(tunnel)
        to_melt = [False] * n  
        
        for i in range(n - 2):
            if tunnel[i] == '_' and tunnel[i+1] == '_' and tunnel[i+2] == '_':
                if i+3 < n and tunnel[i+3] == 'I':
                    to_melt[i+3] = True
        
        for i in range(n):
            if to_melt[i]:
                tunnel[i] = '_'  
                tm += 1
                mr = True
    
    return tm
