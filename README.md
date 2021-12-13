# Elevator_Code_Python
def goup(cur,f):
    print("Going UP")
    for i in range(cur+1,f+1):
        if i!=f:
            print("Floor {0} passed".format(i))
        cur=i
    print("Floor {0} arrived".format(cur))
    return cur
def godown(cur,f):
    print("Going DOWN")
    for j in range(cur-1,f-1,-1):
        if j!=f:
            print("Floor {0} passed".format(j))
        cur=j
    print("Floor {0} arrived".format(cur))
    return cur

def floor():
    q=1
    cur=0
    while (q!=0):
        lower=[]
        higher=[]
        for i in range(int(input("Number of stops\n"))):
            #f=int(input("press button: 0,1,2,3,4,5,6"))
            x=int(input())
            if x<cur:
                lower.append(x)
            else:
                higher.append(x)
        higher=list(set(higher))
        higher.sort()
        lower=list(set(lower))
        lower.sort(reverse=True)
        print(higher,lower)
        for f in higher:
            if f<0 or f>6:
                print("invalid number",f)
                continue
            print("current floor:",cur)
            if f==cur:
                print("already on {0} floor".format(f))
            elif f<cur:
                cc=godown(cur,f)
            else:
                cc=goup(cur,f)
            print(cc)
            cur=cc
        for f in lower:
            if f<0 or f>6:
                print("invalid number",f)
                continue
            print("current floor:",cur)
            if f==cur:
                print("already on {0} floor".format(f))
            elif f<cur:
                cc=godown(cur,f)
            else:
                cc=goup(cur,f)
            print(cc)
            cur=cc

        q=int(input("press '0' to ShutDown the Lift"))

top=6
min=0
floor()
