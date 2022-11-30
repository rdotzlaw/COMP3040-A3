
# Manitoba Bearberry API Version 1.0.0

## Our API allows the user to get a list of BearyBerry plants that meet the provided parameters?

## Endpoints and parameters
1. ### Endpoints
   * https://bearberry.org/json

2. ### Parameters
    * variantId (uint): The ID of the variant. Optional
    * percentHarvest (float): The harvest percentage of the plant. Optional
    * berryCount (uint): Number of berries in a plant. Optional

## Resources

The following status codes indicate the success/failure of an API request:
* OK: All parameters correct, operation completed successfully.
* INVALID_REQUEST: The parameters were invalid, operation not completed.
* UNKNOWN_ERROR: The parameters were valid, but there was an error with the server that prevented the operation from being completed.

A successful API request with the following parameters:
* variantId: 10,
* percentHarvest: 0.7,
* berryCount: 2048

Would return the following response:

```
{
    "plants": 
        [
            {
            "uniqueId": 7,
            "variantId": 10,
            "name": "Supreme Ultimate Bearberry Tenth Edition",
            "created": "2019-05-05",
            "percentHarvest": 0.7,
            "berryCount": 2048
            },
            {
            "uniqueId": 8,
            "variantId": 10,
            "name": "Beary Good Bearberry",
            "created": "2007-05-05",
            "percentHarvest": 0.7,
            "berryCount": 2048
            },
            {
            "uniqueId": 99,
            "variantId": 10,
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
* variantId: "The one that's kinda green, ya know?",
* percentHarvest: 1000,
* berryCount: "Not enough"

Would return the following response:

```
{
    "plants": [],
    "status": "INVALID_REQUEST"
}
```

## Sample
```
https://bearberry.org/json
https://bearberry.org/json?variantId=12345
https://bearberry.org/json?percentHarvest=0.6
https://bearberry.org/json?berryCount=4
https://bearberry.org/json?variantId=23456&percentHarvest=0.8
https://bearberry.org/json?variantId=34567&berryCount=2
https://bearberry.org/json?percentHarvest=0.25&berryCount=8
https://bearberry.org/json?variantId=8765&percentHarvest=0.63&berryCount=12
```
