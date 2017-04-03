# Clips

This repository maintains all of the clips that are used in FullContact Social Clip browser extension.

### Contributing

Coming Soon

### Clip Definition Schema

```
{
    "name": "",
    "enabled": true|false,
    "handles": [...],
    "prep": {
        //Optional; Supports one
        "click": {
            "elementSelector": "", //Selector to Click
            "waitForSelector": "" //Element that should be present before prep is complete
        },
        "scroll": {
            "to": 0, //Integer of pixels to scroll,
            //Supports one
            "wait": 0, //Integer of the amount of seconds to wait before prep is complete,
            "waitForSelector": "" //Element that should be present before prep is complete
        }
    },
    "socialUsername": {
        //Supports one
        "selector": "", //selector to the element that contains the username, can be used with "attribute"
        "attribute": "", //use with selector, default: textContent
        "regex": "", //regexp to use on window.location.pathname
        "regexFlags: "", //Optional; any regex flags you want used, i.e. 'gi'
        "searchParam": "", //name of the searchParam from the query string to use
        "pathIndex": 0 //int of the index of the path token it should use as the username
    },
    "socialUrl": {
        //Optional; Defaults to window.location.href
        "selector": "",
        "regex": "", //regexp to use on window.location.pathname
        "regexFlags: "", //Optional; any regex flags you want used, i.e. 'gi'
        "attribute": "" //defaults to textContent
    }
    "fields": {
        /*
            Supported Types:
            - name
            - photo
            - generalLocation
            - birthday
            - emails
            - phones
            - title
            - company
            - ims
            - website
            - gender
            - additionalSites
        */

        <type>: {
            //Required
            "value": {
                //Use one of selector or xpath
                "selector": "", //selector to select all elements of type
                "attribute": "", //Optional; attribute to use from elements; Default: textContent
                "xpath": "", //xpath to select all elements or values
                "regex": "", //Optional; regex that should be applied to all values
                "regexFlags: "", //Optional; any regex flags you want used, i.e. 'gi'
                "blacklist": [], //Optional; any words you values that should be filtered
                "searchParam": "", //Optional; applies only to "additionalSites" used to pull url from querystring
                "dateFormat": "" //Optional; applies only to "birthday"
            },
            //Optional
            "label": {
                //Use one of selector or xpath
                "selector": "", //selector to select all elements of type
                "attribute": "", //Optional; attribute to use from elements; Default: textContent
                "xpath": "", //xpath to select all elements or values
                "regex": "", //Optional; regex that should be applied to all values
                "regexFlags: "", //Optional; any regex flags you want used, i.e. 'gi'
                "blacklist": [], //Optional; any words you values that should be filtered
            }
        }
    }
}
```

### License