# Towers-of-hanoi
Python code that ind the solution for Towers of Hanoi with n rings

def hanoi_reorder(towers,n,origin,target):
    if n==1:
        towers[origin][n-1]=0;
        towers[target][n-1]=1;
        print(towers)
    else:
        towers=hanoi_reorder(towers,n-1,origin,3-(origin+target));
        towers[origin][n-1]=0;
        towers[target][n-1]=n;
        print(towers)
        towers=hanoi_reorder(towers,n-1,3-(origin+target),target);
    return towers;

n=4;
towers=[[0 for x in range(n)] for y in range(3)];
for i in range(n):
    towers[0][i]=i+1;
print(towers)
towers=hanoi_reorder(towers,n,0,2);
