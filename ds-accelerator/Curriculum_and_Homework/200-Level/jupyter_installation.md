# Jupyter Installation Instructions

## Mac Instructions
1. Open Terminal
	* Ensure you have Python installed by testing the following code: `python --version` OR `python3 --version`
	* If python is not pre-installed, go to [python.org](https://www.python.org/downloads/) to install it to your system. Stick with the recommended defaults.
2. Ensure you have pip installed by testing the following code: `pip list` OR `pip3 list`
	* If there's an error saying you do not have it installed, enter the following into your terminal: `curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py` and then `python3 get-pip.py` (remember that it could be `python` and not `python3` on your computer)
3. Make a specific folder for your homegrown work if you haven't already, for easy organization! 
	* If you need to make a new folder, use `mkdir folder-name`
	* Once you've got that folder, run `cd folder-name`
4. Now that you are inside your folder, we will install the virtual environment: `python3 -m pip install virtualenv` OR `python -m pip install virtualenv`
5. Then, we'll create and activate the virtual environment by running the following:
	* Create a name for your environment: `python -m virtualenv my-env-name` 
	* Run `source my-env-name/bin/activate`
	* Now, you should notice that the home directory has changed to now show `my-env-name`
6. You're inside the environment at this point, so this is where you'll install the following packages:
	* First, set up for jupyter notebooks:
		* `pip install jupyter`
		* `pip install ipython`
		* `pip install ipykernel`
		* `ipython kernel install --user --name=my-env-name`
		* `python -m ipykernel install --user --name=my-env-name`
		* `pip install bash_kernel`
		* `pip install bash_kernel.install`
	* Then, add some of the following packages:
		* `pip install pandas`
		* `pip install matplotlib`
		* `pip install numpy`
		* `pip install scipy`
		*  Note that you'll need to pip install any new packages that we introduce throughout the rest of the 200 level. 
7. While still in the environment, open the jupyter notebook interface: `jupyter notebook`
	* A new tab should open up in your browser that says localhost:8888 where you can open a new Python notebook file and run your code!
8. Once you are done coding in your notebooks, ensure you deactivate the virtual environment. 
	* Press ctrl and C to shut down the server
	* Deactivate to end the environment

The next time you need to work in jupyter notebooks, start from step 7. You should be able to select the virtual environment from the dropdown in the top right. 

## Windows Instructions
1. Open Command Prompt (Make sure it's not the powershell)
2. Check if python is installed by doing `python --version` OR `python3 --version`
3. If python is not installed, go to [python.org](https://www.python.org/downloads/) to install it to your system.
4. Make a specific folder for your homegrown work if you haven't already. Navigate to the location where your code and projects will be stored. You can use `cd` to go to that location.
5. Next, install pip by doing the following: `curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py` and then `python3 get-pip.py` OR `python get-pip.py`
6. Then, install the virtual environment: `python -m pip install virtualenv`
7. Set up your virtual environment.
	* Create a name for your virtual environment: `python3 -m virtualenv my-env-name` 
	* Then run `source my-env-name/bin/activate`
	* You should notice that the home directory has changed to now show `my-env-name`
8. Once inside the environment, you'll install the following packages:
	* First, set up for jupyter notebooks:
		* `pip install jupyter`
		* `pip install ipython`
		* `pip install ipykernel`
		* `ipython kernel install --user --name=my-env-name`
		* `python -m ipykernel install --user --name=my-env-name`
		* `pip install bash_kernel`
		* `python -m bash_kernel.install`
	* Then, add some of the following packages:
		* `pip install pandas`
		* `pip install matplotlib`
		* `pip install numpy`
		* `pip install scipy`
		*  Note that you'll need to pip install any new packages that we introduce throughout the rest of the 200 level.
9. While still in the environment, open the jupyter notebook interface: `jupyter notebook`
	* A new tab should open up in your browser that says localhost:8888 where you can open a new Python notebook file and run your code!
10. Once you are done coding in your notebooks, ensure you deactivate the virtual environment. 
	* Press ctrl and C to shut down the server
	* Deactivate to end the environment
	
The next time you need to work in jupyter notebooks, start from step 7. You should be able to select the virtual environment from the dropdown in the top right. 