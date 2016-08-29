# Hashmap
package hashmap;

import java.util.*;
import javax.swing.*;
class Details
{
	String name;
	String Address;
	String phone;	
}


public class hashmap {

	public static Details currentRecord = null;
	static HashMap<String, Details> contacts;
	
	public static void main(String[] args) {
		String input;
    	contacts  = new HashMap<String, Details>();
	    Details temp = new Details();

		do {
		System.out.println("Press 1 to Add");
		System.out.println("Press 2 to Remove");
		System.out.println("Press 3 to Search");
		
		
		Scanner sc = new Scanner(System.in);
	    input = sc.nextLine();
	    	    
	    if(input.equals("1"))
	    {	    	
	    	System.out.println("Please Enter Name");
		    input = sc.nextLine();
		    temp.name = input;
		    
		    System.out.println("Please Enter Address");
		    input = sc.nextLine();
		    temp.Address = input;
		    
		    
		    System.out.println("Please Enter Phone Number");
		    input = sc.nextLine();
		    temp.phone = input;
		    
		    currentRecord = temp;
		    
		    contacts.put(temp.name, temp);
		    System.out.println("Contact Succesfully Inserted");
	    }else if(input.equals("2"))
	    {
	    	if(!contacts.isEmpty())
	    	{
	    		String key = currentRecord.name;
	    		contacts.remove(key);
	    		System.out.println("Contact Succesfully Removed");
	    	}else
	    	{
	    		System.out.println(" List is empty");
	    	}
	    	
	    }else if(input.equals("3")){
	    	System.out.println("Please Enter Name:");
	    	String name = sc.nextLine();
	    	
	    	Details temp1 = contacts.get(name);
	    	
	    	if(temp1.equals(null)){
	    		System.out.println("No such name exist in the records");
	    	}
	    	else
	    	{
	    		System.out.println("Name: "+temp.name);
	    		System.out.println("Address: "+temp.Address);
	    		System.out.println("Phone Number: "+temp.phone);
	    	}
	    } else if(input.equals("5")) {
		    sc.close();
	    	break;
	    }
	    else
	    {
	    	System.out.println("Please Enter Proper Input");
	    }
		} while (true);
	}
}


