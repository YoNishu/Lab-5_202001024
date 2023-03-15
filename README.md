# Lab-5_202001024
	LAB-5

Name: Nishith Gangajaliya
SID: 202001024

Erroneous code (Source: Bing chat)

![image](https://user-images.githubusercontent.com/84803886/225277627-f6d280ff-1fa8-41b8-89ef-820b485644f0.png)


![image](https://user-images.githubusercontent.com/84803886/225277944-f189cf9e-8bba-45a8-966f-c2c08c2b9b8f.png)


import vscode # Import vscode module
import pylance # Import pylance module


# Define an activate function for the extension
def activate(context):
  # Define a command for running Pylance on an open document
  def run_pylance():
    # Get the active text editor
    editor = vscode.window.active_text_editor
    if not editor:
      return # No open text document
   
    # Get the document text
    document = editor.document
    text = document.text


    # Run Pylance on the text
    try:
      results = pylance.lint_text(text)
      # Show the first result in an information message
      vscode.window.show_information_message(str(results[0]))
    except Exception as error:
      # Show an error message if something went wrong
      vscode.window.show_error_message(str(error))
 
  # Register a command for running Pylance with a name and a function
  run_command = vscode.commands.register_command('extension.runPylance', run_pylance)


  # Add the command to the context subscriptions
  context.subscriptions.append(run_command)


# Export activate function
vscode.exports.activate = activate

I have done static analysis for the above given python code and I have chosen Pylint as a static analysis tool.

Pylint installation:

![image](https://user-images.githubusercontent.com/84803886/225278110-2aa0a6fb-5066-4f84-803f-0a500822999e.png)

We can install Pylint by going into extension section in Visual Studio Code and searching for ‘Pylint’.

Output:

Pylint was showing the following errors:

1. ![image](https://user-images.githubusercontent.com/84803886/225278252-a1fb350e-bef7-40e3-bced-003bf2ff68dc.png)

After running the code we get:

![image](https://user-images.githubusercontent.com/84803886/225278564-c5aefaee-0707-4168-b737-248290f2cf67.png)  

As we can see above that the same error Pylint was showing is shown in the terminal by the compiler hence, it's showing correct errors and it is useful.

2. ![image](https://user-images.githubusercontent.com/84803886/225278281-82c904aa-8b59-4cd2-8750-89aa01a9ea06.png)

After running the code we get:

![image](https://user-images.githubusercontent.com/84803886/225279309-a9d21c32-a638-4fcc-82d8-1c7b7c157d9a.png)  

As we can see above that the same error Pylint was showing is shown in the terminal by the compiler hence, it's showing correct errors and it is useful.

3. ![image](https://user-images.githubusercontent.com/84803886/225279466-4b3285e2-a708-4529-ba08-a179f7d13772.png) 
4. ![image](https://user-images.githubusercontent.com/84803886/225280455-af791b9d-ff87-4a5b-9589-e3257f59d3da.png)  

Above errors are also a correct and will be gone after we use format documenting as follows:  
![image](https://user-images.githubusercontent.com/84803886/225280657-e7984ed1-b543-47ee-af4c-d7cedd741cfd.png)  

After formatting document we can see below that all errors are gone:  
![image](https://user-images.githubusercontent.com/84803886/225281056-a80a5ea6-f8a5-4ed2-a203-faa2708c69ca.png)  

5. ![image](https://user-images.githubusercontent.com/84803886/225281129-9e26915c-4e9c-4530-a4d0-919cbe606e5a.png)  

Above shown are some errors displayed by the Pylint extension. All the shown errors are accurate and we get same errors on running the program. Hence this Static Ananlysis Tool is extremely for Static Analysis in Python.



