# 15th

#include <iostream>
#include <vector>
using namespace std;

// Class is for 2d arrays problems

// 2d vector
// int main(){
//     // vector<vector<int>> V(row,col);// this is the initialization of 2d arrays

//     return 0;
// }

// Q1. to print the pascal triangle -- in this we use the formula of [nCr = n!/r!(n-r)!] this is the factorial question
// but we are using a[i][j] = a[i-1][j]+a[i-1][j-1]

vector<vector<int>> pascalTriangle(int n){
    vector<vector<int>> pascal(n);

    for(int i=0;i<n;i++){
        pascal[i].resize(i+1);// this makes the places in the vector to place the elements in the array

        for(int j=0;j<i+1;j++){
            if(j==0||j==i){
                pascal[i][j]=1;// this the boundary value statement to place [1]
            }else{
                pascal[i][j] = pascal[i-1][j]+pascal[i-1][j-1];
            }
            
        }
    }
    return pascal;
}

int main()
{
    // i would be the row and j would be the columns
    int n;
    cin>>n;

    vector<vector<int>> ans;
    ans = pascalTriangle(n);
    for(int i=0;i<ans.size();i++){
        for(int j=0;j<ans[i].size();j++){
            cout<<ans[i][j]<<" ";
        
        }cout<<endl;
    }
    
    return 0;
}
