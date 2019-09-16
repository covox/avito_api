# Swagger\Client\ItemApi

All URIs are relative to *https://api.avito.ru/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getItemInfo**](ItemApi.md#getiteminfo) | **GET** /core/v1/accounts/{user_id}/items/{item_id}/ | Получение информации по объявлению
[**getItemsStats**](ItemApi.md#getitemsstats) | **POST** /core/v1/accounts/{user_id}/stats/items | Получение статистики по объявлениям
[**getVasPackagePrice**](ItemApi.md#getvaspackageprice) | **POST** /core/v1/accounts/{user_id}/price/vas_packages | Получение информации о стоимости пакетов дополнительных услуг
[**getVasPrices**](ItemApi.md#getvasprices) | **POST** /core/v1/accounts/{user_id}/price/vas | Получение информации о стоимости дополнительных услуг
[**putItemVas**](ItemApi.md#putitemvas) | **PUT** /core/v1/accounts/{user_id}/items/{item_id}/vas | Применение дополнительных услуг
[**putItemVasPackage**](ItemApi.md#putitemvaspackage) | **PUT** /core/v1/accounts/{user_id}/items/{item_id}/vas_packages | Применение пакета дополнительных услуг

# **getItemInfo**
> \Swagger\Client\Model\ItemInfoAvito getItemInfo($user_id, $item_id, $authorization)

Получение информации по объявлению

Возвращает данные об объявлении - его статус, список примененных услуг, статистику просмотров

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\ItemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$user_id = 789; // int | Номер пользователя в Личном кабинете Авито
$item_id = 789; // int | Идентификатор объявления на сайте
$authorization = "authorization_example"; // string | Токен для авторизации

try {
    $result = $apiInstance->getItemInfo($user_id, $item_id, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ItemApi->getItemInfo: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_id** | **int**| Номер пользователя в Личном кабинете Авито |
 **item_id** | **int**| Идентификатор объявления на сайте |
 **authorization** | **string**| Токен для авторизации |

### Return type

[**\Swagger\Client\Model\ItemInfoAvito**](../Model/ItemInfoAvito.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getItemsStats**
> \Swagger\Client\Model\InlineResponse2003 getItemsStats($authorization, $user_id, $body)

Получение статистики по объявлениям

Получение статистики по списку идентификаторов объявлений на сайте.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\ItemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Номер пользователя в Личном кабинете Авито
$body = new \Swagger\Client\Model\ItemIdsRequestBody(); // \Swagger\Client\Model\ItemIdsRequestBody | Набор идентификаторов объявлений на сайте

try {
    $result = $apiInstance->getItemsStats($authorization, $user_id, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ItemApi->getItemsStats: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Номер пользователя в Личном кабинете Авито |
 **body** | [**\Swagger\Client\Model\ItemIdsRequestBody**](../Model/ItemIdsRequestBody.md)| Набор идентификаторов объявлений на сайте | [optional]

### Return type

[**\Swagger\Client\Model\InlineResponse2003**](../Model/InlineResponse2003.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getVasPackagePrice**
> \Swagger\Client\Model\InlineResponse2005 getVasPackagePrice($authorization, $user_id, $body)

Получение информации о стоимости пакетов дополнительных услуг

Возвращает в ответ объект со следующей структурой: - `packages` – объект, который содержит информацию о стоимости пакетов дополнительных услуг для каждого объявления. Ключами являются идентификаторы объявлений, значениями – объекты с информацией о стоимости пакетов услуг для данного объявления:   - `turbo_sale` - [пакет услуг продвижения \"Турбопродажа\"](https://support.avito.ru/articles/200026838)   - `quick_sale` - [пакет услуг продвижения \"Быстрая продажа\"](https://support.avito.ru/articles/679) - `errors` – идентификаторы объявлений, для которых информация не получена.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\ItemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Номер пользователя в Личном кабинете Авито
$body = new \Swagger\Client\Model\ItemIdsRequestBody(); // \Swagger\Client\Model\ItemIdsRequestBody | Набор идентификаторов объявлений на сайте

try {
    $result = $apiInstance->getVasPackagePrice($authorization, $user_id, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ItemApi->getVasPackagePrice: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Номер пользователя в Личном кабинете Авито |
 **body** | [**\Swagger\Client\Model\ItemIdsRequestBody**](../Model/ItemIdsRequestBody.md)| Набор идентификаторов объявлений на сайте | [optional]

### Return type

[**\Swagger\Client\Model\InlineResponse2005**](../Model/InlineResponse2005.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getVasPrices**
> \Swagger\Client\Model\InlineResponse2004 getVasPrices($authorization, $user_id, $body)

Получение информации о стоимости дополнительных услуг

Возвращает в ответ объект со следующей структурой: - `vas` – объект, который содержит информацию о стоимости дополнительных услуг для каждого объявления. Ключами являются идентификаторы объявлений, значениями – объекты с информацией о стоимости услуг для данного объявления:   - `premium` — [услуга продвижения \"Премиум\"](https://support.avito.ru/articles/200026868)   - `vip` — [услуга продвижения \"VIP\"](https://support.avito.ru/articles/200026848)   - `pushup` — [услуга продвижения \"Поднять\"](https://support.avito.ru/articles/200026828)   - `highlight` — [услуга продвижения \"Выделить\"](https://support.avito.ru/articles/200026858)   - `xl` – [услуга продвижения \"XL-объявление\"](https://support.avito.ru/articles/685) - `errors` – идентификаторы объявлений, для которых информация не получена.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\ItemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Номер пользователя в Личном кабинете Авито
$body = new \Swagger\Client\Model\ItemIdsRequestBody(); // \Swagger\Client\Model\ItemIdsRequestBody | Набор идентификаторов объявлений на сайте

try {
    $result = $apiInstance->getVasPrices($authorization, $user_id, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ItemApi->getVasPrices: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Номер пользователя в Личном кабинете Авито |
 **body** | [**\Swagger\Client\Model\ItemIdsRequestBody**](../Model/ItemIdsRequestBody.md)| Набор идентификаторов объявлений на сайте | [optional]

### Return type

[**\Swagger\Client\Model\InlineResponse2004**](../Model/InlineResponse2004.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **putItemVas**
> \Swagger\Client\Model\VasApplyAvito putItemVas($authorization, $user_id, $item_id, $body)

Применение дополнительных услуг

Применение дополнительной услуги к объявлению, в ответе возвращает данные о примененной услуге и сумму списания. [Более подробная информация по дополнительным услугам](https://support.avito.ru/sections/200009758)

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\ItemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Номер пользователя в Личном кабинете Авито
$item_id = 789; // int | Идентификатор объявления на сайте
$body = new \Swagger\Client\Model\VasIdRequestBody(); // \Swagger\Client\Model\VasIdRequestBody | 

try {
    $result = $apiInstance->putItemVas($authorization, $user_id, $item_id, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ItemApi->putItemVas: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Номер пользователя в Личном кабинете Авито |
 **item_id** | **int**| Идентификатор объявления на сайте |
 **body** | [**\Swagger\Client\Model\VasIdRequestBody**](../Model/VasIdRequestBody.md)|  | [optional]

### Return type

[**\Swagger\Client\Model\VasApplyAvito**](../Model/VasApplyAvito.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **putItemVasPackage**
> \Swagger\Client\Model\VasPackageApplyAvito putItemVasPackage($authorization, $user_id, $item_id, $body)

Применение пакета дополнительных услуг

Применение пакета дополнительных услуг к объявлению, в ответе возвращает данные о примененной услуге и сумму списания

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\ItemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Номер пользователя в Личном кабинете Авито
$item_id = 789; // int | Идентификатор объявления на сайте
$body = new \Swagger\Client\Model\PackageIdRequestBody(); // \Swagger\Client\Model\PackageIdRequestBody | 

try {
    $result = $apiInstance->putItemVasPackage($authorization, $user_id, $item_id, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ItemApi->putItemVasPackage: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Номер пользователя в Личном кабинете Авито |
 **item_id** | **int**| Идентификатор объявления на сайте |
 **body** | [**\Swagger\Client\Model\PackageIdRequestBody**](../Model/PackageIdRequestBody.md)|  | [optional]

### Return type

[**\Swagger\Client\Model\VasPackageApplyAvito**](../Model/VasPackageApplyAvito.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

