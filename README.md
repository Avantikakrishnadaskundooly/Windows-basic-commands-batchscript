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

## COMMAND AND OUTPUT
```
mkdir my-folder
```

<img width="575" height="239" alt="image" src="https://github.com/user-attachments/assets/ef42d0a5-1262-4419-852e-d866d9256cc5" />


Remove the directory "my-folder"

## COMMAND AND OUTPUT
```
rmdir my-folder
```

<img width="472" height="48" alt="image" src="https://github.com/user-attachments/assets/a7daa106-7b33-42b6-acc8-cbb36ca82b78" />


Create the file Rose.txt

## COMMAND AND OUTPUT
```
COPY CON Rose.txt
dir Rose.txt
```
<img width="648" height="327" alt="image" src="https://github.com/user-attachments/assets/c683a348-18b4-42b8-8f31-cd75a4725289" />


Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
```
echo “hello world” > hello.txt
type hello.txt
```
<img width="655" height="116" alt="image" src="https://github.com/user-attachments/assets/79f90e74-9552-4a8b-9e35-7e76fe0ae27d" />


Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
```
copy hello.txt hello1.txt
```
<img width="607" height="143" alt="image" src="https://github.com/user-attachments/assets/945d01fd-1320-4683-8ffd-ee245bbc1caf" />


Remove the file hello1.txt

## COMMAND AND OUTPUT
```
del hello1.txt
```
<img width="464" height="50" alt="image" src="https://github.com/user-attachments/assets/5493eec7-dcf7-465c-9c47-d451d4df2118" />


List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
```
dir hello1.txt
```
<img width="491" height="180" alt="image" src="https://github.com/user-attachments/assets/03674d01-aa35-47c8-b594-4caab5aa24d2" />


List out all the associated file extensions 

## COMMAND AND OUTPUT
```
assoc | more
```
<img width="542" height="469" alt="image" src="https://github.com/user-attachments/assets/43294b12-a536-49e4-9c16-65f22cf5b47d" />


Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
```
fc hello.txt Rose.txt
```
<img width="554" height="154" alt="image" src="https://github.com/user-attachments/assets/9ae73315-1af8-4431-a32c-4075cf47793d" />



## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
```
@echo off
set name=Avanti
echo Hello, %name%!
pause
```


## OUTPUT
<img width="425" height="85" alt="image" src="https://github.com/user-attachments/assets/635de4fa-02ec-4b41-a800-95aa4111ed22" />



Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
```
@echo off
:main
set /p number=Enter a number: 
rem Calculate remainder when divided by 2
set /a remainder=%number% %% 2
if %remainder%==1 (
    echo %number% is an odd number.
) else (
    echo %number% is not an odd number.
)
:choice
set /p continue=Do you want to check another number? (Y/N): 
if /i "%continue%"=="Y" goto main
if /i "%continue%"=="N" goto end
echo Invalid choice, please enter Y or N.
goto choice
:end
echo Thank you for using the odd number checker!
pause
```


## OUTPUT
<img width="590" height="234" alt="image" src="https://github.com/user-attachments/assets/b36cbc84-3e22-4363-a090-e3e9ed46bf20" />




Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.
```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```



## OUTPUT
<img width="442" height="184" alt="image" src="https://github.com/user-attachments/assets/555fff34-e2eb-456d-b811-8202e9f47073" />




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
```
@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause
```


## OUTPUT
<img width="416" height="92" alt="image" src="https://github.com/user-attachments/assets/a2c4c98b-1823-4a26-baf3-bf7fd9b9fad1" />



Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
```
@echo off
:menu
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option: 
if "%choice%"=="1" goto hello
if "%choice%"=="2" goto createfile
if "%choice%"=="3" goto end

:hello
echo Hello, World!
goto menu

:createfile
echo Creating a file...
echo This is a new file > newfile.txt
goto menu
:end
echo Goodbye!
pause
```


## OUTPUT
<img width="476" height="410" alt="image" src="https://github.com/user-attachments/assets/3c4a0406-9688-43ed-b323-00170bf908f7" />



# RESULT:
The commands/batch files are executed successfully.

