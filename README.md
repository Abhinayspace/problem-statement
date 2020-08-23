#problem statement & solution
#the given problem statement is :
---------------------------------------------------------------------------------
Suresh wants to travel from city A to city B. But due to coronavirus pandemic, almost all the cities have levied entry tax into the cities so that the number of people entering the city can be limited. Suresh can skip at the most m cities at a time. Suresh has to declare his itinerary at the time of leaving city A. Thus he will have to pay upfront for entire itinerary and also has to pay a fee to get the slips issued. Upon payment he will be given the slips for intermediate cities where he has to show the slips to pass through, en route to his destination.

Some cities have enforced lockdown, that means those cities have blocked the entry into the cities and you will have to skip the cities in any case, such cities are represented by -1. This information is known to Suresh upfront.

Help Suresh find the minimum amount to be paid to reach from City A to City B  

Constraints
No of cities <=10^5

Input
First line contains an integer N, denoting the number of cities

Second line contains N space separated integers, where first integer denotes the cost of issuing itinerary slips and next (N-1) integers denote the entry fee of all cities. The last integer is always the destination city. If city is under lock down then its entry fee will be -1.

Third line contains an integer, M which represents number of cities he can skip from a present city during his travel

Output
Single integer which represents the minimum cost Suresh has to pay to travel from city A to B, but if city B is not reachable then print -1

Time Limit
1

Examples
Example 1

Input

5

1 6 -1 5 7

1

Output

19

 

Explanation

Since he could skip only 1 city between the cities. He will have to pay 1+6+5+7, where 1 is the fees paid to issue slips and [6,5,7] are the fees paid for the entry to the respective cities. So the total amount he has to pay while leaving A is 19.

 

Example 2

Input

4

3 4 1 -1

3

Output

-1

Explanation

Since the city B is under lockdown, he cannot go to city B. Hence the output is -1

SOLUTION OF TRAVEL COST
 

A=int(input())
c=list(map(int,input().split()))
B=int(input())
co=skips=0
if(c[-1]<0):
    co=-1
else:
    for i in c:
        if(skips>B):
            break
        else:
            if(i<0):
                skips+=i
                continue
                co+=i
                print(co,end='')
