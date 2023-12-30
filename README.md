#include<bits/stdc++.h>
using namespace std;

int YearToFirstDay(int year)
{
    int day=(year*365+((year-1)/4)-((year-1)/100)+((year-1)/400))%7;
    return day;

}

int main()
{
    string month[]={"JANUARY","FEBRUARY","MARCH","APRIL","MAY","JUNE","JULY","AUGUST","SEPTEMBER","OCTOBER","NOVEMBER","DECEMBER"};

    int DayPerMonth[]={31,28,31,30,31,30,31,31,30,31,30,31};

    int i,j,weekDays=0,spaceCounter,year;
    cout<<"Enter any YEAR: ";
    cin>>year;

    cout<<endl<<endl<<"             CALENDAR-"<<year<<endl<<endl;

    if(year%4==0&&year%100!=0||year%400==0)
    {
        DayPerMonth[1]=29;
    }

    weekDays=YearToFirstDay(year);

    for(i=0;i<12;i++)
    {

        cout<<endl<<"**************-"<<month[i]<<"-**************"<<endl<<endl;
        cout<<"SUN  MON  TUE  WED  THU  FRI  SAT"<<endl;

            for(spaceCounter=1;spaceCounter<=weekDays;spaceCounter++)
            {
                cout<<"     ";
            }
            for(j=1;j<=DayPerMonth[i];j++)
            {
                if(weekDays>6)
                {
                    weekDays=0;
                    cout<<endl;
                }

                weekDays++;

                if(j<=9)
                    cout<<0<<j<<"   ";
                else
                    cout<<j<<"   ";
            }

            cout<<endl;
    }

    return 0;

}
