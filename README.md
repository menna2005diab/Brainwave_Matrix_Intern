# Brainwave_Matrix_Intern
#include <iostream>
using namespace std;
//makeing an accounts class
class Account{
    private:
int accountNumber;
int balance;
public:
// setting up imaginary account
  Account(int accNum, int initialBalance = 2000) {
        accountNumber = accNum;
        balance = initialBalance;
    }
    //setting up the proccesses
void checkBalance(){
cout<<"Your current balance is "<<balance<<" $";
}
void deposit(int amount) {
        balance += amount;
        cout << "You have deposited $" << amount << ". New balance: $" << balance << endl;
    }
void withdraw(int amount){

        if(amount>balance){
            cout<<"insufficient balance";
        }
        else{
         balance-= amount;
        cout <<"You have withdrawn $"<<amount<<". New balance: $"<<balance<<endl;}
}
void transfer(int amount,int account){
     if(amount>balance){
            cout<<"insufficient balance";
        }
        else{
        balance-=amount;
        cout <<"You have transfered $"<<amount<<"to account"<<account<<". New balance: $"<<balance<<endl;}
}


};

void process(Account& Useraccount);
//declaring a class for accounts
using namespace std;
int main(){
cout <<"Please insert card"<<endl;
cout<<"please enter PIN";
int PIN;
Account Useraccount(PIN);
cin>>PIN;
process(Useraccount);


}


void process(Account& Useraccount){
    int process;
 do{
cout<<endl<<
   "1-Check balance"<<endl
<<"2-Deposit money"<<endl
<<"3-Withdraw money"<<endl
<<"4-Transfer funds"<<endl
<<"5-Exit the system"<<endl;

cin>>process;
int deposit;
int withdraw;
int transfer;
int account;
    switch (process){

case 1: Useraccount.checkBalance();
        break;
case 2: cout<<"Please enter the amount you want to deposit"<<endl;
        cin>>deposit;
        Useraccount.deposit(deposit);
break;
case 3: cout<<"Please enter the amount you want to withdraw"<<endl;
        cin>>withdraw;
        Useraccount.withdraw(withdraw);
        break;
case 4: cout<<"Please enter the amount you want to transfer"<<endl;
        cin>>transfer;
        cout<<"Please enter the account number you want to transfer to"<<endl;
        cin>>account;
        Useraccount.transfer(transfer,account);
        break;
case 5:
    cout<<"exiting the system, thank you";
    exit(0);
break;
default: cout<<"Invalid choice. Try again.";
}}while (process!=5);
}
