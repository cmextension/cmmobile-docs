======================
CM Live Deal component
======================

Get deals
^^^^^^^^^

GET request::

	http://yoursite.com/index.php?option=com_cmmobile&task=cmlivedeal.getDeals&format=json&start=PAGINATION_START&limit=PAGINATION_LIMIT

"start" and "limit" are the same to "limitstart" (or "start") and "limit" in Joomla!'s pagination.

Sample successful response::

	{
		"success":true,
		"message":null,
		"messages":null,
		"data":{
			"total":"TOTAL_DEALS",
			"deals":[{
				"id":"DEAL_ID",
				"title":"DEAL_TITLE",
				"description":"DEAL_DESCRIPTION",
				"fine_print":"DEAL_FINE_PRINT",
				"starting_time":"DEAL_STARTING_TIME",
				"merchant_name":"MERCHANT_NAME",
				"merchant_about":"MERCHANT_ABOUT",
				"merchant_address":"MERCHANT_ADDRESS",
				"merchant_latitude":"MERCHANT_LATITUDE",
				"merchant_longitude":"MERCHANT_LONGITUDE",
				"merchant_phone":"MERCHANT_PHONE",
				"merchant_website":"MERCHANT_WEBSITE",
				"merchant_merchant_facebook":"MERCHANT_FACEBOOK",
				"merchant_twitter":"MERCHANT_TWITTER",
				"merchant_pinterest":"MERCHANT_PINTEREST",
				"merchant_google_plus":"MERCHANT_GOOGLE_PLUS",
				"ending_time":"DEAL_ENDING_TIME",
				"thumbnail":"DEAL_THUMBNAIL"
			}, {
			...
			}]
		}
	}

Get deals with filters
^^^^^^^^^^^^^^^^^^^^^^

GET request::

	http://yoursite.com/index.php?option=com_cmmobile&task=cmlivedeal.getDeals&format=json&start=PAGINATION_START&limit=PAGINATION_LIMIT&keyword=KEYWORD&category=CATEGORY_ID&city=CITY_ID&latitude=YOUR_LATITUDE&longitude=YOUR_LONGITUDE

CATEGORY_ID is

* the ID of an existing category in CM Live Deal if only get the deals in that category.
* 0 for getting the deals in all categories.

CITY_ID is

* the ID of an existing city in CM Live Deal if only get the deals in that city.
* 0 for getting the deals in all cities.
* -1 for getting the deals near your location, you need to provide your latidue and longitude.

Get coupons
^^^^^^^^^^^

GET request::

	http://yoursite.com/index.php?option=com_cmmobile&task=cmlivedeal.getCoupons&format=json&token=YOUR_TOKEN&checksum=YOUR_CHECKSUM&start=PAGINATION_START&limit=PAGINATION_LIMIT

Sample successful response::

	{
		"success":true,
		"message":null,
		"messages":null,
		"data":{
			"total":"TOTAL_COUPONS",
			"coupons":[{
				"id":"COUPON_ID",
				"code":"COUPON_CODE",
				"created":"DATE_TIME_WHEN_COUPON_CREATED",
				"deal_name":"DEAL_NAME",
				"deal_ending_time":"DEAL_ENDING_TIME",
				"deal_fine_print":"DEAL_FINE_PRINT",
				"deal_expired":"TRUE_IF_DEAL_IS_EXPIRED",
				"merchant_name":"MERCHANT_NAME",
				"merchant_about":"MERCHANT_ABOUT",
				"merchant_address":"MERCHANT_ADDRESS",
				"merchant_latitude":"MERCHANT_LATITUDE",
				"merchant_longitude":"MERCHANT_LONGITUDE",
				"merchant_phone":"MERCHANT_PHONE",
				"merchant_website":"MERCHANT_WEBSITE",
				"merchant_merchant_facebook":"MERCHANT_FACEBOOK",
				"merchant_twitter":"MERCHANT_TWITTER",
				"merchant_pinterest":"MERCHANT_PINTEREST",
				"merchant_google_plus":"MERCHANT_GOOGLE_PLUS"
				}, {
				...
				}]
		}
	}

Get coupons with filters
^^^^^^^^^^^^^^^^^^^^^^^^

GET request::

	http://yoursite.com/index.php?option=com_cmmobile&task=cmlivedeal.getCoupons&format=json&token=YOUR_TOKEN&checksum=YOUR_CHECKSUM&start=PAGINATION_START&limit=PAGINATION_LIMIT&keyword=KEYWORD&status=STATUS

STATUS is

* -1 for getting all coupons.
* 1 for only getting active coupons.
* 0 for only getting expired coupons.