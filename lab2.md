# Lab Report 1
---
## Part 1: 
String Server Code:
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String string = "";
    int index = 0;
    
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return "Hello! Add a String!";
        } else {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    String s = parameters[1];
                    index++;
                    string += String.format("%d. %s \n", index, s);
                    return string;
                    }
            }
        }
        return "404 Not Found!";
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
```
![Image](cse_15l_lab_images/LabReport2Img1.png)

![Image](cse_15l_lab_images/LabReport2Img2.png)
