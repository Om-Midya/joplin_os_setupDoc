## Repository Name  
  
The repository I chose for this project is [Joplin](https://github.com/laurent22/joplin).  
  
## Steps Taken to Clone and Run Locally 
  
1. **Fork and Clone the repository**: I cloned the repository using the following command:  
  
    ```bash  
    git clone git@github.com:Om-Midya/joplin_os.git  
    ```  
2. **Navigate into the project directory**: After cloning, I navigated into the project directory using:  
  
    ```bash  
    cd joplin_os
    ```  
3. **Install dependencies**: I installed the necessary dependencies using:  
  
```bash  
    yarn install  
```  
4. **Run the project**: I navigated to the required directory, then I ran the project locally using:  
  
    ```bash  
    cd packages/app-desktop
    yarn start  
    ```  
## Errors Faced and Their Resolutions  
  
During the setup process, I encountered the following errors:  
  
1. **Error 1**: `electron package failed to build` 
	I faced this error when i ran `yarn install` for the first time
	![[Pasted image 20240618000824.png]]
	**Resolution**:  
	- Read The `BUILD.md` DOC that stated to install necessary packages for LINUX environment
	- I ran the following command 
	- ```❯ sudo apt install build-essential libnss3 libsecret-1-dev rsync libgbm-dev libatk-bridge2.0-0 libgtk-3-dev libasound2
	- Then I re-ran the command and this time it was executed successfully
	![[Screenshot from 2024-06-18 00-33-33.png]]
2. **Error 2:** While trying to start React Native mobile application using `npm start`, I encountered an error related to watchman. The error message indicated that the user limit on the total number of `inotify` watches was reached.
	![[Pasted image 20240618180525.png]]
	**Resolution:**
	- To resolve this issue, I needed to increase the limit of `inotify` watches. This was done by running the following command in the terminal:
	```bash
echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```
	- This command increases the limit to 524288, which should be sufficient for most projects.
	- After This I re-ran `npm start`and this time it was executed successfully.
	- ![[Pasted image 20240618181527.png]]
## Screenshot of the Finalised Setup
1. Finally after Executing the commands as specified navigated to the project directory and ran the `yarn start` command and the desktop application was built :)
![[Screenshot from 2024-06-17 23-44-05.png]]
2. This is how the mobile setup looks :)
![[mob_jop_setup.jpeg]]