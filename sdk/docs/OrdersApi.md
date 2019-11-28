# lusid.OrdersApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_order**](OrdersApi.md#get_order) | **GET** /api/orders/{scope}/{id} | [EXPERIMENTAL] Fetch a given order.
[**list_orders**](OrdersApi.md#list_orders) | **GET** /api/orders/{scope} | [EXPERIMENTAL] Fetch the last pre-AsAt date version of each order in scope (does not fetch the entire history).
[**upsert_order_properties**](OrdersApi.md#upsert_order_properties) | **POST** /api/orders/{scope}/properties | [EXPERIMENTAL] Upsert; update properties on existing Orders with given ids.
[**upsert_orders**](OrdersApi.md#upsert_orders) | **POST** /api/orders/{scope} | [EXPERIMENTAL] Upsert; update existing orders with given ids, or create new orders otherwise.


# **get_order**
> Order get_order(scope, id, as_at=as_at, property_keys=property_keys)

[EXPERIMENTAL] Fetch a given order.

### Example

* OAuth Authentication (oauth2):
```python
from __future__ import print_function
import time
import lusid
from lusid.rest import ApiException
from pprint import pprint
configuration = lusid.Configuration()
# Configure OAuth2 access token for authorization: oauth2
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Defining host is optional and default to http://localhost
configuration.host = "http://localhost"
# Create an instance of the API class
api_instance = lusid.OrdersApi(lusid.ApiClient(configuration))
scope = 'scope_example' # str | The scope to which the order belongs.
id = 'id_example' # str | The order's unique identifier.
as_at = '2013-10-20T19:20:30+01:00' # datetime | The asat datetime at which to retrieve the order. Defaults to              return the latest version of each order if not specified. (optional)
property_keys = ['property_keys_example'] # list[str] | A list of property keys from the \"Orders\" domain to decorate onto the order.              These take the format {domain}/{scope}/{code} e.g. \"Orders/system/Name\". (optional)

try:
    # [EXPERIMENTAL] Fetch a given order.
    api_response = api_instance.get_order(scope, id, as_at=as_at, property_keys=property_keys)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling OrdersApi->get_order: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **scope** | **str**| The scope to which the order belongs. | 
 **id** | **str**| The order&#39;s unique identifier. | 
 **as_at** | **datetime**| The asat datetime at which to retrieve the order. Defaults to              return the latest version of each order if not specified. | [optional] 
 **property_keys** | [**list[str]**](str.md)| A list of property keys from the \&quot;Orders\&quot; domain to decorate onto the order.              These take the format {domain}/{scope}/{code} e.g. \&quot;Orders/system/Name\&quot;. | [optional] 

### Return type

[**Order**](Order.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/plain, application/json, text/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | The order matching the given identifier. |  -  |
**400** | The details of the input related failure |  -  |
**0** | Error response |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_orders**
> ResourceListOfOrder list_orders(scope, as_at=as_at, property_keys=property_keys)

[EXPERIMENTAL] Fetch the last pre-AsAt date version of each order in scope (does not fetch the entire history).

### Example

* OAuth Authentication (oauth2):
```python
from __future__ import print_function
import time
import lusid
from lusid.rest import ApiException
from pprint import pprint
configuration = lusid.Configuration()
# Configure OAuth2 access token for authorization: oauth2
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Defining host is optional and default to http://localhost
configuration.host = "http://localhost"
# Create an instance of the API class
api_instance = lusid.OrdersApi(lusid.ApiClient(configuration))
scope = 'scope_example' # str | The scope to which the orders belong.
as_at = '2013-10-20T19:20:30+01:00' # datetime | The asat datetime at which to retrieve the orders. Defaults to              return the latest version of each order if not specified. (optional)
property_keys = ['property_keys_example'] # list[str] | A list of property keys from the \"Orders\" domain to decorate onto each order.              These take the format {domain}/{scope}/{code} e.g. \"Orders/system/Name\". (optional)

try:
    # [EXPERIMENTAL] Fetch the last pre-AsAt date version of each order in scope (does not fetch the entire history).
    api_response = api_instance.list_orders(scope, as_at=as_at, property_keys=property_keys)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling OrdersApi->list_orders: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **scope** | **str**| The scope to which the orders belong. | 
 **as_at** | **datetime**| The asat datetime at which to retrieve the orders. Defaults to              return the latest version of each order if not specified. | [optional] 
 **property_keys** | [**list[str]**](str.md)| A list of property keys from the \&quot;Orders\&quot; domain to decorate onto each order.              These take the format {domain}/{scope}/{code} e.g. \&quot;Orders/system/Name\&quot;. | [optional] 

### Return type

[**ResourceListOfOrder**](ResourceListOfOrder.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/plain, application/json, text/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Orders in scope. |  -  |
**400** | The details of the input related failure |  -  |
**0** | Error response |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **upsert_order_properties**
> UpsertOrderPropertiesResponse upsert_order_properties(scope, request=request)

[EXPERIMENTAL] Upsert; update properties on existing Orders with given ids.

### Example

* OAuth Authentication (oauth2):
```python
from __future__ import print_function
import time
import lusid
from lusid.rest import ApiException
from pprint import pprint
configuration = lusid.Configuration()
# Configure OAuth2 access token for authorization: oauth2
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Defining host is optional and default to http://localhost
configuration.host = "http://localhost"
# Create an instance of the API class
api_instance = lusid.OrdersApi(lusid.ApiClient(configuration))
scope = 'scope_example' # str | The scope to which the orders belong.
request = [lusid.UpsertOrderPropertiesRequest()] # list[UpsertOrderPropertiesRequest] | A collection of order property upsert requests. (optional)

try:
    # [EXPERIMENTAL] Upsert; update properties on existing Orders with given ids.
    api_response = api_instance.upsert_order_properties(scope, request=request)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling OrdersApi->upsert_order_properties: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **scope** | **str**| The scope to which the orders belong. | 
 **request** | [**list[UpsertOrderPropertiesRequest]**](UpsertOrderPropertiesRequest.md)| A collection of order property upsert requests. | [optional] 

### Return type

[**UpsertOrderPropertiesResponse**](UpsertOrderPropertiesResponse.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/plain, application/json, text/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | An upsert order properties response. |  -  |
**400** | The details of the input related failure |  -  |
**0** | Error response |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **upsert_orders**
> OrderSet upsert_orders(scope, request=request)

[EXPERIMENTAL] Upsert; update existing orders with given ids, or create new orders otherwise.

### Example

* OAuth Authentication (oauth2):
```python
from __future__ import print_function
import time
import lusid
from lusid.rest import ApiException
from pprint import pprint
configuration = lusid.Configuration()
# Configure OAuth2 access token for authorization: oauth2
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Defining host is optional and default to http://localhost
configuration.host = "http://localhost"
# Create an instance of the API class
api_instance = lusid.OrdersApi(lusid.ApiClient(configuration))
scope = 'scope_example' # str | The scope to which the orders belong.
request = lusid.OrderSetRequest() # OrderSetRequest | The collection of order requests. (optional)

try:
    # [EXPERIMENTAL] Upsert; update existing orders with given ids, or create new orders otherwise.
    api_response = api_instance.upsert_orders(scope, request=request)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling OrdersApi->upsert_orders: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **scope** | **str**| The scope to which the orders belong. | 
 **request** | [**OrderSetRequest**](OrderSetRequest.md)| The collection of order requests. | [optional] 

### Return type

[**OrderSet**](OrderSet.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/plain, application/json, text/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | A collection of successful and unsuccessful orders. |  -  |
**400** | The details of the input related failure |  -  |
**0** | Error response |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)
