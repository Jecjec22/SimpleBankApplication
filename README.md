import java.util.Scanner;
public class BankingApplication_Simple {

    
    public static void main(String[] args) {
        
         Scanner sc= new Scanner(System.in);
         System.out.println("Enter your name:");
         String name = sc.nextLine();
         Scanner cd = new Scanner(System.in);
         System.out.println("Enter your id: ");
         String id = cd.nextLine();
         System.out.println("\n");
         System.out.println("\n");
         
         
         
         
         

       BankAccount obj = new BankAccount(""+name, ""+id);
       obj.showMenu();
    }
    
}

class BankAccount
{
    int balance;
    int previousTransaction;
    String customerName;
    String customerId;
    
    BankAccount(String cname,String cid)
    {
        customerName = cname;
        customerId = cid;
    }
    
    void deposit(int amount)
    {
        if (amount !=0)
        {
            balance = balance + amount;
            previousTransaction = amount;
            
            
        }
    }
    void withdraw (int amount)
    {
        if (amount !=0)
        {
            balance = balance - amount;
            previousTransaction = -amount;
            
            
        }
    }
    void getPreviousTransaction()
    {
        if(previousTransaction>0)
        {
            System.out.println(" You Deposited:" + previousTransaction);
        }
        else if (previousTransaction<0)
        {
            System.out.println("You have withdrawn: "+Math.abs(previousTransaction));
        }
        else
        {
            System.out.println("No transaction Happened");
        }
    }
    void showMenu()
    {
        char option= '\0';
        Scanner scanner = new Scanner(System.in);
        
        try {
			Thread.sleep(3000);
		}
		catch (InterruptedException ex) 
		{ 
			
		}

		
       
        System.out.println("Welcome "+customerName);
        System.out.println("Your ID is "+customerId);
        System.out.println("\n");
        System.out.println("\n");
        try {
			Thread.sleep(2000);
		}
		catch (InterruptedException ex) 
		{ 
			
		}
        System.out.println("A. Check Balance");
        System.out.println("B. Deposit");
        System.out.println("C. Withdraw");
        System.out.println("D. Previous Transaction");
        System.out.println("E. Exit");
        
        do
        {
            System.out.println("===============================================");
            System.out.println("Enter an option");
            System.out.println("===============================================");
            option = scanner.next().charAt(0);
            System.out.println("\n");
            
            switch(option)
            {
                case 'A'|'a':
                    System.out.println("=======================================");
                    System.out.println(" Your Balance is = "+balance);
                    System.out.println("=======================================");
                    System.out.println("\n");
                    break;
                    
                case 'B'|'b':
                    System.out.println("=======================================");
                    System.out.println("Enter an amount to Deposit");
                    System.out.println("=======================================");
                    int amount = scanner.nextInt();
                    deposit(amount);
                    System.out.println("\n");
                    break;
                    
                case 'C'|'c':
                    System.out.println("=======================================");
                    System.out.println("Enter an amount to Withdraw");
                    System.out.println("=======================================");
                    int amount2 = scanner.nextInt();
                    withdraw(amount2);
                    System.out.println("\n");
                    break;
                    
                case 'D'|'d':
                    System.out.println("=======================================");
                    getPreviousTransaction();
                    System.out.println("=======================================");
                    System.out.println("\n");
                    break;
                    
                case 'E'|'e':
                    System.out.println("=======================================");
                    break;
                    
                default:
                    System.out.println("Invalid Option! Please Try Again");
                    break;
                    
                    
            }
        } while(option !='E');
        System.out.println("Thank You for using our services");
    }       
}

    
    
    
