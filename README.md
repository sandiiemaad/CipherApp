# JavaAssignment
package com.mycompany.assignment1cipher;

import java.util.Scanner;

//class for making encryption by using Atbash method
class AtbashEncryption {
    private String msg;
    
    //To store the encrypted msg
    private String encryptedMsg = "";                  

    // Constructor to initialize the message and encrypt it
    public AtbashEncryption(String msg) {
        this.msg = msg;
        encryptMessage();
    }

    private void encryptMessage() {
        
        // converting string to character by using toCharArray
        for (char character : msg.toCharArray()) {
            
            //check if character is letter or not
            if (Character.isLetter(character)) {
                
                // make sure all letter is capital
                character = Character.toUpperCase(character);
                int newCharacter = ('A' - character + 25);
                character = (char) ('A' + newCharacter);
                
                //Store the encrypted letters in empty string
                encryptedMsg += character;  
                
            // check if there is space add it to encrypted msg
            } else if (Character.isWhitespace(character)) {
                encryptedMsg += character;
            }
        }
    }

    // Getter method to return the encrypted message
    public String getEncryptedMsg() {
        return encryptedMsg;
    }
}



//class for making decryption by using Atbash method
class DecryptionAtbash {

    private String msg;
    
    //To store the encrypted msg
    private String decryptedMsg = "";                  

    // Constructor to initialize the message and encrypt it
    public DecryptionAtbash(String msg) {
        this.msg = msg;
        decryptmsg();
    }

    private void decryptmsg() {
        
        // converting string to character by using toCharArray
        for (char character : msg.toCharArray()) {
            
            //check if character is letter or not
            if (Character.isLetter(character)) {
                
                // make sure all letter is capital
                character = Character.toUpperCase(character);
                int newCharacter = ('Z' - character - 25);
                character = (char) ('Z' + newCharacter);
                
                //Store the encrypted letters in empty string
                decryptedMsg += character;  
                
            // check if there is space add it to decrypted msg
            } else if (Character.isWhitespace(character)) {
                decryptedMsg += character;
            }
        }
    }

    // Getter method to return the decrypted message
    public String decryptedmsg() {
        return decryptedMsg;
    }
  
}

public class Assignment1Cipher {
    public static void main(String[] args) {
        
        Scanner input = new Scanner(System.in);
        int Choice1 = 0 ;
        int Choice2 ;
        
        do{
           
        //Display The Menu    
        System.out.println("Welcome To The Program !\n Please Choose One Option From The Following");
        System.out.println("-------------------------------------------------------------------------");
        System.out.println("MENU");
        System.out.println("[1] Encryption");
        System.out.println("[2] Decryption");
        System.out.println("[3] Exit");

        // check if the input is integer or not
        if (input.hasNextInt())                     
        {
                Choice1 = input.nextInt();
                //To clear the buffer 
                input.nextLine();
                
        } else {
                System.out.println("Invalid input....Please Enter A Valid Integer Input");
                input.nextLine(); 
                // Restart the loop
                continue; 
        }

        switch(Choice1){
            case 1 :
                
                //Applying all options od encryption
                System.out.println("--------------------------------------------------------------------------");
                System.out.println("Please Choose Which Type of Cipher you want for Encryption");
                System.out.println("[1] Atbash Cipher");
                System.out.println("[2] Affine Cipher");
                // check if the input is integer or not
                if (input.hasNextInt())                     
                 {
                   Choice2 = input.nextInt();
                   //To clear the buffer 
                  input.nextLine();
                
                } else {
                     System.out.println("Invalid input....Please Enter A Valid Integer Input");
                     input.nextLine(); 
                      // Restart the loop
                       continue; 
                }
                System.out.println("--------------------------------------------------------------------------");

                switch (Choice2){
                    case 1 :
                      
                        // Applying Atbash Cipher Encryption
                        System.out.println("Please Enter your Message to encrypt it:");
                        String message = input.nextLine();
                        //Creat Object From AtbashEncryotion Class
                        AtbashEncryption encryptedMessage = new AtbashEncryption(message);
                        //use getter method to return the encrypted msg
                        System.out.println("The Encrypted Message is: " + encryptedMessage.getEncryptedMsg());
                        System.out.println("--------------------------------------------------------------------------");
                        break;
                   
                    case 2 :    
                        
                        // Applying Affine Cihpher 
                        System.out.println("Please Enter your Message to encrypt it:");
                         message = input.nextLine();
                        System.out.println("Important Note : The Equation of Encryption is [(key1 * x) + key2] % 26");
                        while(true){
                        System.out.print("Please Enter Value Of Key1 : ");
                        // check if the key2 is integer or not
                        if (input.hasNextInt())                     
                        {
                          int key1 = input.nextInt();
                          //To clear the buffer 
                          input.nextLine();
                          break;
                
                        } else {
                            System.out.println("Invalid input....Please Enter A Valid Integer Input");
                            input.nextLine();
                        }
                    }
                        
                        while(true){
                        System.out.print("Please Enter Value Of Key2 : ");
                        // check if the key2 is integer or not
                        if (input.hasNextInt())                     
                        {
                          int key2 = input.nextInt();
                          //To clear the buffer 
                          input.nextLine();
                          break;
                
                        } else {
                            System.out.println("Invalid input....Please Enter A Valid Integer Input");
                            input.nextLine();
                        }
                    }
                        
                        //Creat Object From AtbashEncryotion Class
                        //AtbashEncryption encryptedMessage = new AtbashEncryption(message);
                        //use getter method to return the encrypted msg
                        //System.out.println("The Encrypted Message is: " + encryptedMessage.getEncryptedMsg());
                        System.out.println("--------------------------------------------------------------------------");
                        break;
                        
                    default : 
                        // For inputs which is not in choices
                        System.out.println("Invalid Input...Please Try Again");
                }
                break;
                
            case 2 :
                //Applying all options of decryption
                System.out.println("--------------------------------------------------------------------------");
                System.out.println("Please Choose Which Type of Cipher you want for Decryption");
                System.out.println("[1] Atbash Cipher");
                System.out.println("[2] Affine Cipher");
                Choice2 = input.nextInt();
                //To Clear The Newline Character
                input.nextLine();   
                System.out.println("--------------------------------------------------------------------------");

                switch (Choice2){
                    case 1 :
                       
                        // Applying Atbash Cipher decryption
                        System.out.println("Please Enter your Message to decrypt it:");
                        String message = input.nextLine();
                        DecryptionAtbash decryptedmsg = new DecryptionAtbash(message);
                        System.out.println("The decrypted message is: " + decryptedmsg.decryptedmsg());
                        System.out.println("--------------------------------------------------------------------------");
                        break;
                   
                    case 2 :    
                        // Applying Affine Cihpher decryption
                        
                        break;
                        
                    default : 
                        // For inputs which is not in choices
                        System.out.println("Invalid Input...Please Try Again");
                }
                
                break;
                
            case 3 :
                
                //For Exiting from the program
                System.out.println("Ending The Program...");
                break;
                
            default :
                // For inputs which is not in choices
                System.out.println("Invalid Input....Please Enter Valid Input");
                
        }
        }//For making the menu always display until choose exit
        while (Choice1 != 3);
    }
}
        
        
