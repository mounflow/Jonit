```c
#include<iostream>
using namespace std;
int T=INT_MAX;
int temp;
int d[11][5];
int n;
int m;
void find(int dT[5])  
{  
  if(dT[3]==n)
  { 
  cout<<"sdfsdfgdsfgsd"<<temp<<endl; 
	  if(temp<T){
		  T=temp;
	  }
		  return;
  }
	for(int i=1;i<=m;i++) 
	{
      if(d[i][2]==dT[3]) 
	  {
	  if(d[i][1]==dT[1])  
		  {
             if(d[i][1]==1)   
			 {
                 int *DN=new int[5];
				 DN[1]=1;
				 DN[2]=dT[2];
				 DN[3]=d[i][3];
				 DN[4]=d[i][4]+dT[4];
				 temp=DN[4]*DN[4];
				 find(DN);
				 temp=DN[4]*DN[4];
			 }
			 else           
			 {
				 int *DN=new int[5];
				 DN[1]=0;
				 DN[2]=dT[2];
				 DN[3]=d[i][3];
				 DN[4]=temp+d[i][4];
				 temp=DN[4]; 
				 find(DN);
				 temp=DN[4]*DN[4];
			 }
		  }


		  else  
		  {
              if(dT[1]==0)
			  {
                 int *DN=new int[5];
				 DN[1]=1;
				 DN[2]=d[i][2];
				 DN[3]=d[i][3];
				 DN[4]=d[i][4];
				 temp+=DN[4]*DN[4];
				 find(DN);
				 temp=DN[4]*DN[4];
			  }
			  else
			  {
                 int *DN=new int[5];
				 DN[1]=0;
				 DN[2]=d[i][2];
				 DN[3]=d[i][3];
				 DN[4]=d[i][4];
				 temp+=DN[4]; 
				 find(DN);
				 temp=DN[4]*DN[4];	 
			  }
		  }
	  }
	}
}


int main()
{
	int i,j;
	cin>>n>>m;
    for(i=1;i<=m;i++)
	for(j=1;j<=4;j++)
      cin>>d[i][j];

	for(i=1;i<=m;i++)
	{
		if(d[1][2]!=1)
			continue;
		if(d[i][2]==1)
		{
			int *DN=new int[5];
				 DN[1]=d[i][2];
				 DN[2]=d[i][2];
				 DN[3]=d[i][3];
				 DN[4]=d[i][4];
				 temp=DN[4];
				// cout<<i<<DN[2]<<'\t'<<temp<<endl;
			     find(DN);
		}
			
	}
	cout<<T;
	return 0;
}
```
