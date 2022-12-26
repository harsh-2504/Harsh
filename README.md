#include<iostream>
#include<string.h>
using namespace std;

class Drama
{
    protected:
        char types[50];
        float rating;
    public:
        Drama(char *s,float a)
        {
            strcpy(types,s);
            rating=a;
        }
    virtual void display(){}
};

class K_Drama:public Drama
{
    protected:
        char ileuam[80];
    public:
        K_Drama(char *s,float a,char *k):Drama(s,a)
        {
            strcpy(ileuam,k);
        }
    void display();
};

class Thai_Drama:public Drama
{
    protected:
        char chux[50];
    public:
        Thai_Drama(char *s,float a,char *t):Drama(s,a)
        {
            strcpy(chux,t);
        }
    void display();
};

void K_Drama::display()
{
    cout<<"\n Type of drama:"<<types;
    cout<<"\n Name of drama:"<<ileuam;
    cout<<"\n Rating:"<<rating;
}

void Thai_Drama::display()
{
    cout<<"\n Type of drama:"<<types;
    cout<<"\n Name of drama:"<<chux;
    cout<<"\n Rating:"<<rating;
}

int main()
{
    char *types=new char[30];
    char *ileuam=new char[80];
    char *chux=new char[50];
    float rating;

    cout<<"\n ENTER K_DRAMA DRAMA DETAILS \n";
    cout<<"Type of drama:";
    cin>>types;

    cout<<"Name of drama:";
    cin>>ileuam;

    cout<<"Rating:";
    cin>>rating;

    K_Drama K(types,rating,ileuam);

    cout<<"\n ENTER THAI DRAMA DETAILS \n";
    cout<<"Type of drama:";
    cin>>types;

    cout<<"Name of drama:";
    cin>>chux;

    cout<<"Rating:";
    cin>>rating;

    Thai_Drama T(types,rating,chux);

Drama *KT[2];
KT[0]=&K;
KT[1]=&T;

cout<<"\n DRAMA DETAILS:";

cout<<"\n-------------------------DRAMA 1-----------------------------\n";
KT[0]->display();

cout<<"\n-------------------------DRAMA 2-----------------------------\n";
KT[1]->display();

return 0;
}
