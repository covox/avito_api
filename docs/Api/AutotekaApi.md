# Swagger\Client\AutotekaApi

All URIs are relative to *https://api.avito.ru/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getActivePackage**](AutotekaApi.md#getactivepackage) | **GET** /autoteka/v1/packages/active_package | Метод для запроса остатка отчётов в текущем пакете пользователя
[**getPreview**](AutotekaApi.md#getpreview) | **GET** /autoteka/v1/previews/{previewId} | Запрос на получение превью по ID
[**getReport**](AutotekaApi.md#getreport) | **GET** /autoteka/v1/reports/{report_id} | Метод для получения отчета по ID
[**postPreviewByRegNumber**](AutotekaApi.md#postpreviewbyregnumber) | **POST** /autoteka/v1/request-preview-by-regnumber | Запрос на создание превью по государственному номеру
[**postPreviewByVin**](AutotekaApi.md#postpreviewbyvin) | **POST** /autoteka/v1/previews | Запрос на создание превью по VIN
[**postReport**](AutotekaApi.md#postreport) | **POST** /autoteka/v1/reports | Запрос на создание отчета по превью
[**putReport**](AutotekaApi.md#putreport) | **PUT** /autoteka/v1/reports/{report_id} | Метод для обновление отчета по его идентификатору в случае отсуствия данных

# **getActivePackage**
> \Swagger\Client\Model\GetActivePackageResponseBodyAutoteka getActivePackage($authorization)

Метод для запроса остатка отчётов в текущем пакете пользователя

Возвращает остаток отчётов в текущем пакете пользователя

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AutotekaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации

try {
    $result = $apiInstance->getActivePackage($authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutotekaApi->getActivePackage: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |

### Return type

[**\Swagger\Client\Model\GetActivePackageResponseBodyAutoteka**](../Model/GetActivePackageResponseBodyAutoteka.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getPreview**
> \Swagger\Client\Model\GetPreviewResponseBodyAutoteka getPreview($authorization, $preview_id)

Запрос на получение превью по ID

Возвращает текущий статус сбора информации превью, и краткую инфо по запрашиваемому `VIN`

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AutotekaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$preview_id = 56; // int | Идентификатор превью

try {
    $result = $apiInstance->getPreview($authorization, $preview_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutotekaApi->getPreview: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **preview_id** | **int**| Идентификатор превью |

### Return type

[**\Swagger\Client\Model\GetPreviewResponseBodyAutoteka**](../Model/GetPreviewResponseBodyAutoteka.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getReport**
> \Swagger\Client\Model\GetReportResponseBodyAutoteka getReport($authorization, $report_id)

Метод для получения отчета по ID

Получение подробного отчета по его идентификатору, полученному из [запроса на создание отчета](#operation/postReport)

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AutotekaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$report_id = 56; // int | Идентификатор отчета.

try {
    $result = $apiInstance->getReport($authorization, $report_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutotekaApi->getReport: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **report_id** | **int**| Идентификатор отчета. |

### Return type

[**\Swagger\Client\Model\GetReportResponseBodyAutoteka**](../Model/GetReportResponseBodyAutoteka.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **postPreviewByRegNumber**
> \Swagger\Client\Model\RequestPreviewResponseBodyAutoteka postPreviewByRegNumber($authorization, $body)

Запрос на создание превью по государственному номеру

Возвращает идентификатор `previewId`, по которому асинхронно с помощью [запроса на получение превью по ID](#operation/getPreview) можно получить результат

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AutotekaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$body = new \Swagger\Client\Model\RequestPreviewByRegNumberAutoteka(); // \Swagger\Client\Model\RequestPreviewByRegNumberAutoteka | 

try {
    $result = $apiInstance->postPreviewByRegNumber($authorization, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutotekaApi->postPreviewByRegNumber: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **body** | [**\Swagger\Client\Model\RequestPreviewByRegNumberAutoteka**](../Model/RequestPreviewByRegNumberAutoteka.md)|  | [optional]

### Return type

[**\Swagger\Client\Model\RequestPreviewResponseBodyAutoteka**](../Model/RequestPreviewResponseBodyAutoteka.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **postPreviewByVin**
> \Swagger\Client\Model\RequestPreviewResponseBodyAutoteka postPreviewByVin($authorization, $body)

Запрос на создание превью по VIN

Возвращает идентификатор `previewId`, по которому асинхронно с помощью [запроса на получение превью по ID](#operation/getPreview) можно получить результат

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AutotekaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$body = new \Swagger\Client\Model\RequestPreviewByVinAutoteka(); // \Swagger\Client\Model\RequestPreviewByVinAutoteka | 

try {
    $result = $apiInstance->postPreviewByVin($authorization, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutotekaApi->postPreviewByVin: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **body** | [**\Swagger\Client\Model\RequestPreviewByVinAutoteka**](../Model/RequestPreviewByVinAutoteka.md)|  | [optional]

### Return type

[**\Swagger\Client\Model\RequestPreviewResponseBodyAutoteka**](../Model/RequestPreviewResponseBodyAutoteka.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **postReport**
> \Swagger\Client\Model\CreateReportResponseBodyAutoteka postReport($authorization, $body)

Запрос на создание отчета по превью

Метод для запроса отчета по `previewId`, возвращает идентификатор отчета по которому сформированный отчет можно получить в [методе для получения отчета по его идентификатору](#operation/getReport). При запросе происходит списание доступных отчетов

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AutotekaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$body = new \Swagger\Client\Model\RequestReportByPreviewIdAutoteka(); // \Swagger\Client\Model\RequestReportByPreviewIdAutoteka | 

try {
    $result = $apiInstance->postReport($authorization, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutotekaApi->postReport: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **body** | [**\Swagger\Client\Model\RequestReportByPreviewIdAutoteka**](../Model/RequestReportByPreviewIdAutoteka.md)|  | [optional]

### Return type

[**\Swagger\Client\Model\CreateReportResponseBodyAutoteka**](../Model/CreateReportResponseBodyAutoteka.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **putReport**
> \Swagger\Client\Model\UpdateReportResponseBodyAutoteka putReport($authorization, $report_id)

Метод для обновление отчета по его идентификатору в случае отсуствия данных

Запрос на перегенерацию отчета по ID, который был получен из [запроса на создание отчета](#operation/postReport)

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\AutotekaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$report_id = 56; // int | Идентификатор отчета.

try {
    $result = $apiInstance->putReport($authorization, $report_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AutotekaApi->putReport: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **report_id** | **int**| Идентификатор отчета. |

### Return type

[**\Swagger\Client\Model\UpdateReportResponseBodyAutoteka**](../Model/UpdateReportResponseBodyAutoteka.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

