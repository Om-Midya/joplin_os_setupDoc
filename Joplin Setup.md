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
	![Screenshot from 2024-06-18 00-08-20](https://github.com/Om-Midya/joplin_os_setupDoc/assets/76900049/f06de766-49a3-4756-a64b-94fa28e83c40)

	
 	**Resolution**:  
	- Read The `BUILD.md` DOC that stated to install necessary packages for LINUX environment
	- I ran the following command 
	```bash
	sudo apt install build-essential libnss3 libsecret-1-dev rsync libgbm-dev libatk-bridge2.0-0 libgtk-3-dev libasound2
 	```
	- Then I re-ran the command and this time it was executed successfully
	![Screenshot from 2024-06-18 00-33-33](https://github.com/Om-Midya/joplin_os_setupDoc/assets/76900049/72d85d9a-21db-492e-82da-0b9f3bd17b7a)


2. **Error 2:** While trying to start React Native mobile application using `npm start`, I encountered an error related to watchman. The error message indicated that the user limit on the total number of `inotify` watches was reached.
![Screenshot from 2024-06-18 18-05-21](https://github.com/Om-Midya/joplin_os_setupDoc/assets/76900049/de00ef4f-74c0-4a3c-8e81-258dfd196f34)

	
 	**Resolution:**
	- To resolve this issue, I needed to increase the limit of `inotify` watches. This was done by running the following command in the terminal:
	```bash
	echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
 	```
	- This command increases the limit to 524288, which should be sufficient for most projects.
	- After This I re-ran `npm start`and this time it was executed successfully.
	![Screenshot from 2024-06-18 18-15-23](https://github.com/Om-Midya/joplin_os_setupDoc/assets/76900049/cb7e5d56-ce5b-4634-80f9-a7c17c905093)

## Screenshot of the Finalised Setup
1. Finally after Executing the commands as specified navigated to the project directory and ran the `yarn start` command and the desktop application was built :)
![Screenshot from 2024-06-17 23-44-05](https://github.com/Om-Midya/joplin_os_setupDoc/assets/76900049/ecac7a2b-c065-4a00-a129-3be7fe43a250)

2. This is how the mobile setup looks :)
![mob_jop_setup](https://github.com/Om-Midya/joplin_os_setupDoc/assets/76900049/0dde69c8-4baf-459e-8f76-0565f2939cc3)
