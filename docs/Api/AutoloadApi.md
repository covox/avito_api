# Swagger\Client\AutoloadApi

All URIs are relative to *https://api.avito.ru/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getAutoloadItemInfo**](AutoloadApi.md#getautoloaditeminfo) | **GET** /autoload/v1/accounts/{user_id}/items/{ad_id}/ | Получение информации о выгрузке объявления
[**getLastReport**](AutoloadApi.md#getlastreport) | **GET** /autoload/v1/accounts/{user_id}/reports/last_report/ | Получение данных последнего актуального отчета
[**getReportById**](AutoloadApi.md#getreportbyid) | **GET** /autoload/v1/accounts/{user_id}/reports/{reportId}/ | Получение данных отчета по ID
[**getReports**](AutoloadApi.md#getreports) | **GET** /autoload/v1/accounts/{user_id}/reports/ | Список отчетов об автозагрузке

# **getAutoloadItemInfo**
> \Swagger\Client\Model\ItemInfoAutoload getAutoloadItemInfo($user_id, $ad_id, $authorization)

Получение информации о выгрузке объявления

Возвращает данные отчета о выгрузке объявления на сайт **avito.ru**

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AutoloadApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$user_id = 789; // int | Номер пользователя в Личном кабинете Авито
$ad_id = "ad_id_example"; // string | Идентификатор объявления из XML
$authorization = "authorization_example"; // string | Токен для авторизации

try {
    $result = $apiInstance->getAutoloadItemInfo($user_id, $ad_id, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutoloadApi->getAutoloadItemInfo: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_id** | **int**| Номер пользователя в Личном кабинете Авито |
 **ad_id** | **string**| Идентификатор объявления из XML |
 **authorization** | **string**| Токен для авторизации |

### Return type

[**\Swagger\Client\Model\ItemInfoAutoload**](../Model/ItemInfoAutoload.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getLastReport**
> \Swagger\Client\Model\InlineResponse2002 getLastReport($user_id, $authorization)

Получение данных последнего актуального отчета

Возвращает данные отчета о последнем завершенном цикле автозагрузки

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AutoloadApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$user_id = 789; // int | Номер пользователя в Личном кабинете Авито
$authorization = "authorization_example"; // string | Токен для авторизации

try {
    $result = $apiInstance->getLastReport($user_id, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutoloadApi->getLastReport: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_id** | **int**| Номер пользователя в Личном кабинете Авито |
 **authorization** | **string**| Токен для авторизации |

### Return type

[**\Swagger\Client\Model\InlineResponse2002**](../Model/InlineResponse2002.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getReportById**
> \Swagger\Client\Model\InlineResponse2002 getReportById($user_id, $report_id, $authorization)

Получение данных отчета по ID

Возвращает данные одного отчета об автозагрузке по ID отчета

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AutoloadApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$user_id = 789; // int | Номер пользователя в Личном кабинете Авито
$report_id = 56; // int | Идентификатор отчета
$authorization = "authorization_example"; // string | Токен для авторизации

try {
    $result = $apiInstance->getReportById($user_id, $report_id, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutoloadApi->getReportById: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_id** | **int**| Номер пользователя в Личном кабинете Авито |
 **report_id** | **int**| Идентификатор отчета |
 **authorization** | **string**| Токен для авторизации |

### Return type

[**\Swagger\Client\Model\InlineResponse2002**](../Model/InlineResponse2002.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getReports**
> \Swagger\Client\Model\InlineResponse2001 getReports($user_id, $authorization, $per_page, $page)

Список отчетов об автозагрузке

Отчеты отсортированы в порядке убывания даты загрузки, т.е. самый свежий отчет будет в самом начале списка

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AutoloadApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$user_id = 789; // int | Номер пользователя в Личном кабинете Авито
$authorization = "authorization_example"; // string | Токен для авторизации
$per_page = 1.2; // float | Количество ресурсов на страницу
$page = 1.2; // float | Номер страницы

try {
    $result = $apiInstance->getReports($user_id, $authorization, $per_page, $page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutoloadApi->getReports: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_id** | **int**| Номер пользователя в Личном кабинете Авито |
 **authorization** | **string**| Токен для авторизации |
 **per_page** | **float**| Количество ресурсов на страницу | [optional]
 **page** | **float**| Номер страницы | [optional]

### Return type

[**\Swagger\Client\Model\InlineResponse2001**](../Model/InlineResponse2001.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

