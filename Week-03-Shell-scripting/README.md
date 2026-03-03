# ⭐Week 3 Challenge 1: User Account Management <br>

## Tasks <br>

### Part 1: Account Creation

1.Implement an option -c or --create that allows the script to create a new user account. The script should prompt the user to enter the new username and password.

2.Ensure that the script checks whether the username is available before creating the account. If the username already exists, display an appropriate message and exit gracefully.

3.After creating the account, display a success message with the newly created username.

#### Shell-script

<img width="744" height="687" alt="image" src="https://github.com/user-attachments/assets/1ad21fc1-043b-47c5-ad2d-2d014d8beaae" />


#### Output

<img width="893" height="208" alt="image" src="https://github.com/user-attachments/assets/b6ab0672-82a1-44db-bf0c-a4ab388bdd69" />

<img width="913" height="154" alt="image" src="https://github.com/user-attachments/assets/1043e421-9e73-488b-b229-3c637347ed79" />


### Part 2: Account Deletion

1.Implement an option -d or --delete that allows the script to delete an existing user account. The script should prompt the user to enter the username of the account to be deleted.

2.Ensure that the script checks whether the username exists before attempting to delete the account. If the username does not exist, display an appropriate message and exit gracefully.

3.After successfully deleting the account, display a confirmation message with the deleted username.

#### Shell-script

<img width="910" height="702" alt="image" src="https://github.com/user-attachments/assets/39b0e6bb-ec4d-4f6b-9c86-468306c9d458" />

#### Output

<img width="742" height="224" alt="image" src="https://github.com/user-attachments/assets/a940cb77-2f86-4c6f-94b7-53634446bbe7" />


### Part 3: Password Reset

1.Implement an option -r or --reset that allows the script to reset the password of an existing user account. The script should prompt the user to enter the username and the new password.

2.Ensure that the script checks whether the username exists before attempting to reset the password. If the username does not exist, display an appropriate message and exit gracefully.

3.After resetting the password, display a success message with the username and the updated password.

#### Shell-script

<img width="817" height="711" alt="image" src="https://github.com/user-attachments/assets/bb211349-2b91-4504-ad36-cd36536ad3fc" />


#### Output

<img width="683" height="143" alt="image" src="https://github.com/user-attachments/assets/35477876-eb25-41be-a090-ba2a772c8147" />

<img width="672" height="122" alt="image" src="https://github.com/user-attachments/assets/77d1379b-a340-4b0e-b869-3c91f1c92daf" />



### Part 4: List User Accounts

1.Implement an option -l or --list that allows the script to list all user accounts on the system. The script should display the usernames and their corresponding user IDs (UID).

#### Shell-script

<img width="512" height="229" alt="Screenshot (561)" src="https://github.com/user-attachments/assets/e3d7e27b-3ed8-4086-b9c8-aa44faf8e327" />

#### Output

<img width="687" height="320" alt="image" src="https://github.com/user-attachments/assets/4ec1e789-4f90-4212-92ea-748dd9d8ba87" />


### Part 5: Help and Usage Information

1. Implement an option -h or --help that displays usage information and the available command-line options for the script.

#### Shell-script

<img width="706" height="347" alt="image" src="https://github.com/user-attachments/assets/36bab06b-06e5-4d74-bdd6-c4fa29e07be3" />


#### Output

<img width="646" height="201" alt="image" src="https://github.com/user-attachments/assets/b86e9cec-3a8d-46c5-934c-e2c8b295002a" />

# ⭐ Week 3 Challenge 2: Automated Backup & Recovery using Cron <br>

## Tasks <br>

Your task is to create a bash script that takes a directory path as a command-line argument and performs a backup of the directory. The script should create timestamped backup folders and copy all the files from the specified directory into the backup folder.

Additionally, the script should implement a rotation mechanism to keep only the last 3 backups. This means that if there are more than 3 backup folders, the oldest backup folders should be removed to ensure only the most recent backups are retained.

Script

<img width="624" height="575" alt="image" src="https://github.com/user-attachments/assets/ea537b02-170b-4ef0-89f9-1a448ff48167" />

<img width="750" height="307" alt="image" src="https://github.com/user-attachments/assets/6a846094-44cf-4d14-bc37-131f9f91a094" />

Output

<<img width="920" height="107" alt="image" src="https://github.com/user-attachments/assets/7675398c-bc24-41a5-820d-fc493e4a7dc4" />

<img width="585" height="102" alt="image" src="https://github.com/user-attachments/assets/0b4a329a-d7d3-4edb-bd36-ff7df889c632" />










