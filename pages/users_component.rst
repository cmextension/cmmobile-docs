===============
Users component
===============

CM Mobile supports the following actions for Users component:

* Register for a new account
* Login
* Logout

Register
^^^^^^^^

GET request::

	http://yoursite.com/index.php?option=com_cmmobile&task=users.register&format=json&username=YOUR_USERNAME&password=YOUR_PASSWORD&name=YOUR_NAME&email=YOUR_EMAIL

Sample successful response::

	{
		"success":true,
		"message":"Your account was created. Successfully logged in.",
		"messages":null,
		"data":{
			"token":"YOUR_TOKEN"
		}
	}

Login
^^^^^

GET request::

	http://yoursite.com/index.php?option=com_cmmobile&task=users.login&format=json&username=YOUR_USERNAME&password=YOUR_PASSWORD

Sample successful response::

	{
		"success":true,
		"message":"Login succeeded.",
		"messages":null,
		"data":{
			"token":"YOUR_TOKEN"
		}
	}

Logout
^^^^^^

GET request::

	http://yoursite.com/index.php?option=com_cmmobile&task=users.logout&format=json&token=YOUR_TOKEN&checksum=YOUR_CHECKSUM

Sample successful response::

	{
		"success":true,
		"message":"Logout succeeded.",
		"messages":null,
		"data":null
	}