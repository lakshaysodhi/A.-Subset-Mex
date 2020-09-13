# A.-Subset-Mex
#include <bits/stdc++.h>
using namespace std;
#define ull unsigned long long
 
int main(){
 
    int t;
    cin>>t;
    while(t--){
 
        int n;
        cin>>n;
        vector<int> A(n);
        vector<int> H(101,0);
        for(int i=0;i<n;i++){
            cin>>A[i];
            H[A[i]]++;
        }
        int flagx=0;
        for(int i=0;i<H.size();i++){
 
            if(H[i]==0){
                cout<<2*i<<endl;
                flagx=1;
                break;
            }else if(H[i]==1){
                int mex1=i;
                int flag=0;
                for(int j=i+1;j<H.size();j++){
                    if(H[j]==0) {
                        cout<<j+mex1<<endl;
                        flag=1;
                        break;
                    }
                }
                flagx=1;
                if(flag==1) break;
                else cout<<mex1+H.size()<<endl;
                break;
            }
 
 
        }
 
        if(flagx==0) cout<<2*101<<endl;
    }
 
}
 
