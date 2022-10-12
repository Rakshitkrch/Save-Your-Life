# Save-Your-Life
//{ Driver Code Starts
//Initial Template for C++

#include<bits/stdc++.h>
using namespace std;

// } Driver Code Ends
//User function Template for C++

class Solution{
public:
      string maxSum(string w,char x[], int b[],int n){
          unordered_map<char,int> mp;
          for(int i=0;i<n;i++){
              mp[x[i]]=b[i];
              
          }
          int sum=0;
          string ans="";
          int maxsum=INT_MIN;
          string mxstr="";
          for(int i=0;i<w.size();i++){
              if(mp.count(w[i])){
                  sum+=mp[w[i]];
                  ans+=w[i];
                  
                  
                  
              }
              else{
                  sum+=w[i];
                  ans+=w[i];
              }
              if(sum>maxsum){
                  maxsum=sum;
                  mxstr=ans;
                  
              }
              if(sum<0){
                  sum=0;
                  ans="";
              }
              
          }
          return mxstr;
      }
};

//{ Driver Code Starts.
int main() 
{ 
    int t;
    cin>>t;
    while(t--)
    {
        string w;
        cin>>w;
        int n;
        cin>>n;
        char x[n];
        int b[n];
        for(int i = 0;i<n;i++)
            cin>>x[i];
        for(int i = 0;i<n;i++)
            cin>>b[i];
        Solution ob;
        cout << ob.maxSum(w,x,b,n) << endl;
    }
    return 0; 
}
// } Driver Code Ends
