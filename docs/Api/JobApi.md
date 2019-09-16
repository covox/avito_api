# Swagger\Client\JobApi

All URIs are relative to *https://api.avito.ru/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getResume**](JobApi.md#getresume) | **GET** /job/v1/resumes/{resume_id}/ | Просмотр резюме
[**getResumeContacts**](JobApi.md#getresumecontacts) | **GET** /job/v1/resumes/{resume_id}/contacts/ | Доступ к контактным данным соискателя
[**getResumes**](JobApi.md#getresumes) | **GET** /job/v1/resumes/ | Поиск резюме

# **getResume**
> \Swagger\Client\Model\Resume getResume($authorization, $resume_id, $fields)

Просмотр резюме

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\JobApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$resume_id = 789; // int | Идентификатор резюме
$fields = "fields_example"; // string | Поля ответа (можно указать несколько значений через запятую)

try {
    $result = $apiInstance->getResume($authorization, $resume_id, $fields);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling JobApi->getResume: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **resume_id** | **int**| Идентификатор резюме |
 **fields** | **string**| Поля ответа (можно указать несколько значений через запятую) | [optional]

### Return type

[**\Swagger\Client\Model\Resume**](../Model/Resume.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getResumeContacts**
> \Swagger\Client\Model\ResumeContacts getResumeContacts($authorization, $resume_id)

Доступ к контактным данным соискателя

Для получения контактов пользователя необходимо приобрести пакет просмотров контактных данных в [личном кабинете](https://www.avito.ru/account/cv_packages).

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\JobApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$resume_id = 789; // int | Идентификатор резюме

try {
    $result = $apiInstance->getResumeContacts($authorization, $resume_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling JobApi->getResumeContacts: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **resume_id** | **int**| Идентификатор резюме |

### Return type

[**\Swagger\Client\Model\ResumeContacts**](../Model/ResumeContacts.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getResumes**
> \Swagger\Client\Model\_ getResumes($authorization, $per_page, $page, $cursor, $fields, $query, $location, $specialization, $schedule, $business_trip_readiness, $relocation_readiness, $gender, $age_min, $age_max, $education_level, $experience_min, $experience_max, $salary_min, $salary_max, $updated_than)

Поиск резюме

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\JobApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$authorization = "authorization_example"; // string | Токен для авторизации
$per_page = 1.2; // float | Количество записей на странице (положительное число больше 0 и меньше 100)
$page = 1.2; // float | Номер страницы (положительное число больше 0)
$cursor = 1.2; // float | Курсор поиска (если не указан, будет начат новый поиск и его курсор будет возвращен в ответе)
$fields = "fields_example"; // string | Поля ответа (можно указать несколько значений через запятую)
$query = "query_example"; // string | Поисковая фраза
$location = 1.2; // float | Идентификатор региона поиска (можно указать несколько значений через запятую) <br> Метод принимает идентификаторы сущностей Region и City из [справочника](http://autoload.avito.ru/format/Locations.xml).
$specialization = 1.2; // float | Идентификатор сферы деятельности (можно указать несколько значений через запятую) <br> Возможные значения: - 10166 - IT, интернет, телеком - 10167 - Медицина, фармацевтика - 10168 - Продажи - 10169 - Страхование - 10170 - Транспорт, логистика - 10171 - Образование, наука - 10172 - Строительство - 10173 - Туризм, рестораны - 10174 - Фитнес, салоны красоты - 10175 - Без опыта, студенты - 10180 - Автомобильный бизнес - 10181 - Бухгалтерия, финансы - 10182 - Высший менеджмент - 10183 - Госслужба, НКО - 10184 - ЖКХ, эксплуатация - 10185 - Искусство, развлечения - 10186 - Консультирование - 10187 - Маркетинг, реклама, PR - 10188 - Охрана, безопасность - 10189 - Управление персоналом - 10190 - Юриспруденция - 10191 - Административная работа - 10192 - Банки, инвестиции - 10193 - Производство, сырьё, с/х - 16844 - Домашний персонал
$schedule = "schedule_example"; // string | График работы (можно указать несколько значений через запятую) <br> Возможные значения: - partial-day - Неполный рабочий день - full-day - Полный рабочий день - fly-in-fly-out - Вахтовый метод - flexible - Гибкий график - shift - Сменный график - remote - Удаленная работа
$business_trip_readiness = "business_trip_readiness_example"; // string | Готовность к командировкам (можно указать несколько значений через запятую) <br> Возможные значения: - ready - Готов - never - Не готов - sometimes - Иногда
$relocation_readiness = "relocation_readiness_example"; // string | Готовность к переезду (можно указать несколько значений через запятую) <br> Возможные значения: - possible - Возможен - never - Невозможен
$gender = "gender_example"; // string | Пол (можно указать несколько значений через запятую) <br> Возможные значения: - female - Женщина - male - Мужчина
$age_min = 1.2; // float | Минимальный возраст (включительно, положительное число от 18 до 99)
$age_max = 1.2; // float | Максимальный возраст (включительно, положительное число от 18 до 99)
$education_level = "education_level_example"; // string | Уровень образования (можно указать несколько значений через запятую) <br> Возможные значения: - higher - Высшее - unfinished-higher - Неоконченное высшее - secondary - Среднее - special-secondary - Среднее специальное
$experience_min = 1.2; // float | Минимальный стаж работы (включительно, положительное число от 0 до 50)
$experience_max = 1.2; // float | Максимальный стаж работы (включительно, положительное число от 0 до 50)
$salary_min = 1.2; // float | Минимальный размер заработной платы (включительно, положительное число)
$salary_max = 1.2; // float | Максимальный размер заработной платы (включительно, положительное число)
$updated_than = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Дата последнего обновления

try {
    $result = $apiInstance->getResumes($authorization, $per_page, $page, $cursor, $fields, $query, $location, $specialization, $schedule, $business_trip_readiness, $relocation_readiness, $gender, $age_min, $age_max, $education_level, $experience_min, $experience_max, $salary_min, $salary_max, $updated_than);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling JobApi->getResumes: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **per_page** | **float**| Количество записей на странице (положительное число больше 0 и меньше 100) | [optional]
 **page** | **float**| Номер страницы (положительное число больше 0) | [optional]
 **cursor** | **float**| Курсор поиска (если не указан, будет начат новый поиск и его курсор будет возвращен в ответе) | [optional]
 **fields** | **string**| Поля ответа (можно указать несколько значений через запятую) | [optional]
 **query** | **string**| Поисковая фраза | [optional]
 **location** | **float**| Идентификатор региона поиска (можно указать несколько значений через запятую) &lt;br&gt; Метод принимает идентификаторы сущностей Region и City из [справочника](http://autoload.avito.ru/format/Locations.xml). | [optional]
 **specialization** | **float**| Идентификатор сферы деятельности (можно указать несколько значений через запятую) &lt;br&gt; Возможные значения: - 10166 - IT, интернет, телеком - 10167 - Медицина, фармацевтика - 10168 - Продажи - 10169 - Страхование - 10170 - Транспорт, логистика - 10171 - Образование, наука - 10172 - Строительство - 10173 - Туризм, рестораны - 10174 - Фитнес, салоны красоты - 10175 - Без опыта, студенты - 10180 - Автомобильный бизнес - 10181 - Бухгалтерия, финансы - 10182 - Высший менеджмент - 10183 - Госслужба, НКО - 10184 - ЖКХ, эксплуатация - 10185 - Искусство, развлечения - 10186 - Консультирование - 10187 - Маркетинг, реклама, PR - 10188 - Охрана, безопасность - 10189 - Управление персоналом - 10190 - Юриспруденция - 10191 - Административная работа - 10192 - Банки, инвестиции - 10193 - Производство, сырьё, с/х - 16844 - Домашний персонал | [optional]
 **schedule** | **string**| График работы (можно указать несколько значений через запятую) &lt;br&gt; Возможные значения: - partial-day - Неполный рабочий день - full-day - Полный рабочий день - fly-in-fly-out - Вахтовый метод - flexible - Гибкий график - shift - Сменный график - remote - Удаленная работа | [optional]
 **business_trip_readiness** | **string**| Готовность к командировкам (можно указать несколько значений через запятую) &lt;br&gt; Возможные значения: - ready - Готов - never - Не готов - sometimes - Иногда | [optional]
 **relocation_readiness** | **string**| Готовность к переезду (можно указать несколько значений через запятую) &lt;br&gt; Возможные значения: - possible - Возможен - never - Невозможен | [optional]
 **gender** | **string**| Пол (можно указать несколько значений через запятую) &lt;br&gt; Возможные значения: - female - Женщина - male - Мужчина | [optional]
 **age_min** | **float**| Минимальный возраст (включительно, положительное число от 18 до 99) | [optional]
 **age_max** | **float**| Максимальный возраст (включительно, положительное число от 18 до 99) | [optional]
 **education_level** | **string**| Уровень образования (можно указать несколько значений через запятую) &lt;br&gt; Возможные значения: - higher - Высшее - unfinished-higher - Неоконченное высшее - secondary - Среднее - special-secondary - Среднее специальное | [optional]
 **experience_min** | **float**| Минимальный стаж работы (включительно, положительное число от 0 до 50) | [optional]
 **experience_max** | **float**| Максимальный стаж работы (включительно, положительное число от 0 до 50) | [optional]
 **salary_min** | **float**| Минимальный размер заработной платы (включительно, положительное число) | [optional]
 **salary_max** | **float**| Максимальный размер заработной платы (включительно, положительное число) | [optional]
 **updated_than** | **\DateTime**| Дата последнего обновления | [optional]

### Return type

[**\Swagger\Client\Model\_**](../Model/_.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

