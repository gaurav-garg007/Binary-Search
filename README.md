#include<bits/stdc++.h>
using namespace std;
bool ip(int a[], int n, int m, int mid){
   int sc=1,ps=0;
   for(int i=0;i<n;i++){
       if(ps+a[i]<=mid){
           ps+=a[i];
       }
       else{
           sc++;
           if(sc>m){
               return false;
           }
           ps = a[i];
       }
   }
   return true;
}
int main()
{
    int s,n,sum=0,m,e,ans;
    cin>>n>>m;
    int a[n];
    for(int i=0;i<n;i++){
        cin>>a[i];
        sum +=a[i];
    }
    s=0;e=sum;
    int mid=(e+s)/2;
    while(s<e){
        if(ip(a, n, m, mid)){
            ans = mid;
            e = mid-1;
        }
        else{
            s = mid+1;
        }
        mid=(e+s)/2;
    }
    cout<<ans;
}
