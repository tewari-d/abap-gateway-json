# abap-gateway-json

## ABAP JSON Generator
Generate JSON payloads for POST/PUT requests for Gateway Client/Postman

This is a simple program that can be used to automatically generate JSON payload templates to test PUT/POST operations for odata services.

PUT/POST requests need a payload along with the url to be executed. So for testing **POST/PUT** in an odata service generally ABAPers *(at least ME used to)* use the following techniques to get the JSON payload for firing requests:

-   Redefine GET_ENTITY of the same entityset to receive data and then use the same as payload, and then delete the redefinition at the end. This costs us additional time.
-   Fire GET_ENTITY of a different entityset and replace all the properties in the result data with the required entityset. Again this costs additional time and is highly prone to errors.
-   Generate whole JSON from scratch by looking at the format of above json. LOTS of time needed if there are lots of properties in the entity.

To save some time, this ABAP program *(utility)* can generate JSON payload for you to fire POST/PUT requests.

### Inputs Of Program:
1. Project Name *(Odata service)*
2. EntitySet name *(EntitySet for which JSON is needed)*
3. File Name *(file path If Generated JSON is to be saved in a file)*
4. Expand Navigations ? *(Expand Navigations in case of deep entity)*
5. Copy to Clipboard ? *(Copy Generted JSON to clipboard ?)*

### Known Bugs

One limitation is that in the generated JSON the program places "" as values of properties. Now for the Integer type properties the value should come without the quotes. The plan going forward is to populate initial values as property values e.g. 0 for integer, "" for Strings, "false" for boolean etc. that can be edited by the users.

Also, currently, very less emphasis is laid on performance of the program which will surely be enhanced in future versions. 

Your valuable feedback is highly welcome.
