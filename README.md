C++商品存取系统
=
#include <iostream>
#include <string>
#include <stdio.h>
using namespace std;
int n=0;
class Shang
{
private:
    int num,li;
    string name;
public:
    void display();
    void ru();
    void cha();
    void cun();
    void chu();
};
Shang t[1000];
void Shang::display()
{
    cout<<"\t"<<"******************************************"<<endl;
    cout<<"\t"<<"**                                      **"<<endl;
    cout<<"\t"<<"**       欢迎使用商品查询系统           **"<<endl;
    cout<<"\t"<<"** ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ **"<<endl;
    cout<<"\t"<<"**                                      **"<<endl;
    cout<<"\t"<<"**           1.创建商品                 **"<<endl;
    cout<<"\t"<<"**           2.查询商品                 **"<<endl;
    cout<<"\t"<<"**           3.商品出库                 **"<<endl;
    cout<<"\t"<<"**           4.商品入库                 **"<<endl;
    cout<<"\t"<<"**           0.退出                     **"<<endl;
    cout<<"\t"<<"**                                      **"<<endl;
    cout<<"\t"<<"**                                      **"<<endl;
    cout<<"\t"<<"**                                      **"<<endl;
    cout<<"\t"<<"**                请输入需要操作的编号  **"<<endl;
    cout<<"\t"<<"**                                      **"<<endl;
    cout<<"\t"<<"******************************************"<<endl;
}
void Shang::ru()
{
    n++;
    t[n].num=n;
    cout<<"请输入商品名称"<<endl;
    cin>>t[n].name;
    cout<<"请输入商品数量"<<endl;
    cin>>t[n].li;
}
void Shang::cha()
{
    int i;
    if(n==0)
        cout<<"请先创建商品"<<endl;
    else
    {
        cout<<"\t"<<"编号"<<"\t"<<"名称"<<"\t"<<"数量"<<endl;
        for(i=1; i<=n; i++)
            cout<<"\t"<<t[i].num<<"\t"<<t[i].name<<"\t"<<t[i].li<<endl;

    }
}
void Shang::chu()
{
    int b,c,i;
    cout<<"请输入取出商品编号及数量"<<endl;
    cin>>b>>c;
    for(i=1; i<=n; i++)
    {
        if(b==i)
        {
            t[i].li=t[i].li-c;
        }
    }
}
void Shang::cun()
{
    int b,c,i;
    cout<<"请输入存入商品编号及数量"<<endl;
    cin>>b>>c;
    for(i=1; i<=n; i++)
    {
        if(b==i)
        {
            t[i].li=t[i].li+c;
        }
    }
}
int main()
{
    int p;
    Shang w;
    while(1)
    {
        w.display();
        cin>>p;
        switch(p)
        {
        case 1:
            t[n].ru();
            break;
        case 2:
            t[n].cha();
            break;
        case 3:
            t[n].chu();
            break;
        case 4:
            t[n].cun();
            break;
        case 0:
            break;
        default:
            break;
        }
    }
    return 0;
}


