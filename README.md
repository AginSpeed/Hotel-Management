# Hotel-Management
char newpass[20],  cdate[32][13];
int m=4;
#include<iostream.h>
#include<conio.h>
#include<stdio.h>
#include<stdlib.h>
#include<fstream.h>
#include<time.h>
#include<iomanip.h>
#include<math.h>
#include<ctype.h>
#include<process.h>
#include<string.h>
void check();
void load();
void choice();
void ad();
void memselection();
struct date
{
 char cfname[20],clname[20];
 int smon,emon;
 int sdate,edate;
}dd;
class Room
{
 int roomno;
 char roomtype[20];
 int ac;
 float fare;
 float totfare;

 char cfname[20],clname[20];
 char gender;
 char nation[20];
 long phno;
 int nomember;

 char mon[13][32];

 struct address
 {
  int bldg,road,block;
  char place[20];
 }a;
 public:
  int retroom();
  void retddate();
  Room();
  void getinfo(int,int,int,int,int);
  void copyname(int sdate,int edate,int smon,int emon)
  {
   strcpy(dd.cfname,cfname);
   strcpy(dd.clname,clname);
   dd.smon=smon;
   dd.emon=emon;
   dd.sdate=sdate;
   dd.edate=edate;
   ofstream file;
   file.open("entry.dat",ios::app | ios::binary);
   file.write((char*)&dd,sizeof(dd));
  }
};
int Room::retroom()
{
 return roomno;
}
void Room::retddate()
{
 for(int x=1;x<13;x++)
 for(int i=1;i<32;i++)
 {
  cdate[x][i]=mon[x][i];
 }
}
void Room::getinfo(int rno,int sdate,int edate,int smon,int emon)
{
 int k=0;
 roomno=rno;
 cout<<"The Room number is                 :"<<roomno<<endl;
 cout<<"Enter the Customer First Name      :";
 gets(cfname);
 cout<<"Enter the Customer Last Name       :";
 gets(clname);
 cout<<"Enter the Gender of the Customer   :";
 cin>>gender;
 cout<<"Enter the Number of Customers      :";
 cin>>nomember;
 cout<<"Enter the Nationality              :";
 gets(nation);
 cout<<"Enter the Phone number             :";
 cin>>phno;
 if(sdate<edate)
 {
  k=sdate;
  while(k<=edate)
  {
   mon[smon][k]='Y';
   k++;
  }
 }
 if(sdate>edate)
 {
  k=1;
  while(k<=edate)
  {
   mon[emon][k]='Y';
   k++;
  }
  k=sdate;
  while(k<=31)
  {
   mon[smon][k]='Y';
   k++;
  }
 }
 cout<<"Enter the Address below           :";
}
Room::Room()
{
 for(int j=1;j<=12;j++)
 for(int i=1;i<32;i++)
 {
  mon[j][i]='N';
 }
}
void grey(long n)
{
 for(long x=0;x<n;x++)
 {}
}
void delay()
{
 for(long x=0;x<92500;x++)
 {}
}
void delay1()
{
 for(double long x=0;x<725000;x++)
 {}
}
void delay2()
{
 for(double long x=0;x<925000;x++)
 {}
}
void slow()
{
 for(long x=0;x<525000;x++)
 {}
}
void stop()
{
 for(long x=0;x<99999999;x++)
 {}
}
void main()
{
 randomize();
 for(int k=12,i=13;k>=1,i<=25;k--,i++)
 for(int j=40,l=41;j>=1,l<=79;j--,l++)
 {
  gotoxy(j,k);
  cout<<random(9);
  gotoxy(l,k);
  cout<<random(9);
  gotoxy(j,i);
  cout<<random(9);
  gotoxy(l,i);
  cout<<random(9);
  slow();
 }
 for(i=12,j=13;i>=1,j<26;i--,j++)
 {
  gotoxy(1,i);
  cout<<"";
  gotoxy(79,j);
  cout<<"";
  delay2();
 }
 for(i=0,j=79;i<80,j>=1;i++,j--)
 {
  gotoxy(i,1);
  cout<<"";
  gotoxy(j,25);
  cout<<"";
  delay1();
 }
 for(i=1,j=25;i<13,j>12;i++,j--)
 {
  gotoxy(1,j);
  cout<<"";
  gotoxy(79,i);
  cout<<"";
  delay2();
 }
 stop();
 for(i=2;i<=78;i++)
 {
  for(j=2;j<=24;j++)
  {
   gotoxy(i,j);
   if(j==3 || j==9)
   {
    if(i==24 || i==30 || i==32 || i==33 || i==34 || i==35 || i==36 || i==37 || i==38 || i==40 || i==41)
    cout<<"";
    if(i==42 || i==43 || i==44 || i==45 || i==46 || i==48 || i==49 || i==50 || i==51 || i==52 || i==53)
    cout<<"";
    if(i==54 || i==56)
    cout<<"";
    if(j==9)
    {
     if(i==40 || i==41 || i==42 || i==44 || i==45 || i==46)
     {
      cout<<" ";
     }
     if(i==57 || i==58 || i==59 || i==60 || i==61 || i==62)
     {
      cout<<"";
     }
     else
     cout<<" ";
    }
    else
    cout<<" ";
   }
   else if(j==4 || j==5 || j==7 || j==8)
   {
    if(i==24 || i==30 || i==32 || i==38 || i==43 || i==48 || i==56)
    {
     cout<<"";
    }
    else
    cout<<" ";
   }
   else if(j==6)
   {
    if(i==24 || i==25 || i==26 || i==27 || i==28 || i==29 || i==30 || i==32 || i==38 || i==43 || i==48)
    {
     cout<<"";
    }
    if(i==49 || i==50 || i==51 || i==52 || i==56)
    {
     cout<<"";
    }
    else
    cout<<" ";
   }
   else if(j==12)
   {
    if(i==36)
    cout<<"W";
    if(i==37 || i==42)
    cout<<"E";
    if(i==38)
    cout<<"L";
    if(i==39)
    cout<<"C";
    if(i==40 || i==45)
    cout<<"O";
    if(i==41)
    cout<<"M";
    if(i==44)
    cout<<"T";
    else
    cout<<" ";
   }
   else if(j==13)
   {
    if(i==33)
    cout<<"H";
    if(i==34)
    cout<<"O";
    if(i==35 || i==48)
    cout<<"T";
    if(i==36 || i==44 || i==46)
    cout<<"E";
    if(i==37)
    cout<<"L";
    if(i==39 || i==45)
    cout<<"M";
    if(i==40 || i==42)
    cout<<"A";
    if(i==41 || i==47)
    cout<<"N";
    if(i==43)
    cout<<"G";
    else
    cout<<" ";
   }
   else
   cout<<" ";
  }
  grey(4250000);
  gotoxy(36,11);
 }
 stop();
 stop();
 stop();
 stop();
 clrscr();
 check();
}
void check()
{
 for(int i=12,j=13;i>=1,j<26;i--,j++)
 {
  gotoxy(1,i);
  cout<<"";
  gotoxy(79,j);
  cout<<"";
 }
 for(i=0,j=79;i<80,j>=1;i++,j--)
 {
  gotoxy(i,1);
  cout<<"";
  gotoxy(j,25);
  cout<<"";
 }
 for(i=1,j=25;i<13,j>12;i++,j--)
 {
  gotoxy(1,j);
  cout<<"";
  gotoxy(79,i);
  cout<<"";
 }
 ifstream file;
 file.open("Pass1.txt");
 file>>newpass;
 gotoxy(2,3);
 for(i=2;i<79;i++)
 cout<<"_";
 gotoxy(33,2);
 cout<<"PLEASE LOGIN"<<endl;
 stop();
 stop();
 char user[20],pass[20],ch;
 back:
 gotoxy(53,9);
 cout<<" ----------------------- ";
 gotoxy(53,10);
 cout<<"|                       |";
 gotoxy(53,11);
 cout<<"|                       |";
 gotoxy(53,12);
 cout<<"|                       |";
 gotoxy(53,13);
 cout<<"|                       |";
 gotoxy(53,14);
 cout<<"|                       |";
 gotoxy(53,15);
 cout<<"|                       |";
 gotoxy(53,16);
 cout<<" ----------------------- ";
 gotoxy(55,11);
 cout<<"USERNAME: ";
 gotoxy(65,11);
 cout<<"          ";
 gotoxy(55,13);
 cout<<"PASSWORD: ";
 gotoxy(65,13);
 cout<<"          ";
 int k=65;
 gotoxy(k,11);
 for(i=0;i<11;i++)
 {
  ch=getch();
  if(ch!=13)
  {
   if(ch==8)
   {
    k--;
    if(k<65)
    {
     k=65;
     gotoxy(k,11);
     i=-1;
    }
    else
    {
     cout<<'\b';
     i=i-2;
    }
   }
   else
   {
    k++;
    user[i]=ch;
    cout<<ch;
   }
  }
  else
  {
   k++;
   user[i]='\0';
   break;
  }
 }
 k=65;
 gotoxy(k,13);
 for(i=0;i<11;i++)
 {
  ch=getch();
  if(ch!=13)
  {
   if(ch==8)
   {
    k--;
    if(k<65)
    {
     gotoxy(65,13);
     k=65;
     i=-1;
    }
    else
    {
     cout<<'\b';
     i=i-2;
    }
   }
   else
   {
    k++;
    pass[i]=ch;
    cout<<".";
   }
  }
  else
  {
   pass[i]='\0';
   break;
  }
 }
 if(strcmpi("agje",user)==0 && strcmp(newpass,pass)==0)
 {
  load();
  choice();
 }
 if(strcmpi("agje",user)==0 && strcmp(pass,"fast")==0)
 {
  choice();
 }
 if(strcmpi("admin",user)==0 && strcmp("admin",pass)==0)
 {
  clrscr();
  cout<<"The the admin choice function is under construction";
 }
 else
 {
  m--;
  for(int w=2;w<20;w++)
  for(int z=10;z<18;z++)
  {
   gotoxy(w,z);
   cout<<" ";
  }
  if(m>0)
  {
   cout<<'\a';
   gotoxy(5,9);
   if(m==3)
   {
    cout<<"No.of tries remaining!";
    gotoxy(3,10);
    cout<<"          * *   ";
    gotoxy(3,11);
    cout<<"         *   *  ";
    gotoxy(3,12);
    cout<<"             *  ";
    gotoxy(3,13);
    cout<<"            *   ";
    gotoxy(3,14);
    cout<<"             *  ";
    gotoxy(3,15);
    cout<<"         *   *  ";
    gotoxy(3,16);
    cout<<"          * *   ";
   }
   if(m==2)
   {
    cout<<"No.of tries remaining!";
    gotoxy(3,10);
    cout<<"                   ";
    gotoxy(3,11);
    cout<<"           * *     ";
    gotoxy(3,12);
    cout<<"          *   *    ";
    gotoxy(3,13);
    cout<<"          *   *    ";
    gotoxy(3,14);
    cout<<"             *     ";
    gotoxy(3,15);
    cout<<"            *      ";
    gotoxy(3,16);
    cout<<"          *****    ";
   }
   if(m==1)
   {
    cout<<"No.of tries remaining!";
    gotoxy(3,10);
    cout<<"                   ";
    gotoxy(3,11);
    cout<<"            *      ";
    gotoxy(3,12);
    cout<<"           **      ";
    gotoxy(3,13);
    cout<<"          * *      ";
    gotoxy(3,14);
    cout<<"            *      ";
    gotoxy(3,15);
    cout<<"            *      ";
    gotoxy(3,16);
    cout<<"           ***     ";
   }
   goto back;
  }
  if(m==0)
  {
   clrscr();
   gotoxy(30,12);
   cout<<"Sorry Authorized Entry only!";
   stop();
   stop();
   stop();
   clrscr();
   gotoxy(35,12);
   cout<<"Have a nice day!";
  }
 }
}
void load()
{
 clrscr();
 gotoxy(30,12);
 cout<<" __________________________ ";
 gotoxy(30,13);
 cout<<"|                          |";
 gotoxy(30,14);
 cout<<" -------------------------- ";
 int k=31;
 for(int i=0;i<101;i++)
 {
  for(int j=0;j<10;j++)
  {
   if(i<100)
   {
    gotoxy(42,15);
    cout<<i<<"."<<j<<" %";
    slow();
   }
   else
   {
    gotoxy(42,15);
    cout<<i<<".0 %";
   }
  }
  if(i%4==0)
  {
   gotoxy(k,13);
   cout<<"";
   k++;
  }
 }
 stop();
 stop();
 stop();
 clrscr();
 gotoxy(35,12);
 cout<<"Loading...";
 stop();
 stop();
 stop();
 stop();
 stop();
 stop();
 clrscr();
 char a;
 gotoxy(1,23);
 for(i=0;i<80;i++)
 cout<<"_";
 gotoxy(1,24);
 cout<<"***************************|PRESS ENTER TO CONTINUE|***************************";
 while(a)
 {
  if(kbhit())
  {
   a=getch();
   if(a==13)
   break;
  }
  else
  {
   gotoxy(33,12);
   cout<<"**|Load Complete!|**";
   slow();
   slow();
   slow();
   slow();
   gotoxy(33,12);
   cout<<"                    ";
   slow();
   slow();
   slow();
   slow();
  }
 }
}
void ad()
{
 for(int a=8;a<26;a++)
 for(int b=3;b<78;b++)
 {
  gotoxy(b,a);
  cout<<" ";
 }
 gotoxy(1,12);
 cout<<"4";
 gotoxy(79,12);
 cout<<"6";
 gotoxy(43,3);
 cout<<"SEARCH";
 gotoxy(50,2);
 cout<<"    ";
 gotoxy(50,3);
 cout<<"                     ";
 gotoxy(50,4);
 cout<<" ''   ";
 gotoxy(50,5);
 cout<<"                      ''  ";
}
void choice()                                      //RECEIPTIONIST Choice
{
 first:
 clrscr();
 for(int d=1;d<80;d++)
 {
  gotoxy(d,1);
  cout<<"*";
 }
 for(d=1;d<80;d++)
 {
  gotoxy(d,7);
  cout<<"*";
 }
 for(d=1;d<8;d++)
 {
  gotoxy(1,d);
  cout<<"*";
  gotoxy(79,d);
  cout<<"*";
 }
 struct tm *ptr;
 time_t t;
 t=time(NULL);
 char str[100];
 ptr=localtime(&t);
 gotoxy(7,3);
 strftime(str,100,"%A %B ",ptr);
 cout<<str<<ptr->tm_year+1900;
 gotoxy(11,4);
 cout<<ptr->tm_mday<<"-"<<ptr->tm_mon+1<<"-"<<ptr->tm_year+1900;
 gotoxy(30,4);
 strftime(str,100,"%I:%M %p",ptr);
 cout<<str;
 char choice[20][20];
 strcpy(choice[0],"CHECK IN");
 strcpy(choice[1],"ALL FACILITIES");
 strcpy(choice[2],"CHECK OUT");
 strcpy(choice[3],"MODIFY");
 strcpy(choice[4],"REPORTS");
 strcpy(choice[5],"REFRESH");
 strcpy(choice[6],"CHANGE PASSWORD");
 strcpy(choice[7],"RESTART PROGRAM");
 strcpy(choice[8],"EXIT");
 int x=0;
 char bb;
 ad();
 gotoxy(35,12);
 cout<<choice[x];
 w:
 gotoxy(33,12);
 cout<<"->";
 gotoxy(34,12);
 bb=getch();
 if(bb==52)
 {
  x--;
  if(x<0)
  {
   ad();
   x=7;
   gotoxy(35,12);
   cout<<choice[x];
   goto w;
  }
  else
  {
   ad();
   gotoxy(35,12);
   cout<<choice[x];
   goto w;
  }
 }
 else if(bb==54)
 {
  x++;
  if(x>7)
  {
   ad();
   x=0;
   gotoxy(35,12);
   cout<<choice[x];
   goto w;
  }
  else
  {
   ad();
   gotoxy(35,12);
   cout<<choice[x];
   goto w;
  }
 }
 else if(bb=='s' || bb=='S')
 {
  gotoxy(51,3);
  char ser[10];
  getch();
  exit(0);
 }
 else if(bb==13)
 {
  if(x==0)
  {
   int k;
   long pos;
   int check=0;
   Room r;
   int rno,sdate,edate,croom;
   int smon,emon;
   clrscr();
   cout<<"Enter the room no        :";
   cin>>rno;
   if(rno<=120 && rno>=101)
   {
    cout<<"Enter the Starting Date :";
    cin>>sdate;
    cout<<"Enter the Ending Date   :";
    cin>>edate;
    cout<<"Enter the Starting Month:";
    cin>>smon;
    cout<<"Enter the Ending Month  :";
    cin>>emon;
    fstream file;
    file.open("Roomchec.dat",ios::in | ios::out | ios::binary);
    file.seekg(0);
    while(file.read((char*)&r,sizeof(r)))
    {
     pos=file.tellg();
     if(rno==r.retroom())
     {
      cout<<"I'm in!"<<endl;
      r.retddate();
      if(sdate<edate)
      {
       k=sdate;
       while(k<=edate)
       {
	if(cdate[smon][k]=='Y')
	{
	 check=1;
	 break;
	}
	k++;
       }
       if(check==1)
       {
	cout<<"That room is already taken";
       }
       else
       {
	cout<<"That is a good room for you!";
	cout<<endl<<"Now you enter the details...";
	getch();
	clrscr();
	r.getinfo(rno,sdate,edate,smon,emon);
	file.seekp(pos-sizeof(r));
	file.write((char*)&r,sizeof(r));
       }
      }
      if(sdate>edate)
      {
       k=1;
       while(k<=edate)
       {
	if(cdate[emon][k]=='Y')
	{
	 check=1;
	 break;
	}
	k++;
       }
       k=sdate;
       while(k<=31)
       {
	if(cdate[smon][k]=='Y')
	{
	 check=1;
	 break;
       }
	k++;
       }
       if(check==1)
       {
	cout<<"That room is already taken";
       }
       else
       {
	cout<<"That is a good room for you!";
	cout<<endl<<"Now you enter the details...";
	getch();
	clrscr();
	r.getinfo(rno,sdate,edate,smon,emon);
	file.seekp(pos-sizeof(r));
	file.write((char*)&r,sizeof(r));
       }
      }
      if(sdate==edate)
      {
       cout<<"They both are same";
      }
      r.copyname(sdate,edate,smon,emon);
     }
    }
   }
   else
   {
    clrscr();
    cout<<"Sorry that room does not exist!";
    exit(0);
   }
  }
  if(x==1)
  {
  }
  if(x==2)
  {
  }
  if(x==3)
  {
  }
  if(x==4)
  {
  }
  if(x==5)
  {
   randomize();
   int j=0,k=0;
   for(int i=0;i<14000;i++)
   {
    j=random(79+1);
    k=random(25+1);
    gotoxy(j,k);
    cout<<"*";;
    delay();
   }
   goto first;
  }
  if(x==6)
  {
  }
  if(x==7)
  {
  }
  if(x==8)
  {
  }
 }
 else
 {
  gotoxy(38,24);
  cout<<"Not Possible";
  stop();
  stop();
  gotoxy(38,24);
  cout<<"            ";
  goto w;
 }
 exit(0);
}
