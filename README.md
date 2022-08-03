

import java.util.Scanner;
import java.time.LocalDate;
 

class Banking_Data{

//instance private variables
public String bank_Name;
private String name;
private long ac_No;
private long mobile_No;
private String email;
public String ifsc_Code;
public String branch;
private String account_Type;
public double min_Balance = 1000.0;
private double deposit;
private double withdraw;
private double transfer;
private double totalBalance = min_Balance;
private String nomini;
//mini statement purpse
double[] mini = new double[1000];
int i=0;

//instance methods using setter and getters. setter means set the value and getter means get the value.
public String getBankName(){
	return bank_Name;
}

public void setBankName(String bank_Name){
	this.bank_Name = bank_Name;
}

public String getName(){
	return name;
}

public void setName(String name){
	this.name = name;
}

public long getAcNo(){
	return ac_No;
}

public void setAcNo(long ac_No){
	this.ac_No = ac_No;
}

public long getMobile(){
	return mobile_No;
}

public void setMobile(long mobile_No){
	this.mobile_No = mobile_No;
}

public String getEmail(){
	return email;
}

public void setEmail(String email){
	this.email = email;
}

public String getIfsc(){
	return ifsc_Code;
}

public void setIfsc(String ifsc_Code){
	this.ifsc_Code = ifsc_Code;
}

public String getBranch(){
	return branch;
}

public void setBranch(String branch){
	this.branch = branch;
}


public String getAccountType(){
	return account_Type;
}

public void setAccountType(String account_Type){
	this.account_Type = account_Type;
}

public double getDeposit(){
	this.mini[i] = deposit;
	this.i++;
	return deposit;
}

public void setDeposit(double deposit){
	this.deposit = deposit;
}

public double getWithdraw(){
	this.mini[i] = withdraw;
	this.i++;
	return withdraw;
}

public void setWithdraw(double withdraw){
	this.withdraw = withdraw;
}

public double getTransfer(){
	this.mini[i] = transfer;
	this.i++;
	return transfer;
}

public void setTransfer(double transfer){
	this.transfer = transfer;
}

public double getTotalBalance(){
	this.mini[i] = totalBalance;
	this.i++;
	return totalBalance;
}

public void setTotalBalance(){
	this.totalBalance += deposit - withdraw - transfer;
}

public String getNomini(){
	return nomini;
}

public void setNomini(String nomini){
	this.nomini = nomini;
}

LocalDate date = LocalDate.now();

//display methods
//for profile
public void profile_Display(){
	System.out.println(name+"\t"+ac_No+"\t"+account_Type+"\t"+ bank_Name+"\t"+branch+"\t"+ifsc_Code+"\t"+mobile_No+"\t"+nomini);
}
//for transactions
public void transaction_Display(){
System.out.println("NAME \t\t AC_NUM \t\t Date \t\t  DEPOSIT \t\t WITHDRAW \t\t TRANSFER \t\t TOTAL BALANCE");
System.out.println(name+"\t\t"+ac_No+"\t\t"+date+"\t\t"+deposit+"\t\t"+withdraw+"\t\t\t"+transfer+"\t\t\t"+totalBalance);
}

}

//main class
public class Bank_Application{
Scanner sc = new Scanner(System.in);

public static void main(String[] args){ //main method start
Scanner sc = new Scanner(System.in);

//Banking_Data data = new Banking_Data(); //object creation for user defined class

Bank_Application app = new Bank_Application(); //object creation for main class

System.out.println("Welcome to NetBanking Application");
/*
//creation user name and password from user.
System.out.println("\n Create User Name & PassWord.Password must contains atleast 8 characters within 1 upper case and lower case letter 1 special charater 1 numeric value.");

System.out.print(" Create User Name:");

String uName = sc.next();

System.out.print(" Create User PassWord:");

String uPassword = sc.next();
System.out.println("your username and password created successfully.");
*/

//i have taken two user credentials.to store in database
//one user credentials in database
String uName = "Techmahendra";
String uPassword = "Tech@143";


//another user credentials in database
String vName = "Javadeveloper";
String vPassword = "java@7799";

//enter user name and password for validation of credentials
System.out.print(" Enter Your User Name:");

String userName = sc.next();

System.out.print("\n Enter Your User PassWord:");

String userPassword = sc.next();

//check validation 
if((uName.equals(userName))&&(uPassword.equals(userPassword))){  
     System.out.println("Hello!, Welcome To Net Banking Services.");
	  app.setVamsi();
	  app.dashBoard();
	
	 
}else if((vName.equals(userName))&&(vPassword.equals(userPassword))){
	 System.out.println("Hello!, Welcome To Net Banking Services." );
	 app.setKrishna();
	 app.dashBoard();
	 
}else{
	 System.out.println("you are entered credentials are not matched.please check and enter correct credentials.");
    }
	sc.close();
}//main method close
Banking_Data data = new Banking_Data(); 
//screen display and perform operations
 public void dashBoard(){
	System.out.println("select which operation do you want to perform");
    System.out.println("1.Profile 	2.Balance Enquery \n3.Deposit	 4.Withdraw \n5.Fund Tranfer  6.Account Statement \n7.Eminities	8.exit");     System.out.print("enter key:");
     int key = sc.nextInt();
     switch(key){
	   case 1: System.out.println("\nyou are selected profile page.");
			   System.out.println("NAME \t ACCOUNT_NUM \t ACCOUNT TYPE \t BANK NAME \t BRANCH \t IFSC \t      MOBILE_NUM \t NOMINI");
			   getProfile();
			   changePassword();
			   break;
			   
	   case 2:System.out.println("you are selected Balance Enquery.");
				methodBalance();
				getTransaction();
				methodExit();
				break;
				
	   case 3:System.out.println("you are selected Amount Deposit.");
				methodDeposit();
				getTransaction();
				methodExit();
				break;
				
	   case 4:System.out.println("you are selected Amount Withdraw.");
				methodWithdraw();
				getTransaction();
				methodExit();
				break;
				
	   case 5:System.out.println("you are selected Fund Transfer.");
				methodTransfer();
			    getTransaction();
				methodExit();
				break;
				
	   case 6: System.out.println("you are selected Account statement.");
				for(int j=0; j<data.i; j++){
					//getTransaction();
				System.out.print("\n"+data.mini[j]);
				}
				methodExit();
				break;
				
	   case 7: System.out.println("you are selected Eminities.");
				methodEminities();
				break;
		
	   default : System.exit(0);
				
       }
   
}

//set vamsi details through user defined class
 public void setVamsi(){
	data.setBankName("Andhra Bank");
	data.setName("N VAMSI");
	data.setAcNo(44410100010660l);
	data.setAccountType("Saving Account");
	data.setMobile(7793923253l);
	data.setBranch("vijayawada");
	data.setIfsc("ANDB0444");
	data.setNomini("Naga Lakshmi");
}
//set krishna details through user defined class
 public void setKrishna(){
	data.setBankName("Axis Bank");
	data.setName("K Krishna");
	data.setAcNo(123452233012l);
	data.setAccountType("Current Account");
	data.setMobile(9923564215l);
	data.setBranch("Secundrabad");
	data.setIfsc("AXIS0123");
	data.setNomini("Eswara Rao");	
}
//get profile through user defined class
public void getProfile(){
	data.getBankName();
	data.getName();
	data.getAcNo();
	data.getAccountType();
	data.getMobile();
	data.getBranch();
	data.getIfsc();
	data.getNomini();
	data.profile_Display();
}
//get transaction details through user defined class
public void getTransaction(){
	data.getName();
	data.getAcNo();
	data.getDeposit();
	data.getWithdraw();
	data.getTransfer();
	data.getTotalBalance();
	data.transaction_Display();
}

//method for totalBalance used in switch case
public void methodBalance(){
	data.setDeposit(0.0);
	data.setWithdraw(0.0);
	data.setTransfer(0.0);
	data.setTotalBalance();
}

//method for deposit used in switch case
public void methodDeposit(){
	System.out.println("Enter deposit amount");
	double amount = sc.nextDouble();
	data.setDeposit(amount);
	data.setWithdraw(0.0);
	data.setTransfer(0.0);
	data.setTotalBalance();
}
	
//method for withdraw used in switch case
public void methodWithdraw(){
	System.out.println("Enter Withdraw Amount:");
	while(true){
		double draw = sc.nextDouble();
		data.setDeposit(0.0);
		data.setTransfer(0.0);
		data.setTotalBalance();
		if(draw <= data.getTotalBalance()){
		data.setWithdraw(draw);
		data.setTotalBalance();
		break;
	   }else{
		System.out.println("insuffient balance in your account.enter less amount:");
	   }
	}
}

//method for transfer used in switch case
public void methodTransfer(){
	System.out.println("Enter Benificiary Name:");
	String b_Name = sc.next();
	while(true){
	System.out.println("Enter Benificiary Account Number:");
	  long num1 = sc.nextLong();
      if( num1 != data.getAcNo()){
		while(true){
			System.out.println("Re-Enter Benificiary Account Number:");
			long num2 = sc.nextLong();
			if( num1 == num2){
			  while(true){
				System.out.println("Enter Benificiary mobile Number:");
				String phone = sc.next();
				if(phone.length() == 10){
					while(true){
				      System.out.println("Enter Transfer Amount:");
					  double trf = sc.nextDouble();
					  data.setWithdraw(0.0);
					  data.setDeposit(0.0);
					  data.setTotalBalance();
					  if(trf <= data.getTotalBalance()){
						   data.setTransfer(trf);
						   data.setTotalBalance();
					  System.out.println("your taransaction is successful.Amount transfer to "+ num1 +" Account Number.");
					  break;
					  }else{
						System.out.println("insuffient balance in your account.enter less amount:");
					  }
					}	
				break;
				}else{
					System.out.println("your entered mobile number is invalid.\n RE-Enter mobile Number:");
				}
			 }
				break;
			
                }else{
					System.out.println("your entered Account number is mismatch.\n RE-Enter Account Number:");
				   }
		}break;
	    }else{
			System.out.println("your entered Account number is invalid.that is your account number");
		}
	}
}

//method for change password used in switch case
 public void changePassword(){
	 String vPassword = "java@7799";
	 String uPassword = "Tech@143";
	 System.out.println("Change password.If you want to change Password.press 1.Go to Home page press 0.Logout this page press any key.");
	 int change = sc.nextInt();
	 if( change == 1 ){
		 while(true){
			System.out.println("enter the Old password");
			String password = sc.next();
			if( (uPassword.equals(password)) || (vPassword.equals(password)) ){
			  System.out.println("enter the new password");
			  String new_pwd1 = sc.next();
			  while(true){
				   System.out.println("Re-Enter the new password");
					String new_pwd2 = sc.next();
					if( new_pwd1.equals(new_pwd2)){
					System.out.println("your password changed successfully.");
					break;
					}else{
					System.out.println("your entered passwords are not matched.please check and Re-Enter:");
					}
				}
			    break;		 
		    }else{
			 System.out.println("your entered password is invalid.please check and Re-Enter:");
		 }
	    }
	 }else if( change == 0 ){
		 dashBoard();
	 }else{
		 System.exit(0);
	 }
}

//method for Eminities used in switch case
public void methodEminities(){
	System.out.println("1.Cheque Book Request	2.Apply ATM Card  \n3.SMS Request	4.ATM Card block \n5.Change ATM Pin	6.Close Account");
	System.out.println("Select which operation do you want to perform.enter key:");	
		int select = sc.nextInt();
		switch(select){
			case 1:System.out.println("you are selected Cheque Book request.apply for Cheque Book press 1.home page press 0.press any key exit.");
					System.out.println("enter key");
					int apply = sc.nextInt();
					if(apply == 1){
						System.out.println("Thanking you for apply Cheque Book.you are my valid customer.your Cheque Book will be deliver with in 7 working days to your address.");
						 methodExit();
					}else if(apply == 0){
						 dashBoard();
					}else{
						System.exit(0);
					}
					break;
					
			case 2:System.out.println("you are selected Apply ATM Card.press 1 Apply ATM Card.press 0 home page.press any key exit page.");
					System.out.println("enter key");
					int card = sc.nextInt();
					if(card == 1){
						System.out.println("Thanking you for Apply ATM Card.you are my valid customer.your ATM Card will be deliver with in 7 working days to your address.");
						 methodExit();
					}else if(card == 0){
						 dashBoard();
					}else{
						System.exit(0);
					}
					break;
			case 3:System.out.println("you are selected Apply SMS Request.press 1 SMS Request.press 0 home page.press any key exit page.");
					System.out.println("enter key");
					int sms = sc.nextInt();
					if(sms == 1){
						System.out.println("Thanking you for SMS Request.you are my valid customer.your request is in proccesing with in 1 hour you got the conformation message. ");
						 methodExit();
					}else if(sms == 0){
						 dashBoard();
					}else{
						System.exit(0);
					}
					break;
					
			case 4:System.out.println("you are selected ATM CARD BLOCKING.press 1 ATM CARD BLOCKING.press 0 home page.press any key exit page.");
					System.out.println("enter key");
					int block = sc.nextInt();
					if(block == 1){
						System.out.println("Thanking you for ATM CARD BLOCKING.you are my valid customer.");
						System.out.println("enter Atm card Number:");
						long atm = sc.nextLong();
						System.out.println("Successfully your Atm card is blocked.");
						 methodExit();
					}else if(block == 0){
						 dashBoard();
					}else{
						System.exit(0);
					}
					break;
					
			case 5:System.out.println("you are selected Change ATM PIN .press 1 Change ATM CARD .press 0 home page.press any key exit page.");
					System.out.println("enter key");
					int atm = sc.nextInt();
					if(atm == 1){
						System.out.println("Thanking you for selected Change ATM PIN.you are my valid customer.");
						System.out.println("enter Atm pin:");
						int pin1 = sc.nextInt();
						System.out.println("Re-enter Atm pin:");
						while(true){
							int pin2 = sc.nextInt();
							if(pin1 == pin2){						
						      System.out.println("Successfully your Atm card pin is changed.");
							  break;
							}else{
								System.out.println("your entered pin not matched.check and Re-enter:");
							}
						}methodExit();
					}else if(atm == 0){
						 dashBoard();
					}else{
						System.exit(0);
					}
					break;
					
			case 6:System.out.println("you are selected Close Account.press 1 Close Account.press 0 home page.press any key exit page.");
					System.out.println("enter key");
					int close = sc.nextInt();
					if(close == 1){
						System.out.println("Sorry for your inconvenient .you are my valid customer.your Account will be closed with in 24 hours.");
						 System.exit(0);
					}else if(close == 0){
						 dashBoard();
					}else{
						System.exit(0);
					}
					break;
					
			default :System.out.println("sorry you are entered wrong key");
		}
}

//method for exit or home page used in switch case
public void methodExit(){
	 System.out.println("if you want go home page press 1 and logout the page press 0");
	 int press = sc.nextInt();
	 if(press == 1){
		 dashBoard();
	 }else if(press == 0){
		 System.out.println("Thanking you for using my NetBanking services !");
	 }else{
			System.out.println("sorry you entered wrong key.");
			System.exit(0);
	 }
}

		 
}
	 

