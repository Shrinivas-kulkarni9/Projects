if __name__ == "__main__":
    tc = int(input())
    for i in range(tc):
        n = int(input())
        d = int(input())
        twoness = 0
        fiveness = 0
        two = 0
        five = 0
        while d%2 == 0:
            d = d/2
            twoness+=1
        while d%5 == 0:
            d = d/5
            fiveness+=1
        while n%2 == 0:
            n = n/2
            two+=1
        while n%5 == 0:
            n = n/5
            five+=1
        if two>twoness:
            n = n*(2**(two - twoness))
        else:
            twoness = twoness - two
        if five>fiveness:
            n = n*(2**(five - fiveness))
        else:
            fiveness = fiveness - five
        m = max(twoness,fiveness)
        fac = (10**m)//((2**twoness)*(5**fiveness))
        n = n*fac
        integer = n//d
        frac = n%d
        if frac == 0:
            if integer%(10**m) == 0:
                print(int(integer/(10**m)))
            else:
                print(integer/(10**m))
            continue
        k = 9
        recur = 0
        i = 0
        temp = frac
        while int((temp*10)/d) == 0:
            temp*=10
            i+=1
        zeros = '0'*i
        while True:
            if k%d == 0:
                temp = k/d
                recur = int(frac*temp)
                print(frac,k,d,'frac*k/d')
                print(frac*k/d)
                break
            k = k*10 + 9
        if integer%(10**m) == 0:
            print(str(int(integer//(10**m))) + '.' + '(' + zeros + str(recur) + ')')
        else:
            print(str(integer/(10**m)) + '(' + zeros + str(recur) + ')')
