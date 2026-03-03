# ⭐Week 2: Linux System Administration & Automation <br>

## Tasks

### A. **User & Group Management**

Create a user devops_user and add them to a group devops_team.

#### 1️⃣ Create group devops_team

<img width="574" height="97" alt="image" src="https://github.com/user-attachments/assets/396691bf-cd72-4b3d-b87f-2705669c510f" />
<br>

<img width="429" height="100" alt="image" src="https://github.com/user-attachments/assets/e87b375b-1cfa-405a-9602-3690c1113e69" />


#### 2️⃣ Create user devops_user and add to group

<img width="762" height="112" alt="image" src="https://github.com/user-attachments/assets/839a5989-7358-4ba8-831d-573d0f7133c6" />

#### 3️⃣ Set password for devops_user

<img width="528" height="102" alt="image" src="https://github.com/user-attachments/assets/273fc95a-977e-4290-a581-4931d6e8d6ef" />

#### 4️⃣ Grant sudo access
-commands
$sudo usermod -aG sudo devops_user

$su - devops_user
sudo whoami

#### 5️⃣ Restrict SSH login for certain users

Edit SSH config:

$sudo nano /etc/ssh/sshd_config

Allow only a group 

$AllowGroups devops_team

### B. **File & Directory Permissions**


#### 1️⃣.Create /devops_workspace

  command-> mkdir devops_workspace
  
<img width="649" height="83" alt="image" src="https://github.com/user-attachments/assets/db38448e-39c1-463d-9691-ce731221b7d2" />


#### 2️⃣ Create a file project_notes.txt.

 command-> touch project_notes.txt

<img width="828" height="87" alt="image" src="https://github.com/user-attachments/assets/1ecc04be-42fd-4e16-8e4f-b9ade203772c" />



#### 3️⃣ Set permissions: Owner can edit, group can read, others have no access.

<img width="451" height="142" alt="image" src="https://github.com/user-attachments/assets/87fe1372-ef2b-450e-8497-0884d6c21f9d" />


#### 4️⃣ Use ls -l to verify permissions

 command-> chmod 640 project_notes.txt

<img width="645" height="204" alt="image" src="https://github.com/user-attachments/assets/16af3b78-108b-4dc0-af16-b5312604b770" />


### C. **Log File Analysis with AWK, Grep & Sed**
#### 1️⃣.Create /devops_workspace Use grep to find all occurrences of the word "authentication failure".
grep -i "authentication failure" app.log
<img width="1129" height="327" alt="image" src="https://github.com/user-attachments/assets/3ba73f12-a209-484e-bc63-58140328a96c" />


#### 2️⃣ Use awk to extract timestamps and log levels.

<img width="642" height="218" alt="image" src="https://github.com/user-attachments/assets/8ceab1f3-201e-4680-940d-e97ed3248cb1" />


#### 3️⃣ Use sed to replace all IP addresses with [REDACTED] for security.

<img width="1162" height="282" alt="image" src="https://github.com/user-attachments/assets/d445cb06-2a3a-4b23-9405-a142d9319362" />




#### 4️⃣ Find the most frequent log entry using sort | uniq -c | sort -nr | head -10.


<img width="1040" height="173" alt="image" src="https://github.com/user-attachments/assets/f30cfc8a-f6d9-42c7-85ae-9782d5a77463" />



### D. **Volume Management & Disk Usage**

#### 1️⃣.Create a volume on aws.
<img width="1365" height="632" alt="image" src="https://github.com/user-attachments/assets/cf8e5bed-3a5c-482c-9df7-e02ca2e00e51" />


#### 2️⃣ Create a directory /mnt/devops_data.

<img width="582" height="104" alt="image" src="https://github.com/user-attachments/assets/0d9dd88d-49f1-41f4-9fc9-1d11f39e80be" />


#### 3️⃣ Mount a new volume (or loop device for local practice).
mkfs -t ext4 /dev/nvme1n1
mount -o loop /devops_disk.img /mnt/devops_disk.img /mnt/devops_data    
<img width="837" height="292" alt="image" src="https://github.com/user-attachments/assets/58b864c2-12f1-432c-96b5-c39d1d6f21e8" />


#### 4️⃣ Verify using df -h.

<img width="855" height="293" alt="image" src="https://github.com/user-attachments/assets/de2256f5-c052-461e-a686-88a68a96eaf4" />



### E. **Process Management & Monitoring**

#### 1️⃣.Start a background process (ping google.com > ping_test.log &).

<img width="512" height="57" alt="Screenshot (547)" src="https://github.com/user-attachments/assets/e5c74d34-fa44-4206-88dd-07e09308e7dc" />

#### 2️⃣ Use ps, top, and htop to monitor it.

1.ps -> ps aux | grep ping


<img width="512" height="84" alt="Screenshot (548)" src="https://github.com/user-attachments/assets/8bbe1b2a-20ba-45f9-b228-4361abc147e5" />

2.top

<img width="512" height="668" alt="Screenshot (549)" src="https://github.com/user-attachments/assets/ffa0668a-1c8f-44f7-b9cb-812d5af2f98a" />

3.htop 

<img width="512" height="702" alt="Screenshot (550)" src="https://github.com/user-attachments/assets/0c36d0b8-f784-48fb-a03b-f9d79283f8d7" />

#### 3️⃣ Kill the process and verify it's gone.

<img width="512" height="172" alt="Screenshot (551)" src="https://github.com/user-attachments/assets/3c909011-b0ad-4ec3-9613-e08b1996a455" />

