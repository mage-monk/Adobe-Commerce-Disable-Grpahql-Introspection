# Adobe-Commerce-Disable-Grpahql-Introspection
Adobe Commerce - Magento Disable Grpahql Introspection

**Step 1:** Login to https://console.adobecommerce.com/

**Step 2:** Select your project

**Step 3:** Goto Settings
<img width="308" alt="image" src="https://github.com/user-attachments/assets/b45063c2-80dd-4c80-ab7a-29d566104748" />

**Step 4**: Update the value as in screenshot

**Variable name:** ```env:MAGENTO_DC_GRAPHQL_DISABLE_INTROSPECTION```

**Value:** ```true```

![image](https://github.com/user-attachments/assets/9031a6db-48e2-4069-a9a9-ae8bf0c146bd)

**Step 5:** Save

**Step 6:** Clear or Flush the cache

**Step 7:** Validate the Introspection request with Grpahql

**Example introspection queries**

**Sample Request:**
```
query IntrospectionQuery {
  __schema {
    queryType {
      fields {
        name
        description
        type{
         name
         kind
        }
      }
    }
  }
}
```
Sample Response:
```
{
  "errors": [
    {
      "message": "GraphQL introspection is not allowed, but the query contained __schema or __type",
      "locations": [
        {
          "line": 2,
          "column": 3
        }
      ]
    }
  ],
  "status_code": 200
}
```
<img width="662" alt="image" src="https://github.com/user-attachments/assets/abbf6e3c-e839-48cf-a54e-b4fa5347182d" />


