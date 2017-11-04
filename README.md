# Floyd

Floyd

#include <iostream>
  
#include <vector>
  
using namespace std;

#define M 301

#define LIM 200000000

int w[M][M],d[2][M][M];


void floyd(int g[M][M],int d[2][M][M],int n){

	int i,j,k;
  
	for(i=1;i<=n;i++){
  
		for(j=1;j<=n;j++){
    
			d[0][i][j]=g[i][j];
      
		}
    
		d[0][i][i]=0;
    
	}        //这里是令d[0]=g
  
	for(k=1;k<=n;k++){
  
		for(i=1;i<=n;i++)
    
			for(j=1;j<=n;j++){
      
				int t1=k%2; int t2=(t1+1)%2;
        
				d[t1][i][j]=d[t2][i][j] < d[t2][i][k]+d[t2][k][j]?d[t2][i][j]:d[t2][i][k]+d[t2][k][j];
        
			}
      
	}
  
}
