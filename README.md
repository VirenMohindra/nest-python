# Python Works with Nest Sample App


NOTE: This is not an official Google product.

## 1. Introduction

This is a simple web app that talks to the Works with Nest API using Python and  
the Flask web framework. You'll use a Nest product to be accessed from the app.  
   
—————————————————————————————————————

## 2. Requirements

* The sample code
* Basic knowledge of HTML, CSS, Javascript, and Python (to change the sample)
* Python interpreter 2.7.x
* At least one Nest device, such as Nest Thermostat, Nest Cam, or Nest Protect

—————————————————————————————————————

## 3. Install dependencies

This project uses Python's PIP to manage dependent packages.

1. Install PIP and Python 2.7: 
   [https://zaiste.net/posts/installing\_python\_27\_on\_osx\_with\_homebrew/](https://zaiste.net/posts/installing_python_27_on_osx_with_homebrew/)<br/>
1. Download the sample app and install the dependencies.
1. (Optional) Use Redis sessions  
   You can use Redis for Flask server-side sessions instead of the default Flask cookie based sessions.
   *  Install Redis - see [https://redis.io/topics/quickstart](http://redis.io/topics/quickstart).
   *  Uncomment redis in requirements.txt. Continue with steps below.
1. (Optional) Use REST streaming  
   You can use REST Streaming server-sent events instead of polling the API server.  
   *  Update static/js/app.js and un-comment listenRESTStreamClient().  Comment out pollRESTClient().  
   *  Uncomment sseclient-py and urllib3 in requirements.txt. Continue with steps below.  
  

In a terminal window, go to the python-sample directory and run the following 
commands.

Spin up a virtual environment:

```
$ pip install virtualenv
$ virtualenv env
$ . env/bin/activate
```

Install the dependencies (virtualenv):

```
(env) $ pip install -r requirements.txt
```

—————————————————————————————————————

## 4. Set up your Nest device

If you don't already have a Nest device set up and associated with your  
home.nest.com account, use one of the following procedures.

Set up a Nest device with a Mac or Windows computer

-OR-

Set up a Nest device with the Nest App

-OR- 

Use the Nest Home Simulator to simulate a Nest device

—————————————————————————————————————

## 5. Create a cloud product at console.developers.nest.com

Use the same account that you used for your Nest device. 

For the redirect URI, use http://localhost:5000/callback

For the permissions, select read/write corresponding with your Nest product. For 
example,  
if your Nest product is a Thermostat, select Thermostat Read/Write.

In order to authorize your Nest integration, you need a Product ID and Product  
Secret. The next step is to set the product ID and product secret as environment  
variables so these values can be retrieved by the application.

If you are using Linux or MacOS, open a Bash shell and type the commands below  
(substitute your product ID and secret you copied from your product page):

```
$ export PRODUCT_ID='Your product ID here'
$ export PRODUCT_SECRET='Your product secret here'
```

—————————————————————————————————————

## 6. Run the app

If it's not already running, spin up the virtual environment:


```
$ virtualenv env
$ . env/bin/activate
```

Run app.py:


```
$ python app.py
``` 
  
**(Optional) Use Redis sessions**  
* Verify you have the redis server installed in the [Install dependencies](#3._install_dependencies) section.
* Open a shell and run the redis server from the command line:
```
$ redis-server
```
*  Open another shell (or the same one if redis-server is run in the background) and    
   run app.py with command-line argument '--use-redis' instead:
 
Run app.py (with Redis server-side sessions): 
```
$ python app.py --use-redis
```  
   
  

If you are prompted, click to allow incoming network connections.

—————————————————————————————————————

## 7. Open http://localhost:5000/

Click **Login**.

When we log in, we are redirected to the Nest Authorization screen.  
On the Nest Authorization screen, click **Accept**.

When we accept the integration, the Nest Authorization screen redirects to the  
Redirect URL configured for our product integration 
(http://localhost:5000/callback).

—————————————————————————————————————

## 8. See the app in a mobile format

In Chrome, right-click the app and select **Inspect**.  
In the Responsive pulldown menu, select another format, such as iPhone 6.  
Click the icon that looks like a phone (**Toggle device toolbar**).

## Companion codelab

[10 Tips for a successful Nest integration](https://codelabs.developers.google.com/codelabs/nest-ten-tips-for-success)

## Contributing

Contributions are always welcome and highly encouraged.

See [CONTRIBUTING](CONTRIBUTING.md) for more information on how to get started.

## License

Apache 2.0 - See [LICENSE](LICENSE) for more information.
