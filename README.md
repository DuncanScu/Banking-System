# Banking-System
#include <iostream>
#include <string>
#include <stdio.h>
#include <time.h> 
#include <stdlib.h>

using namespace std;

//Prototyping
    string name{};
    int initial_dep{};
    int balance{};
    int deposite{};
    int with{};
    int randomNum{};

    void create_account(); //Funtion to get user data
    void show_account(); //Function to show account data
    void dep(int); //Function to add currency
    void withdraw(int); //Function to withdraw currency
    void create_accNum(); //Function to create account number

void create_account(){
    cout<<"Enter The Name Of The Account Holder: ";
    cin.ignore();
    getline(cin, name);
    cout<<endl;
    cout<<"What would you like as an initial deposite: ";
    cin>>initial_dep;

    
}
void show_account(){
    cout<<"Name: "<<"'"<<name<<"'"<<endl;
    cout<<"Account Number: "<<randomNum<<endl;
    cout<<"Current Balance: "<<balance<<endl;

}
void dep(){
    cout<<"Enter Deposite Amount: ";
    cin>>deposite;
    cout<<"Your deposite was accepted"<<endl;
    cout<<"Your New Balance is: "<<balance + deposite<<endl;
    balance += deposite;
}
void withdraw() {
    cout<<"Your Balance: "<<balance<<endl;
    cout<<"Enter the amount you would like to withdraw: ";
    cin>>with;
    if (with > balance){
        cout<<"Sorry, you can not withdraw more than you have"<<endl;

    }else{
        balance -= with;
        cout<<" Your new balance is: "<<balance<<endl;
    }

}
void create_accNum(){
    srand (time(NULL));
    randomNum = rand() % 100000 +999999;
    cout<<"Account Number: "<<randomNum<<endl;
}

int main(){
    
cout<<"**********************************"<<endl;
cout<<"Welcome to Duncan's Banking System"<<endl;
cout<<"**********************************"<<endl;

int action{};

//Menu 
do{
cout<<"1) New Account"<<endl;
cout<<"2) Make A Deposite"<<endl;
cout<<"3) Make A Withdrawal"<<endl;
cout<<"4) Current Balance"<<endl;
cout<<"5) Close Account"<<endl;
cout<<"6) Account Details"<<endl;
cout<<"7) Quit"<<endl;
cin>>action;
cout<<endl;
switch (action)
{
case 1:
    /* New Account */
    create_account();
    create_accNum();
    break;
case 2:
    /* Make a Deposite */
    dep();
    break;
case 3:
    /* Make A Withdrawal */
    withdraw();
    break;
case 4:
    /* Current Balance */
    cout<<balance<<endl;
    break;
case 5:
    /* Close Account */
    break;
case 6:
    /*Account Details*/
    cout<<"Account Holder Name: "<<name<<endl;
    cout<<"Account Number: "<<randomNum<<endl;
    cout<<"Balance: "<<balance<<endl;
    break;
case 7:
    cout<<"Goodbye"<<endl;
    break;

default:
    break;
}

}while (action !=7);




return 0;
}
