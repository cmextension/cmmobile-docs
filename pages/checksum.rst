========
Checksum
========

Checksum is one of many methods in CM Mobile to ensure that request comes from your mobile application and comes from your users.

Checksum is a MD5 string of: token, Joomla! username and secret key. You can set your secret key in CM Mobile's configuration.

Sample PHP code for generating checksum::

	$string = $token . $username . $secretKey;
	$checksum = md5($string);

When you send your requests which require authentication, you need to include your token and your checksum in your request. If testing mode is enabled in CM Mobile's configuration, you only need to include token.