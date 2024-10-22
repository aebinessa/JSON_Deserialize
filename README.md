## Welcome to this Repository on JSON deserialization via UiPath.


To demonstrate the usage of the Deserialize JSON activity for extracting data from a JSON file, let's look at an example that retrieves a person's age from a simple JSON file.

### Follow these steps with me to build the automation process:

 - Open Studio and create a new Process.
 - Create a sequence and the following variables:

 - JsonText of type	String	
 - JsonObj	of type JObject	
 - Age	of type GenericValue

### Next:
 - Add a "Read Text File" activity inside the sequence.
 In the Properties panel, set "JsonString.txt" as the value in the FileName field.
 Assign the JsonText variable to the Content field.
### After that:
 - Add a "Deserialize JSON" activity after the "Read Text File" activity.
 - Set JsonText in the JsonString field and JsonObj in the JsonObject field.
 - Select Newtonsoft.Json.Linq.JObject from the TypeArgument dropdown list.

### Finally:
Drag an "Assign" activity below the "Deserialize JSON" activity.

 - Set Age as the value in the To field and use the expression JsonObj.SelectToken("age").ToString in the Value field.
 - Finally, add a "Write Line" activity and input the Age variable into the Text field.

And now, When you run the process, the robot will extract the age value from the JSON file and display it in the Output panel.
