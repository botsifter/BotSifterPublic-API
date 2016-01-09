# BotSifterPublic-API

Welcome to the BotSifter API. Using the API will provide you access to our current bot/user-agent lists. *(Note Anonymous access will limit the lists to the top 10 entries.  Register for FREE if you want the entire list. [BotSifter Registration](http://www.botsifter.com)

Our Bot/UA ranks are updated daily, so check back often..  But not to Often.  There is a limit on the number of api calls you can make per day in order to give everyone a chance to get thier crack at our data as well.  (The current limit is 5 calls per day)

## BotSifter API


### Get Filter List
The getFilterList endpoint provides a method to obtaining the bot/ua list in json format. For anonymous uses, use the GET method, for registered user use the POST method with your user credentials supplied in json format.

### GET - Anonymous - Top 10 Only

```curl -X GET http://www.botsifter.com/api/getFilterList```

### POST - Registered Users - Full List


```curl -H "Content-Type: application/json" --data '{"auth": {"userid":"[USERID]","password":"[PASSWORD]"}}' -X POST http://www.botsifter.com/api/getFilterList ```

### Auth JSON Format

```
{
  "auth": {
    "userid": "[USERID]",
    "password": "[PASSWORD]"
  }
}

```

### Return JSON Format
Field | Description
----- | -----------
Status | Contains the Status of the API call [success / failed / Unauthorized / ]
Referrers / UserAgents | Contains the array of either Referrers or UserAgents
DateAdded | The Date added to the list
Rank | The Rank of the Bot/UA
Score | The Score of the Bot/UA
Type | The Type of the Bot/UA

*Note: IP's are for future use*


```
    {
      "Status": "success",
      "Referrers": [{
        "Referrer": "floating-share-buttons.com",
        "DateAdded": "2016-01-08 00:00:00",
        "Rank": "1",
        "Score": "1299780",
        "Type": "Spam Referrer"
      }, {
        "Referrer": "get-free-social-traffic.com",
        "DateAdded": "2016-01-08 00:00:00",
        "Rank": "2",
        "Score": "1177230",
        "Type": "Spam Referrer"
      }],
      "UserAgents": [{
        "Referrer": "Mozilla\/5.0 (compatible; Yahoo! Slurp; http:\/\/help.yahoo.com\/help\/us\/ysearch\/slurp)",
        "DateAdded": "2016-01-08 00:00:00",
        "Rank": "1",
        "Score": "1345.96",
        "Type": "Valid Bot"
      }, {
        "Referrer": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10_10_1) AppleWebKit\/600.2.5 (KHTML, like Gecko) Version\/8.0.2 Safari\/600.2.5 (Applebot\/0.1; +http:\/\/www.apple.com\/go\/applebot)",
        "DateAdded": "2016-01-08 00:00:00",
        "Rank": "2",
        "Score": "734.92",
        "Type": "Valid Bot"
      }],
      "IPs": []
    }



```

