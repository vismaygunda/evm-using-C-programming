# evm-using-C-programming
#created a simple virtual voting machine using basics of C programming

#include<stdio.h>
struct voter
{
    int age;
    int voter_id;
    char name[10];
    char sex[10];
    int secret_code;
}s[];
void main()
{
    int i,n,a=0,k,b=0,c=0,sec,v;
    long int secret_code=91378;
    printf("\nwelcome to VIRTUAL VOTING MACHINE!\n");
    printf("\nenter total number of voters:");
    scanf("%d",&v);
    for(i=0;i<=v-1;i++)
    {
        printf("\n\nvoter %d information\n\n",i+1);
        printf("\nenter the name:");
        scanf("%s",&s[i].name);
        printf("\nenter the age:");
        scanf("%d",&s[i].age);
        getchar();
        if(s[i].age<18)
            {
                printf("\nunable to vote! since age issues!\n\n");
            }
        else
            {
                printf("\nenter the sex m/f:");
                scanf("%c",&s[i].sex);
                printf("\nenter the voter id:");
                scanf("%d",&s[i].voter_id);
                s[i].secret_code=secret_code*17+1;
                secret_code++;
                printf("\nyour secret code for voting:%d\n\n",s[i].secret_code);
            }
    }

    printf("\nVARNASI LOK SABHA ELECTIONS 2019!\n");
    printf("\nPARTICIPANTS\n1.MODI\n2.RAHUL GANDHI\n3.ARVIND KEJRIVAL\n");
    for(k=0;k<v;k++)
    {
        if(s[k].age>=18)
        {
            printf("\nenter person %d secret code=",k+1);
            scanf("%d",&sec);
            if(sec==s[k].secret_code)
            {
                printf("\nenter your choice:");
                scanf("%d",&n);
                switch(n)
                {
                    case 1:printf("\nthanks for voting");
                            a++;
                            break;
                    case 2:printf("\nthanks for voting");
                            b++;
                            break;
                    case 3:printf("\nthanks for voting");
                            c++;
                            break;
                    default:printf("\ninvalid vote");
                }
            }
            else
                printf("secret code of voter %d doesnot match!",k+1);

        }


    }
            if(a>b&&a>c)
            {
                printf("\nMODI won the elections! with %d votes",a);

            }
            else if(b>a&&b>c)
            {
                printf("\nRAHUL GANDHI won the elections! with %d votes",b);
            }
            else if(a==b&&a>c)
            {
                printf("\nMODI and RAHUL GANDHI ties up");
            }
            else if(a==c&&a>b)
            {
                printf("\nMODI and ARVIND KEJRIVAL ties up");
            }
            else if(b==c&&b>a)
            {
                printf("\nRAHUL GANDHI and ARVIND KEJRIVAL ties up");
            }
            else if(a==b&&a==c)
            {
                printf("\nMODI,RAHUL GANDHI AND ARAVIND KEJRIWAL ties up");
            }
            else
            {
                printf("\nARVIND KEJRIVAL won the elections with %d votes",c);
            }
            printf("\nvoting list:");
            printf("\nNARENDRA MODI:%d",a);
            printf("\nRAHUL GANDHI:%d",b);
            printf("\nARVIND KEJRIVAL:%d",c);
}



