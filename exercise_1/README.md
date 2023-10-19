# Exercise 1

## First steps programming with Bing Chat

### Rövarspråket encoder

Create a program that converts a sentence into rövarspråket. 
Rövarspråket is a Swedish language game. Each consonant is doubled with an "o" in between. For example, the sentence "Hej jag heter Kalle" is translated into "Hohejoj jojagog hohetoteror Kokalollole".

We will use Bing Chat for this problem. It uses GPT-4 from OpenAI under the hood.

1. Go to https://bing.com/chat
2. Prompt bing chat to solve your problem, for example:

    Let's use a simple prompt to warm up:

    ```
    write a program in [your-favorite-language] that converts any sentence to rövarspråket
    ```

3. Verify that the program works by running it locally on your computer, or use an online playground for your language of choice.

### Debugging the rövarspråket decoder

1. Use bing chat to debug code. 
2. The following code is supposed to decode a rövarspråket sentence, but it has a bug. 

    ```javascript
    function fromRovarspraket(rovarspraket) {
        var sentence = "";
        for (var i = 0; i < rovarspraket.length; i++) {
            var char = rovarspraket.charAt(i);
            if (char.match(/[bcdfghjklmnpqrstvwxyzBCDFGHJKLMNPQRSTVWXYZ]/)) {
                sentence += char.charAt(0);
                i += 1;
            } else {
                sentence += char;
            }
        }
        return sentence;
    }
    ```
      
3. Prompt bing chat

    Let's use a prompt like this (you can use shift-enter to add a new line in the chat)

    ```
    Find the bugs in the following code. The code should decode a rövarspråket sentence to normal language. [insert code here]
    ```

4. Refine your prompt by giving example output

    If you are not getting the expected response, try to refine your prompt by giving example output. For example:
    
    ```
    There is another bug. The code above should decode

    Hohejoj jojagog hohetoteror Kokalollole
    
    into
    
    Hej jag heter Kalle
    
    but it decodes it into
    
    HhjjjjgghhttrrKkllol
    ```

### Explaining code

1. Here is some code. What does it do?



1. Here is some code

    ```
    def foo(x):
    z = 1.0
    
        while True:
            temp = z
            z = z - (z * z - x) / (2 * z)
            
            if abs(z - temp) < 1e-6: 
                break
        
        return z
   ```
   
2. Prompt bing chat to explain the code

    ```
    Explain the following code [insert code here]
    ```
   

### Bonus exercises if you're done early

#### Improving code

Ask bing chat how to improve the following code:

   ```java
   public class JDBCExample {
       public static void main(String[] args) {
           Connection conn = null;
           Statement stmt = null;
           ResultSet rs = null;
           try {
               Class.forName("com.mysql.jdbc.Driver");
               conn = DriverManager.getConnection("jdbc:mysql://localhost/myDatabase", "root", "password");
               stmt = conn.createStatement();
               rs = stmt.executeQuery("SELECT * FROM employees");
               while (rs.next()) {
                   String fullName = rs.getString("firstName") + " " + rs.getString("lastName");
                   System.out.println(fullName);
               }
           } catch (Exception e) {
               e.printStackTrace();
           }
       }
   }
   ```

#### Refactoring code

Ask bing chat to refactor the following code

   ```kotlin
   fun printOwing() {
      var outstanding: Double = 0.0
      //  print banner
      println("********************************")
      println("******** Customer Owes *********")
      println("********************************")
   
      //  calculate outstanding
      for (orderLine in orderLines) {
         outstanding += orderLine.amount
      }
      //  print details
      println("Name: $name")
      println("Amount: $outstanding")
   }
   ```