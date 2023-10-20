## Part 1
###Code:
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int index = 1;
    ArrayList<String> Strings = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("");
        } 
        else if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            String IntFormat = "";
            if (parameters[1].contains("+")){ 
                String SpaceStr = parameters[1].replaceAll("\\+", " ");
                IntFormat = IntFormat.format("%x", index);
                Strings.add(IntFormat);
                Strings.add(". ");
                Strings.add(SpaceStr);
                Strings.add("\n");
                index++;
                return String.format(String.join("", Strings));
            }
            IntFormat = IntFormat.format("%x", index);
            Strings.add(IntFormat);
            Strings.add(". ");
            Strings.add(parameters[1]);
            Strings.add("\n");
            index++;
            return String.format(String.join("", Strings));
        }
        return "Error";
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}


Screenshots:
---
![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/691c3ff7-95d3-4d2b-88e3-e7b119a391e9)
My handleRequest method was called. The relevant arguments in the method within this screenshot is in lines 15-18, 31-37. 
The values in those fields are index = 1, IntFormat = "1", String = ["add-messages?s", "hello"], Strings = []. The values that are changed
in this field are Strings and index since index is postincremented before the method is done via index++, Strings gets strings added to its array as the
add method is used in lines 29-32.

![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/7fbc38f3-4b6b-44bb-8143-77ab7853202c)
My handleRequest method was called. The relevant arguments in the method within the screenshot is in lines 15-26. 
The values in those fields are index = 2, IntFormat = "2", String = ["add-messages?s", "how are you?"], Strings = [].
The values that are changed in this field are Strings and index since index is postincremented before the method is returned via index++,
Strings gets strings added to its array from lines 21-24. 





##Part 2:
![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/231e065b-da9c-4482-ad6e-d511eb43240e)

![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/7e193a5c-caea-497e-84dd-286cde97ff02)

![image](https://github.com/Konica-l/cse15l-lab-reports/assets/144089855/9d622ea9-9742-49b1-9f03-eb2b37b4bdb0)

##Part 3:

Something new I learned from lab 2 and 3 are how servers are created and websites. I understand why there exists server rooms now considering
that in order for a website to function, we need a client to run it.
