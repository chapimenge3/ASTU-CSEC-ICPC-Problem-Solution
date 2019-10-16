#include <bits/stdc++.h>
#include <cstdio>
#include <cstring>
#include <cmath>
#include <cstring>
#include <chrono>
#include <complex>
#define endl "\n"
#define ll long long int
#define vi vector<int>
#define vll vector<ll>
#define vvi vector < vi >
#define pii pair<int,int>
#define pll pair<long long, long long>
#define mod 1000000007
#define inf 1000000000000000001;
#define all(c) c.begin(),c.end()
#define mp(x,y) make_pair(x,y)
#define mem(a,val) memset(a,val,sizeof(a))
#define eb emplace_back
#define f first
#define s second

using namespace std;
/* Function to calculate x raised to the power y in O(logn)*/
ll power(ll x, unsigned ll y)
{
    ll temp;
    if( y == 0)
        return 1;
    temp = power(x, y/2);
    if (y%2 == 0)
        return (temp*temp)%mod;
    else
        return (x*temp*temp)%mod;
}

int main()
{
    //for fast i/o with equivalent to printf() and scanf to cout and cin
    std::ios::sync_with_stdio(false);
    cin.tie(0);
    ll a,b,c,d;
    //it excute until the first input is -1
    while(cin>>a && a!= -1)
    {
        cin>>b>>c>>d;
        int t;
        cin>>t;
        // max array size
        ll arr[500];
        for(int i=0 ; i<t; ++i)
        {
            //asign to array
            cin>>arr[i];
        }
        // map for the number and its recursion result like 0 :  1  
        map<ll,ll> m ;
        int ar[500];
        //copy the array bcos the orgional array is important after the recusion done
        copy(arr,arr+t,ar);
        //sort it to do the recursion for the larger one first bcos if we do for the large
        //then we can simply get for the simple 
        sort(ar,ar+t);
        int k = 0;
        ll j = ar[k];
        //for assigning j to smallest posetive integer of the array
        while(j <= 0)
        {
            j=ar[++k];
        }
        ll x = 1,y = 0, z = 0,w = 1 ;
        // pow2 is 2^d ( 2 the power of d) as the question request the 2^d is done once here
        ll pow2 = power(2,d);
        ll n = ar[t-1];
        // now starting from 1 the recursion will do for every i less than n and store if i is in array 
        for(ll i = 1 ; i <= n; i++)
        {
            // here is the same calculation as the question 
            // f(n) = a*f(n-1) + b*f(n-2) + c*f(n-3) + 2^d
            // w = f(n) ,x = f(n-1) , y = f(n-2) and z = f(n-3)  
            w = ((a*x) + (b*y) + (c*z) + pow2)%mod ;

            z = y, y = x, x = w;
            if (i == j)
            {
                m[i] = w;
                j = ar[++k];
                while(i==j)
                {
                    j=ar[++k];
                }
            }

        }
        // lastly output if the element less than 0 then print -1
        // if the element is equals to zero the print 1
        // else print the stored value of the element that we stored above  m[i] = w;

        for(int i = 0; i < t; i++)
        {
            if(arr[i] < 0)
                cout<<0<<endl;
            else if ( arr[i] == 0)
                cout<<1<<endl;
            else
                cout<<m[arr[i]]<<endl;
        }
    }
}
