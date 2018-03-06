#include <bits/stdc++.h>
 
using namespace std;
bool are_distinct(int n, int p)
{
    int a,b,c,counter=0;
    set<int>st;
    int cnt=0;
    while(cnt<5)
    {
        cnt++;
        a=n/10;
        b=a*10;
        c=n-b;
        st.insert(c);
        n=a;
    }
    cnt=0;
    while(cnt<5)
    {
        cnt++;
        a=p/10;
        b=a*10;
        c=p-b;
        st.insert(c);
        p=a;
    }
    bool w,y;
    int r=st.size();
    if(r==10)
        return true;
    else
        return false;
}
int main()
{
    int N;
    bool onecase=false;
    while(cin>>N&&N)
    {
        if(onecase)
            cout<<endl;
        onecase=true;
        int cnt,ans;
         bool chc,exist=false;
            for(int k=0; k<=9; k++)
    {
        for(int l=0; l<=9; l++)
        {
           for(int m=0; m<=9; m++)
            {
                for(int n=0; n<=9; n++)
                {
                    for(int o=0; o<=9; o++)
                    {
                            cnt=(k*10000)+(l*1000)+(m*100)+(n*10)+(o*1);
                            if(cnt%N==0){
                                ans=cnt/N;
                                chc=are_distinct(cnt,ans);
 
                                if(chc)
                                {
                                    if(ans<10000 && cnt<10000)
                                    {
                                        exist=true;
                                        cout<<0<<cnt<<" / "<<0<<ans<<" = "<<N<<endl;
                                    }
                                    else if(ans>=10000 && cnt<10000)
                                    {
                                        exist=true;
                                        cout<<0<<cnt<<" / "<<ans<<" = "<<N<<endl;
                                    }
                                    else if(ans<10000 && cnt>=10000)
                                    {
                                        exist=true;
                                        cout<<cnt<<" / "<<0<<ans<<" = "<<N<<endl;
                                    }
                                    else
                                    {
                                         exist=true;
                                        cout<<cnt<<" / "<<ans<<" = "<<N<<endl;
                                    }
 
                        }
                    }
                }
            }
        }
    }
}
    if(exist==false)
        cout<<"There are no solutions for "<<N<<"."<<endl;
 
    }
 
    return 0;
}
