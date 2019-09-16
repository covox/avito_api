# ReportCollectionAutoloadInner

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** | ID отчета | 
**started_at** | [**\DateTime**](\DateTime.md) | Время создания отчета | 
**finished_at** | [**\DateTime**](\DateTime.md) | Время окончания выгрузки объявлений на сайт | 
**import_success** | **bool** | Успешно ли прошел импорт файла | [optional] 
**export_success** | **bool** | Успешно ли прошла выгрузка объявления на сайте | [optional] 
**status** | **string** | Статус обработки отчета на русском языке | 
**report_status** | **string** | Сокращенный статус обработки отчета | [optional] 
**stat** | [**\Swagger\Client\Model\ReportCollectionAutoloadInnerStat**](ReportCollectionAutoloadInnerStat.md) |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

