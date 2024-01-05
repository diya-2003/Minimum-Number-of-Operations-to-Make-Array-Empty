#include <stdio.h>
int check(int*s,int l) {
    int i,j,temp,k,m,count=0;
    for(i=0;i<l;i++){
	    if(s[i]!=-1){
		for (j=i+1,temp=s[i],s[i]=1;j<l;j++){
		    if(temp==s[j]){
		    	s[j]=-1;
		    	s[i]++;
		    }
		}
		if(s[i]==1)
		   return -1;
		else{
			if(s[i]%3 == 0){
				count+=s[i]/3;
			}
			else if(s[i]%2 == 0){
				count+=s[i]/2;
			}
			else{
				count+=s[i]/3;
				temp=s[i]%3;
				count+=temp/2;
			}
		}
	}
    }
    return count;
}
int main(){
    int n=9,s[]={2, 3, 3, 2, 2, 4, 2, 3, 4};
    int result=check(s, n);
    printf("\nMinimum number of operation:%d",result);
    return 0;
}
