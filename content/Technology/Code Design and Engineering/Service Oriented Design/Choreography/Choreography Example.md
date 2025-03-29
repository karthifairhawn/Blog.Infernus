******************************************************************************

```java
Welcome to GDB Online.
GDB online is an online compiler and debugger tool for C, C++, Python, Java, PHP, Ruby, Perl,
C#, OCaml, VB, Swift, Pascal, Fortran, Haskell, Objective-C, Assembly, HTML, CSS, JS, SQLite, Prolog.
Code, Compile, Run and Debug online from anywhere in world.

*******************************************************************************/
public class Main
{
	public static void main(String[] args) {
		BundleChore.event_subscriber_list.add("addUser", [MailService, AuditLog, DelayDowngrade, LicenseCount]);
		BundleChore.event_subscriber_list.add("addUserFromIam", [MailService, DelayDowngrade, LicenseCount]);

		
		UserService.addUser();
	}
}

// Choreography Model
class UserService{
    public static void addUser(){
        // Add to Db
        // Add to IAM,...
        BundleChore.handleEvent("addUser")
    }
}

class UserService{
    public static void addUser(){
        // Add to Db
        // Add to IAM,...
        sendMail();
        ..
        ..
    }
}


public BundleChore{
    
    public static Map<String, List<Subscriber>> event_subscriber_list = new HashMap<String, Subscriber>();
    
    public void handleEvent(String eventName){
        List<Subscriber> allEventSubs = event_subscriber_list.get(eventName);
        for(Subscriber s:allEventSubs){
            s.subscribeEvent(eventName);
        }
        
    }
}

interface Subscriber{
    public void subscribeEvent(String eventName);
}

class MailService implements Subscriber{
    
    @Override
    public static void subscribeEvent(String eventName){
        if(eventName=="addUser"){  sendUserAddedMail(); };
    }
    
    private static sendUserAddedMail(){ ... }
}
```