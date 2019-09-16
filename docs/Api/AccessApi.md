# Swagger\Client\AccessApi

All URIs are relative to *https://api.avito.ru/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getAccessToken**](AccessApi.md#getaccesstoken) | **GET** /token/ | Получение access token

# **getAccessToken**
> \Swagger\Client\Model\InlineResponse200 getAccessToken($grant_type, $client_id, $client_secret)

Получение access token

Получения временного ключа для авторизации

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AccessApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$grant_type = "grant_type_example"; // string | Тип OAuth flow. В данный момент поддерживается только client_credentials
$client_id = "client_id_example"; // string | 
$client_secret = "client_secret_example"; // string | 

try {
    $result = $apiInstance->getAccessToken($grant_type, $client_id, $client_secret);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccessApi->getAccessToken: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **grant_type** | **string**| Тип OAuth flow. В данный момент поддерживается только client_credentials |
 **client_id** | **string**|  |
 **client_secret** | **string**|  |

### Return type

[**\Swagger\Client\Model\InlineResponse200**](../Model/InlineResponse200.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

