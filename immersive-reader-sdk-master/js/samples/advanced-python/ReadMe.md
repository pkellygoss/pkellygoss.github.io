# Immersive Reader - Python Sample

----------------------------------

## Follow these steps to get the sample up and running

### Create an Immersive Reader resource and configure Azure Active Directory (Azure AD) authentication

1. Follow the instructions at https://docs.microsoft.com/en-us/azure/cognitive-services/immersive-reader/aadauth to create an Immersive Reader resource with a custom subdomain and configure Azure Active Directory (Azure AD) authentication in your Azure tenant.  
You will need some of the values created here when configuring the sample project properties. Save the output of your session into a text file for future reference.

### Installation on Windows

1. Install [Python](https://www.python.org/downloads/). Choose custom installation and set the installation path as your root folder e.g. `C:\Python37-32\`.
2. Open Command Prompt and `cd` to the Python Scripts folder e.g `cd C:\Python37-32\Scripts`.
3. `pip` is the preferred installer program, [Learn more](https://docs.python.org/3/installing/index.html). Starting with Python 3.4, it is included by default with the Python binary installers.
4. Add the path of your pip installation to your PATH variable e.g. `setx PATH "%PATH%;C:\Python37-32\Scripts"`.
5. Install Flask by running `pip install flask`.
6. Install [Jinja](http://jinja.pocoo.org/docs/2.10/intro/#installation), a full featured template engine for Python by running `pip install Jinja2`.
7. Install virtualenv by running `pip install virtualenv`. It's a tool to create isolated Python environments [Learn more](https://virtualenv.pypa.io/en/latest/).
8. Install virtualenvwrapper-win by running `pip install virtualenvwrapper-win`. The idea behind virtualenvwrapper is to ease usage of virtualenv [Learn more](https://pypi.org/project/virtualenvwrapper-win/).
9. Install the [requests module](https://pypi.org/project/requests/2.7.0/) by running `pip install requests`. Requests is an Apache2 Licensed HTTP library, written in Python, for human beings.
10. Install the [python-dotenv module](https://github.com/theskumar/python-dotenv) by running `pip install python-dotenv`. Reads the key-value pair from .env file and adds them to environment variable.

#### WINDOWS USAGE

Using [Git](https://git-scm.com/), open a Command Prompt and run `git clone https://github.com/Microsoft/immersive-reader-sdk` to a preferred folder then:

1. Make a virtual environment by opening a Command Prompt and run `mkvirtualenv advanced-python`.
2. `cd` to the sample project root folder on your local machine e.g. `cd C:\immersive-reader-sdk\js\samples\advanced-python`.
3. Connect the sample project with the environment by running `setprojectdir .`. This maps the newly created virtual environment to the sample project root folder. The project should now be active and you'll see something like `(advanced-python) C:\immersive-reader-sdk\js\samples\advanced-python>` in the Command Prompt.
4. Ensure the environment is activated by running the `activate` command. If it wasn't before, the `(advanced-python)` prefix should now be present.
5. To deactivate the environment run `deactivate`. The `(advanced-python)` prefix should now be gone as the environment is now deactivated.
6. To reactivate the environment run `workon advanced-python` from the sample project root folder.
7. Create a file called .env and add the following to it, supplying the corresponding information where appropriate:

```text
TENANT_ID={YOUR_TENANT_ID}
CLIENT_ID={YOUR_CLIENT_ID}
CLIENT_SECRET={YOUR_CLIENT_SECRET}
SUBDOMAIN={YOUR_SUBDOMAIN}
```

You need property values from the Azure AD authentication configuration step above for this part. Refer back to the text file you saved of that session. See the details section below.  

Property value details:

* TENANT_ID     => Azure subscription TenantId  
* CLIENT_ID     => Azure AD ApplicationId  
* CLIENT_SECRET => Azure AD Application Service Principal password  
* SUBDOMAIN     => Immersive Reader resource subdomain (resource 'Name' if the resource was created in the Azure portal, or 'CustomSubDomain' option if the resource was created with Azure CLI Powershell. Check the Azure portal for the subdomain on the Endpoint in the resource Overview page, for example, 'https://[SUBDOMAIN].cognitiveservices.azure.com/')

8. Run the sample project by entering `flask run` from the sample project root folder.
9. Open a browser and navigate to [http://127.0.0.1:5000/](http://127.0.0.1:5000/)

### Installation on OSX

Using [Git](https://git-scm.com/), Launch Terminal and run `git clone https://github.com/Microsoft/immersive-reader-sdk` to a preferred folder then:

1. Install [Python](https://www.python.org/downloads/). The Python root folder e.g. `Python37-32` should now be in the Applications folder.
2. Launch Terminal and `cd` to the project sample folder e.g `cd immersive-reader-sdk/js/samples/advanced-python`.
3. `pip` is the preferred installer program, [Learn more](https://docs.python.org/3/installing/index.html). Starting with Python 3.4, it is included by default with the Python binary installers. However an easy way to use it from any path is to install Pip for the current user. Launch Terminal and run `curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py`, then run `python get-pip.py --user` to install Pip for the currently signed-in user to avoid permissions issues.
4. Add the path of your pip installation to your PATH variable.
   * Launch a new Terminal window.
   * Run the following command: `sudo nano /etc/paths`.
   * Enter your password, when prompted.
   * Go to the bottom of the file, and enter the path you wish to add as the last item of the list e.g. `PATH=$PATH:/usr/local/bin`.
   * Hit control-x to quit.
   * Enter `Y` to save the modified buffer.
   * That's it! To test it, in new terminal window, type: `echo $PATH`.
5. Install Flask by running `pip install flask --user`.
6. Install [Jinja](http://jinja.pocoo.org/docs/2.10/intro/#installation), a full featured template engine for Python by running `pip install Jinja2 --user`.
7. Install virtualenv by running `pip install virtualenv --user`. It's a tool to create isolated Python environments [Learn more](https://virtualenv.pypa.io/en/latest/).
8. Install virtualenvwrapper by running `pip install virtualenvwrapper --user`. The idea behind virtualenvwrapper is to ease usage of virtualenv [Learn more](https://virtualenvwrapper.readthedocs.io/en/latest/).
9. Install the [requests module](https://pypi.org/project/requests/2.7.0/) by running `pip install requests --user`. Requests is an Apache2 Licensed HTTP library, written in Python, for human beings.
10. Install the [python-dotenv module](https://github.com/theskumar/python-dotenv) by running `pip install python-dotenv --user`. Reads the key-value pair from .env file and adds them to environment variable.
11. Choose a place where you would like to keep your virtual environments, e.g. `mkdir ~/.virtualenvs`.

#### OSX USAGE

1. `cd` to the sample project root folder e.g. `cd immersive-reader-sdk/js/samples/advanced-python`.
2. Make a virtual environment by launching Terminal and run `mkvirtualenv -p /usr/local/bin/python3 advanced-python`.
3. Create a file called .env and add the following to it, supplying the corresponding information where appropriate:

```text
TENANT_ID={YOUR_TENANT_ID}
CLIENT_ID={YOUR_CLIENT_ID}
CLIENT_SECRET={YOUR_CLIENT_SECRET}
SUBDOMAIN={YOUR_SUBDOMAIN}
```

4. Run the sample project by entering `flask run` from the sample project root folder.
5. Open a browser and navigate to [http://127.0.0.1:5000/](http://127.0.0.1:5000/)

Copyright (c) Microsoft Corporation. All rights reserved.

Licensed under the MIT License.