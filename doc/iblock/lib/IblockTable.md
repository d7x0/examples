## Класс IblockTable

Пространство имён: `Bitrix\Iblock`

Class IblockTable 

@package Bitrix\Iblock

#### Оглавление:

* Методы:
    * Собственные методы:

        1. [Метод getTableName](#метод-getTableName)
        1. [Метод getMap](#метод-getMap)
        1. [Метод compileEntity](#метод-compileEntity)
        1. [Метод compileAllEntities](#метод-compileAllEntities)
        1. [Метод validateIblockTypeId](#метод-validateIblockTypeId)
        1. [Метод validateLid](#метод-validateLid)
        1. [Метод validateCode](#метод-validateCode)
        1. [Метод validateName](#метод-validateName)
        1. [Метод validateListPageUrl](#метод-validateListPageUrl)
        1. [Метод validateDetailPageUrl](#метод-validateDetailPageUrl)
        1. [Метод validateSectionPageUrl](#метод-validateSectionPageUrl)
        1. [Метод validateCanonicalPageUrl](#метод-validateCanonicalPageUrl)
        1. [Метод validateXmlId](#метод-validateXmlId)
        1. [Метод validateTmpId](#метод-validateTmpId)
        1. [Метод validateEditFileBefore](#метод-validateEditFileBefore)
        1. [Метод validateEditFileAfter](#метод-validateEditFileAfter)
        1. [Метод onAfterAdd](#метод-onAfterAdd)
        1. [Метод onAfterUpdate](#метод-onAfterUpdate)
        1. [Метод onAfterDelete](#метод-onAfterDelete)

    * Унаследованные методы используемые в примерах:

        1. [Метод getList](#метод-getList)
        1. [Метод add](#метод-add)
        1. [Метод update](#метод-update)
        1. [Метод delete](#метод-delete)
        1. [Метод query](#метод-query)
        1. [Метод getByPrimary](#метод-getByPrimary)
        1. [Метод createObject](#метод-createObject)

* Примеры:
    * [Старый стиль](#Старый-стиль)
        * Получение списка
        * Добавление нового элемента
        * Удаление существующего элемента
        * Обновление существующего элемента

    * [Объектный стиль](#Объектный-стиль)
        * Получение списка
        * Добавление нового элемента
        * Удаление существующего элемента
        * Обновление существующего элемента


![s](/asset/image/separator/30x30.png)

# Методы
## Собственные методы


#### Метод **getTableName**

Описание: 
Returns DB table name for entity

Сигнатура: 

```php
public static getTableName()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

[к оглавлению](#оглавление)

Примеры использования: 

Пример 1

```php
// use Bitrix\Main\Loader;
// Loader::includeModule("iblock");
// CRUD операции описаны в Bitrix\Main\ORM\Data\DataManager
$itgtnex1 = IblockTable::getTableName();        // "b_iblock"

```

![s](/asset/image/separator/30x30.png)


#### Метод **getMap**

Описание: 
Returns entity map definition.

Сигнатура: 

```php
public static getMap()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

Исключения: 

| Класс |
| :--- |
| `\Bitrix\Main\SystemException` |

[к оглавлению](#оглавление)

Примеры использования: 

Пример 1

```php
$itgnex11     = IblockTable::getMap();
$itgnex11keys = array_keys(IblockTable::getMap());      // Array, count = 35, in db table b_iblock have count = 43
/* Array
(
    [0] => ID
    [1] => TIMESTAMP_X
    [2] => IBLOCK_TYPE_ID
    [3] => LID
    [4] => CODE
    [5] => 0                        // API_CODE ,string
    [6] => 1                        // REST_ON, boolean
    [7] => NAME
    [8] => ACTIVE
    [9] => SORT
    [10] => LIST_PAGE_URL
    [11] => DETAIL_PAGE_URL
    [12] => SECTION_PAGE_URL
    [13] => CANONICAL_PAGE_URL
    [14] => PICTURE
    [15] => DESCRIPTION
    [16] => DESCRIPTION_TYPE
//  [.1.] => RSS_TTL
//  [.2.] => RSS_ACTIVE
//  [.3.] => RSS_FILE_ACTIVE
//  [.4.] => RSS_FILE_LIMIT
//  [.5.] => RSS_FILE_DAYS
//  [.6.] => RSS_YANDEX_ACTIVE
    [17] => XML_ID
    [18] => TMP_ID
    [19] => INDEX_ELEMENT
    [20] => INDEX_SECTION
    [21] => WORKFLOW
    [22] => BIZPROC
    [23] => SECTION_CHOOSER
    [24] => LIST_MODE
    [25] => RIGHTS_MODE
    [26] => SECTION_PROPERTY
    [27] => PROPERTY_INDEX
    [28] => VERSION
    [29] => LAST_CONV_ELEMENT
    [30] => SOCNET_GROUP_ID
    [31] => EDIT_FILE_BEFORE
    [32] => EDIT_FILE_AFTER
//  [.7.] => SECTIONS_NAME
//  [.8.] => SECTION_NAME
//  [.9.] => ELEMENTS_NAME
// [.10.] => ELEMENT_NAME
    [33] => TYPE                    // not found in db table
    [34] => 2                       // new OneToMany('PROPERTIES', PropertyTable::class, 'IBLOCK')
)
35 - 1 - 1 = 33
43 - 33 = 10
*/
$itgnex11k0 = $itgnex11[0];         // Bitrix\Main\ORM\Fields\StringField
$itgnex11k1 = $itgnex11[1];         // Bitrix\Main\ORM\Fields\BooleanField
$itgnex11k2 = $itgnex11[2];         // Bitrix\Main\ORM\Fields\Relations\OneToMany

```
Пример 2

```php
$iblockTable = new \ReflectionClass(IblockTable::class);
$lc = $iblockTable->getConstants();
/* Array
(
// const from Bitrix\Iblock\IblockTable
    [PROPERTY_STORAGE_COMMON] => 1
    [PROPERTY_STORAGE_SEPARATE] => 2
    [RIGHTS_SIMPLE] => S
    [RIGHTS_EXTENDED] => E
    [PROPERTY_INDEX_DISABLE] => N
    [PROPERTY_INDEX_ENABLE] => Y
    [PROPERTY_INDEX_INVALID] => I
    [LIST_MODE_SEPARATE] => S
    [LIST_MODE_COMBINED] => C
    [SECTION_CHOOSER_SELECT] => L
    [SECTION_CHOOSER_DROPDOWNS] => D
    [SECTION_CHOOSER_PATH] => P
    [SELECT] => L
    [DROPDOWNS] => D
    [PATH] => P
    [SIMPLE] => S
    [EXTENDED] => E
    [SEPARATE] => S
    [COMBINED] => C
    [INVALID] => I
    [DATA_CLASS_NAMESPACE] => Bitrix\Iblock\Elements
    [DATA_CLASS_PREFIX] => Element
// const from Bitrix\Main\ORM\Data\DataManager
    [EVENT_ON_BEFORE_ADD] => OnBeforeAdd
    [EVENT_ON_ADD] => OnAdd
    [EVENT_ON_AFTER_ADD] => OnAfterAdd
    [EVENT_ON_BEFORE_UPDATE] => OnBeforeUpdate
    [EVENT_ON_UPDATE] => OnUpdate
    [EVENT_ON_AFTER_UPDATE] => OnAfterUpdate
    [EVENT_ON_BEFORE_DELETE] => OnBeforeDelete
    [EVENT_ON_DELETE] => OnDelete
    [EVENT_ON_AFTER_DELETE] => OnAfterDelete
) */

```

![s](/asset/image/separator/30x30.png)


#### Метод **compileEntity**

Сигнатура: 

```php
public static compileEntity($iblockApiCode)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $iblockApiCode | int, Iblock |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| ElementEntity, false |  |

Исключения: 

| Класс |
| :--- |
| `\Bitrix\Main\ArgumentException` |
| `\Bitrix\Main\ObjectPropertyException` |
| `\Bitrix\Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **compileAllEntities**

Сигнатура: 

```php
public static compileAllEntities()
```

Исключения: 

| Класс |
| :--- |
| `\Bitrix\Main\ArgumentException` |
| `\Bitrix\Main\ObjectPropertyException` |
| `\Bitrix\Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateIblockTypeId**

Описание: 
Returns validators for IBLOCK_TYPE_ID field.

Сигнатура: 

```php
public static validateIblockTypeId()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateLid**

Описание: 
Returns validators for LID field.

Сигнатура: 

```php
public static validateLid()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateCode**

Описание: 
Returns validators for CODE field.

Сигнатура: 

```php
public static validateCode()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateName**

Описание: 
Returns validators for NAME field.

Сигнатура: 

```php
public static validateName()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateListPageUrl**

Описание: 
Returns validators for LIST_PAGE_URL field.

Сигнатура: 

```php
public static validateListPageUrl()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateDetailPageUrl**

Описание: 
Returns validators for DETAIL_PAGE_URL field.

Сигнатура: 

```php
public static validateDetailPageUrl()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateSectionPageUrl**

Описание: 
Returns validators for SECTION_PAGE_URL field.

Сигнатура: 

```php
public static validateSectionPageUrl()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateCanonicalPageUrl**

Описание: 
Returns validators for CANONICAL_PAGE_URL field.

Сигнатура: 

```php
public static validateCanonicalPageUrl()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateXmlId**

Описание: 
Returns validators for XML_ID field.

Сигнатура: 

```php
public static validateXmlId()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateTmpId**

Описание: 
Returns validators for TMP_ID field.

Сигнатура: 

```php
public static validateTmpId()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateEditFileBefore**

Описание: 
Returns validators for EDIT_FILE_BEFORE field.

Сигнатура: 

```php
public static validateEditFileBefore()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateEditFileAfter**

Описание: 
Returns validators for EDIT_FILE_AFTER field.

Сигнатура: 

```php
public static validateEditFileAfter()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **onAfterAdd**

Описание: 
Default onAfterAdd handler. Absolutely necessary.

Сигнатура: 

```php
public static onAfterAdd($event)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $event		Current | Event | data for add. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| void |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **onAfterUpdate**

Описание: 
Default onAfterUpdate handler. Absolutely necessary.

Сигнатура: 

```php
public static onAfterUpdate($event)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $event		Current | Event | data for add. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| void |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **onAfterDelete**

Описание: 
Default onAfterDelete handler. Absolutely necessary.

Сигнатура: 

```php
public static onAfterDelete($event)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $event		Current | Event | data for add. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| void |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)



## Унаследованные методы
#### Оглавление:

* Методы:
    * Собственные методы:

        1. [Метод getList](#метод-getList)
        1. [Метод add](#метод-add)
        1. [Метод update](#метод-update)
        1. [Метод delete](#метод-delete)
        1. [Метод query](#метод-query)
        1. [Метод getByPrimary](#метод-getByPrimary)
        1. [Метод createObject](#метод-createObject)

![s](/asset/image/separator/30x30.png)


#### Метод **getList**

Описание: 
Executes the query and returns selection by parameters of the query. This function is an alias to the Query object functions 		"select" => array of fields in the SELECT part of the query, aliases are possible in the form of "alias"=>"field";<br> 		"filter" => array of filters in the WHEREHAVING part of the query in the form of "(condition)field"=>"value"; 			also could be an instance of Filter;<br> 		"group" => array of fields in the GROUP BY part of the query;<br> 		"order" => array of fields in the ORDER BY part of the query in the form of "field"=>"asc|desc";<br> 		"limit" => integer indicating maximum number of rows in the selection (like LIMIT n in MySql);<br> 		"offset" => integer indicating first row number in the selection (like LIMIT n, 100 in MySql);<br> 	"runtime" => array of entity fields created dynamically;<br> 		"cache => array of cache options:<br> 			"ttl" => integer indicating cache TTL;<br> 			"cache_joins" => boolean enabling to cache joins, false by default. @see Query::filter()

Сигнатура: 

```php
public static getList($parameters)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $parameters | array | An array of query parameters, available keys are:<br> |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| QueryResult |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\ObjectPropertyException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **add**

Описание: 
Adds row to entity table 	array( 		"fields" => array( 			"FIELD1" => "value1", 			"FIELD2" => "value2", 		"auth_context" => \Bitrix\Main\Authentication\Context object or just a plain array of fields.

Сигнатура: 

```php
public static add($data)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $data | array | An array with fields like |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| AddResult | Contains ID of inserted row |

Исключения: 

| Класс |
| :--- |
| `\Exception` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **update**

Описание: 
Updates row in entity table by primary key 	array( 		"fields" => array( 			"FIELD1" => "value1", 			"FIELD2" => "value2", 		"auth_context" => \Bitrix\Main\Authentication\Context object or just a plain array of fields.

Сигнатура: 

```php
public static update($primary, $data)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $primary | mixed |  |
| $data | array | An array with fields like |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| UpdateResult |  |

Исключения: 

| Класс |
| :--- |
| `\Exception` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **delete**

Описание: 
Deletes row in entity table by primary key

Сигнатура: 

```php
public static delete($primary)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $primary | mixed |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| DeleteResult |  |

Исключения: 

| Класс |
| :--- |
| `\Exception` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **query**

Описание: 
Creates and returns the Query object for the entity

Сигнатура: 

```php
public static query()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Query |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getByPrimary**

Описание: 
Returns selection by entity's primary key and optional parameters for getList()

Сигнатура: 

```php
public static getByPrimary($primary, $parameters)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $primary | mixed |    Primary key of the entity |
| $parameters | array | Additional parameters for getList() |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| QueryResult |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\ObjectPropertyException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **createObject**

Сигнатура: 

```php
final public static createObject($setDefaultValues)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $setDefaultValues | bool |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| null | Actual type should be annotated by orm:annotate |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

# Примеры

### Старый стиль

#### Получение списка элементов

Пример 1:

```php
$itgdex1 = IblockTable::getList([
    'filter' => ['LIST_MODE' => null],
    'select' => ['CODE', 'NAME']
]);
$itgdex1datafirst = $itgdex1->fetch();
$itgdex1data  = [];
$itgdex1count = 0;
while ($itgdex1row = $itgdex1->fetchAll())
{
    array_push($itgdex1data, $itgdex1row);
    $itgdex1count++;
}
```

#### Добавление нового элемента

Пример 1:

```php
$status = false;
try
{
    $itadex1result = IblockTable::add([
        'IBLOCK_TYPE_ID' => 'catalog',
        'LID'            => 's1',
        'CODE'           => 'electronics',
        'NAME'           => 'Эдектрониа',
    ]);
    $status = true;
}
catch (Exception $e)
{
}
```

#### Обновление существующего элемента

Пример 1:

```php
$itudex1result = IblockTable::update(2, [
    'NAME' => 'Одежда А'
]);
```

#### Удаление существующего элемента

Пример 1:

```php
$itddex1result = IblockTable::delete(4);
```

### Объектный стиль

#### Получение списка элементов

Пример 1:

```php
$itqex1 = IblockTable::query()
         ->setFilter(['LIST_MODE' => null])
         ->setSelect(['CODE', 'NAME']);
$itqex1result1 = $itqex1->exec();
$itqex1result2 = $itqex1->exec();
$itqex1datafirst = $itqex1result2->fetch();
$itqex1data  = [];
$itqex1count = 0;
while ($itqex1row = $itqex1result1->fetch())
{
    array_push($itqex1data, $itqex1row);
    $itqex1count++;
}
```

#### Добавление нового элемента

Пример 1:

```php
$ita1 = IblockTable::createObject();
$ita1result =  $ita1->setIblockTypeId('catalog')
                      ->setLid('s1')
                      ->setCode('computers')
                      ->setName('Компьютеры')
                      ->save();
```

#### Обновление существующего элемента

Пример 1:

```php
$itu1 = IblockTable::getByPrimary(10)->fetchObject();
$itu1result = $itu1->setCode('computers-2022')
                     ->save();
```

#### Удаление существующего элемента

Пример 1:

```php
$itd1result = IblockTable::getByPrimary(10)->fetchObject()->delete();
```






