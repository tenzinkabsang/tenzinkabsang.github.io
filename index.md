# Facebook Pixel and Conversion API

For redundant setup like ours (*Pixel and Conversion api*) facebook uses deduplication method on their end
to ensure that the ad delivery system is able to differentiate between distinct and overlapping events.

*Documentation*
- [Handling Duplicate Pixel and Conversions API Events](https://developers.facebook.com/docs/marketing-api/conversions-api/deduplicate-pixel-and-server-events/)
- [Additional Duplicate Info](https://www.facebook.com/business/help/823677331451951?id=1205376682832142)
- [User Data Parameters](https://developers.facebook.com/docs/marketing-api/conversions-api/parameters/customer-information-parameters)

## ViewContent

*Pixel event data*


```
fbq("track", "ViewContent",
    {
        value: 11,
        currency: "USD",
        content_ids: [ "pe***" ],
        content_type: "product",
        content_category: "Earrings",
        content_name: "**** Earrings"
    },
    {
        eventID: "d7270c4a-00e4-42b2-ae6c-6eea085bd10a"
    })
```

*Conversion API data*
``` 
"data": [
    {
        "event_name": "ViewContent",
        "event_time": 1698171372,
        "event_source_url": "https://*******.com/***-earrings",
        "action_source": "website",
        "user_data": {
            "client_ip_address": "198.**.**.***",
            "client_user_agent": "mozilla/5.0 (windows nt 10.0; win64; x64),
            "em": [ Hashed email ],
            "ph": [ Hashed phone number ],
            "fn": [ Hashed first name ],
            "ln": [ Hashed last name ],
            "db": [ Hashed date of birth ],
            "ge": [ Hashed gender ],
            "ct": [ Hashed city ],
            "st": [ Hashed state ],
            "zp": [ Hashed zip ],
            "country": [ Hashed country ],
            "external_id": [ Hashed customer guid ]
        },
        "custom_data": {
            "value": 11,
            "currency": "USD",
            "content_ids": [
                "PE***"
            ],
            "content_type": "product",
            "content_category": "Earrings",
            "content_name": "**** Earrings"
        },
        "event_id": "d7270c4a-00e4-42b2-ae6c-6eea085bd10a"
    }
]
```


## Add to Cart

*Pixel event data*
```
fbq("track", "AddToCart",
    {
        value: 11,
        currency: "USD",
        content_ids: [ pe***" ],
        content_type: "product",
        content_category: "Earrings",
        content_name: "**** Earrings",
        contents: [
            {
                id: "PE***",
                quantity: 1,
                item_price: 11
            }]
    },
    {
        eventID: "f3cfb710-0eb7-4b96-8fc3-0702619b7423"
    }) 
```

*Conversion API data*
```
"data": [
    {
        "event_name": "AddToCart",
        "event_time": 1698171475,
        "event_source_url": "https://*******.com/***-earrings",
        "action_source": "website",
        "user_data": {
            "client_ip_address": "198.**.**.***",
            "client_user_agent": "mozilla/5.0 (windows nt 10.0; win64; x64),
            "em": [ Hashed email ],
            "ph": [ Hashed phone number ],
            "fn": [ Hashed first name ],
            "ln": [ Hashed last name ],
            "db": [ Hashed date of birth ],
            "ge": [ Hashed gender ],
            "ct": [ Hashed city ],
            "st": [ Hashed state ],
            "zp": [ Hashed zip ],
            "country": [ Hashed country ],
            "external_id": [ Hashed customer guid ]
        },
        "custom_data": {
            "value": 11,
            "currency": "USD",
            "content_ids": [
                "PE***"
            ],
            "content_type": "product",
            "content_category": "Earrings",
            "content_name": "**** Earrings",
            "contents": [
                {
                    "id": "PE***",
                    "quantity": 1,
                    "item_price": 11
                }
            ]
        },
        "event_id": "f3cfb710-0eb7-4b96-8fc3-0702619b7423"
    }
]
```

## Purchase

*Pixel event data*

```
fbq("track","Purchase",
    {
        value: 17,
        currency: "USD",
        content_type: "product",
        contents:[
            {
                id:"PE***",
                quantity:1
            }]
    },
    {
        eventID:"dbe86cb8-ce37-48ef-9809-df051d2646d2"
    })
```


*Conversion API data*

```
"data": [
    {
        "event_name": "Purchase",
        "event_time": 1698171646,
        "event_source_url": "https://*******.com/***-earrings",
        "action_source": "website",
        "user_data": {
            "client_ip_address": "198.**.**.***",
            "client_user_agent": "mozilla/5.0 (windows nt 10.0; win64; x64),
            "em": [ Hashed email ],
            "ph": [ Hashed phone number ],
            "fn": [ Hashed first name ],
            "ln": [ Hashed last name ],
            "db": [ Hashed date of birth ],
            "ge": [ Hashed gender ],
            "ct": [ Hashed city ],
            "st": [ Hashed state ],
            "zp": [ Hashed zip ],
            "country": [ Hashed country ],
            "external_id": [ Hashed customer guid ]
        },
        "custom_data": {
            "value": 17.00,
            "currency": "USD",
            "content_type": "product",
            "contents": [
                {
                    "id": "PE***",
                    "quantity": 1
                }
            ]
        },
        "event_id": "dbe86cb8-ce37-48ef-9809-df051d2646d2"
    }
]

```