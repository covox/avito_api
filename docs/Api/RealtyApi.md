# Swagger\Client\RealtyApi

All URIs are relative to *https://api.avito.ru/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getRealtyBookings**](RealtyApi.md#getrealtybookings) | **GET** /realty/v1/accounts/{user_id}/items/{item_id}/bookings | Получение списка броней по объявлению
[**postRealtyPrices**](RealtyApi.md#postrealtyprices) | **POST** /realty/v1/accounts/{user_id}/items/{item_id}/prices | Актуализация параметров для выбранных периодов
[**putBookingsInfo**](RealtyApi.md#putbookingsinfo) | **POST** /core/v1/accounts/{user_id}/items/{item_id}/bookings | Заполнение календаря занятости объекта недвижимости

# **getRealtyBookings**
> \Swagger\Client\Model\InlineResponse2007 getRealtyBookings($authorization, $user_id, $item_id, $date_start, $date_end)

Получение списка броней по объявлению

Возвращает информацию о бронированиях объекта за весь период.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\RealtyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Номер пользователя в Личном кабинете Авито
$item_id = 789; // int | Идентификатор объявления на сайте
$date_start = new \DateTime("2013-10-20"); // \DateTime | Фильтр, ограничивающий выборку по нижней границе дат
$date_end = new \DateTime("2013-10-20"); // \DateTime | Фильтр, ограничивающий выборку по верхней границе дат

try {
    $result = $apiInstance->getRealtyBookings($authorization, $user_id, $item_id, $date_start, $date_end);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RealtyApi->getRealtyBookings: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Номер пользователя в Личном кабинете Авито |
 **item_id** | **int**| Идентификатор объявления на сайте |
 **date_start** | **\DateTime**| Фильтр, ограничивающий выборку по нижней границе дат |
 **date_end** | **\DateTime**| Фильтр, ограничивающий выборку по верхней границе дат |

### Return type

[**\Swagger\Client\Model\InlineResponse2007**](../Model/InlineResponse2007.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **postRealtyPrices**
> \Swagger\Client\Model\InlineResponse2006 postRealtyPrices($body, $authorization, $user_id, $item_id)

Актуализация параметров для выбранных периодов

Обновляет параметры (цена за ночь, доплата за гостя, минимальная продолжительность брони) для каждого из переданных диапазонов дат

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\RealtyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$body = new \Swagger\Client\Model\ParamPricesRealty(); // \Swagger\Client\Model\ParamPricesRealty | 
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Номер пользователя в Личном кабинете Авито
$item_id = 789; // int | Идентификатор объявления на сайте

try {
    $result = $apiInstance->postRealtyPrices($body, $authorization, $user_id, $item_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RealtyApi->postRealtyPrices: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**\Swagger\Client\Model\ParamPricesRealty**](../Model/ParamPricesRealty.md)|  |
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Номер пользователя в Личном кабинете Авито |
 **item_id** | **int**| Идентификатор объявления на сайте |

### Return type

[**\Swagger\Client\Model\InlineResponse2006**](../Model/InlineResponse2006.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **putBookingsInfo**
> \Swagger\Client\Model\InlineResponse2006 putBookingsInfo($authorization, $user_id, $item_id, $body)

Заполнение календаря занятости объекта недвижимости

Заполнение календаря занятости объекта недвижимости (для краткосрочной аренды)

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\RealtyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Номер пользователя в Личном кабинете Авито
$item_id = 789; // int | Идентификатор объявления на сайте
$body = new \Swagger\Client\Model\PostCalendarData(); // \Swagger\Client\Model\PostCalendarData | 

try {
    $result = $apiInstance->putBookingsInfo($authorization, $user_id, $item_id, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RealtyApi->putBookingsInfo: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Номер пользователя в Личном кабинете Авито |
 **item_id** | **int**| Идентификатор объявления на сайте |
 **body** | [**\Swagger\Client\Model\PostCalendarData**](../Model/PostCalendarData.md)|  | [optional]

### Return type

[**\Swagger\Client\Model\InlineResponse2006**](../Model/InlineResponse2006.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

