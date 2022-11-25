
# Title

## Our API allows for the creation, deletion and to get information of a Manitoba bearberry variant.


## Endpoints and parameters 
1. ### Creating a new variant
 This endpoint is used to create a new variant.
   * Parameters  
      * Variant name (String)
  
2. ### Deleting a variant
This endpoint is used to delete an existing variant.
   * Parameters  
     * Variant ID (int)
   
3. ### Deleting a variant
This endpoint is used to get the information of the specified variant.
   * Parameters 
     * Variant ID (int)

## Resources

The following status codes indicate the success/failure of an API request:
* OK: All parameters correct, operation completed successfully.
* INVALID_REQUEST: The parameters were invalid, operation not completed.
* UNKNOWN_ERROR: The parameters were valid, but there was an error with the server that prevented the operation from being completed.

A successful API request with the following parameters:
* variantID: 10,
* harvestPercentage: 0.7,
* berryCount: 2048

Would return the following response:

```
{
    "plants": 
        [
            {
            "uniqueID": 7,
            "variantID": 10,
            "name": "Supreme Ultimate Bearberry Tenth Edition",
            "created": "2019-05-05",
            "percentHarvest": 0.7,
            "berryCount": 2048
            },
            {
            "uniqueID": 8,
            "variantID": 10,
            "name": "Beary Good Bearberry",
            "created": "2007-05-05",
            "percentHarvest": 0.7,
            "berryCount": 2048
            },
            {
            "uniqueID": 99,
            "variantID": 10,
            "name": "Genetically Modified Bearberry 1.24",
            "created": "2059-05-05",
            "percentHarvest": 0.7,
            "berryCount": 2048
            }
        ],
    "status": "OK"
}
```

Whereas an invalid API request with the following parameters:
* variantID: "The one that's kinda green, ya know?",
* harvestPercentage: 1000,
* berryCount: "Not enough"

Would return the following response:

```
{
    "plants": [],
    "status": "INVALID_REQUEST"
}
```

## Sample
