# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations

Create a directory named "my-folder"
mkdir my-folder
<img width="387" height="53" alt="image" src="https://github.com/user-attachments/assets/3f363a5a-6c45-48e6-af95-a1e961065744" />


## COMMAND AND OUTPUT

Remove the directory "my-folder"
rmdir my-folder
<img width="408" height="50" alt="image" src="https://github.com/user-attachments/assets/7e2b4e27-cb9c-41ad-be39-a93b5828d68c" />

## COMMAND AND OUTPUT


Create the file Rose.txt
type nul > Rose.txt
<img width="439" height="55" alt="image" src="https://github.com/user-attachments/assets/4f73222a-9ee6-4d8f-8ce3-f7ccb0ba3993" />

## COMMAND AND OUTPUT


Create the file hello.txt using echo and redirection
echo Hello World > hello.txt
<img width="558" height="52" alt="image" src="https://github.com/user-attachments/assets/7457303f-48e4-41a6-b689-8f1f5fe61431" />

## COMMAND AND OUTPUT

Copy the file hello.txt into the file hello1.txt
copy hello.txt hello1.txt
<img width="497" height="69" alt="image" src="https://github.com/user-attachments/assets/8e6908a8-a19a-41e0-b1df-7ff7ce630cbd" />

## COMMAND AND OUTPUT

Remove the file hello1.txt
del hello1.txt
<img width="390" height="49" alt="image" src="https://github.com/user-attachments/assets/e099858f-d529-4ea1-85f5-37dae5cd47ea" />

## COMMAND AND OUTPUT

List out the file hello1.txt in the current directory
dir hello1.txt
<img width="438" height="182" alt="image" src="https://github.com/user-attachments/assets/65f3898b-c37d-4524-a7f0-4f080d80aab5" />

## COMMAND AND OUTPUT

List out all the associated file extensions 
assoc
<img width="625" height="880" alt="image" src="https://github.com/user-attachments/assets/e8144048-dcbe-4351-93d2-70164b886d01" />

## COMMAND AND OUTPUT


Compare the file hello.txt and rose.txt
fc hello.txt Rose.txt
<img width="536" height="159" alt="image" src="https://github.com/user-attachments/assets/a0372694-ef72-4f65-95d2-8abaecbf6ed8" />

## COMMAND AND OUTPUT

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

## CODE:
@echo off
set name=John
echo Hello, %name%
pause



## OUTPUT
<img width="494" height="77" alt="image" src="https://github.com/user-attachments/assets/55560bc0-7512-4478-b2e4-a4fa798b00ef" />



Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

## CODE:
@echo off
:START
set /p num=Enter a number: 

set /a rem=%num% %% 2

if %rem%==1 (
    echo The number %num% is ODD
) else (
    echo The number %num% is NOT ODD
)

:CHOICE
set /p choice=Do you want to check another number? (Y/N): 

if /I "%choice%"=="Y" goto START
if /I "%choice%"=="N" goto END

echo Invalid choice. Please enter Y or N.
goto CHOICE

:END
echo Thank you!
pause

## OUTPUT
<img width="656" height="202" alt="image" src="https://github.com/user-attachments/assets/5b841d13-69d1-48f1-b74b-95f69c82b984" />




Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

## CODE:
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause

## OUTPUT
<img width="457" height="165" alt="image" src="https://github.com/user-attachments/assets/0cf21a6e-511d-4166-97df-fc93e75695ba" />




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

## CODE:
@echo off
if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)
pause

## OUTPUT
<img width="422" height="52" alt="image" src="https://github.com/user-attachments/assets/028cbdfd-cfbb-4836-96b7-f3c6bf398211" />


Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

 ## CODE:
@echo off
:MENU
cls
echo ===== MENU =====
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
echo =================
set /p choice=Enter your choice: 

if "%choice%"=="1" goto HELLO
if "%choice%"=="2" goto CREATE
if "%choice%"=="3" goto EXIT

echo Invalid choice!
pause
goto MENU

:HELLO
echo Hello, World!
pause
goto MENU

:CREATE
echo This is a new file > newfile.txt
echo File created successfully!
pause
goto MENU

:EXIT
echo Goodbye!
pause
exit
## OUTPUT1
<img width="410" height="192" alt="image" src="https://github.com/user-attachments/assets/3fe772af-94ae-426c-ae6f-bdbc34a50889" />


## OUTPUT2
<img width="441" height="203" alt="image" src="https://github.com/user-attachments/assets/31b20d7a-3fc1-4d6a-b8f2-4d0c7c70537d" />


## OUTPUT3
<img width="431" height="197" alt="image" src="https://github.com/user-attachments/assets/5f6b0ad6-e521-4b06-b13f-2dd1385609a0" />


# RESULT:
The commands/batch files are executed successfully.

