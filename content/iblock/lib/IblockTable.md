## Класс IblockTable

Пространство имён: `Bitrix\Iblock`

 
Class IblockTable 
 
@package Bitrix\Iblock 


#### Оглавление:

* Методы:
    * Собственные методы [19]:

        * [Метод getTableName](#метод-getTableName)
        * [Метод getMap](#метод-getMap)
        * [Метод compileEntity](#метод-compileEntity)
        * [Метод compileAllEntities](#метод-compileAllEntities)
        * [Метод validateIblockTypeId](#метод-validateIblockTypeId)
        * [Метод validateLid](#метод-validateLid)
        * [Метод validateCode](#метод-validateCode)
        * [Метод validateName](#метод-validateName)
        * [Метод validateListPageUrl](#метод-validateListPageUrl)
        * [Метод validateDetailPageUrl](#метод-validateDetailPageUrl)
        * [Метод validateSectionPageUrl](#метод-validateSectionPageUrl)
        * [Метод validateCanonicalPageUrl](#метод-validateCanonicalPageUrl)
        * [Метод validateXmlId](#метод-validateXmlId)
        * [Метод validateTmpId](#метод-validateTmpId)
        * [Метод validateEditFileBefore](#метод-validateEditFileBefore)
        * [Метод validateEditFileAfter](#метод-validateEditFileAfter)
        * [Метод onAfterAdd](#метод-onAfterAdd)
        * [Метод onAfterUpdate](#метод-onAfterUpdate)
        * [Метод onAfterDelete](#метод-onAfterDelete)

    * Унаследованные методы [7]:

        * [Метод getList](/content/main/lib/orm/data/DataManager.md#метод-getList)
        * [Метод add](/content/main/lib/orm/data/DataManager.md#метод-add)
        * [Метод update](/content/main/lib/orm/data/DataManager.md#метод-update)
        * [Метод delete](/content/main/lib/orm/data/DataManager.md#метод-delete)
        * [Метод query](/content/main/lib/orm/data/DataManager.md#метод-query)
        * [Метод getByPrimary](/content/main/lib/orm/data/DataManager.md#метод-getByPrimary)
        * [Метод createObject](/content/main/lib/orm/data/DataManager.md#метод-createObject)

* Примеры:

    * [Старый стиль](#старый-стиль)
        * Получение списка элементов
        * Добавление нового элемента
        * Обновление существующего элемента
        * Удаление существующего элемента

    * [Объектный стиль](#объектный-стиль)
        * Получение списка элементов
        * Добавление нового элемента
        * Обновление существующего элемента
        * Удаление существующего элемента

![s](/asset/image/separator/30x30.png)

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
    [0] => ID                       // primary key
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
Описание методов см. класс [`Bitrix\Main\ORM\Data\DataManager`](/content/main/lib/orm/data/DataManager.md)

![s](/asset/image/separator/30x30.png)

![s](/asset/image/separator/30x30.png)

# Примеры

### Старый стиль

#### Получение списка элементов

Пример 1:

```php
// use Bitrix\Main\Loader;
// Loader::includeModule("iblock");
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
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
try
{
    //add iblock
    $itadex1result = IblockTable::add([
        'IBLOCK_TYPE_ID' => 'delivery',
        'LID'            => 's1',
        'CODE'           => 'delivery-city',
        'NAME'           => 'Доставка по городу',
        'INDEX_SECTION'  => 'Y',
        'WORKFLOW'       => 'N',
        'LIST_MODE'      => '',
        'SECTION_PROPERTY' => 'N',
        'PROPERTY_INDEX'   => 'N',
        // добавляются в IblockMessageTable
        // 'SECTIONS_NAME' => 'Разделы',
        // 'SECTION_NAME'  => 'Раздел',
        // 'ELEMENTS_NAME' => 'Элементы',
        // 'ELEMENT_NAME'  => 'Элемент',
    ]);
    $iblockId = $itadex1result->getId();
    // link to site
    $istadex1result =  IblockSiteTable::add([
        'IBLOCK_ID' => $iblockId,
        'SITE_ID'   => 's1',
    ]);
    // add message - 10 rows
    foreach (static::$messageList as $message)
    {
        IblockMessageTable::add([
            'IBLOCK_ID'      => $iblockId,
            'MESSAGE_ID'     => $message['MESSAGE_ID'],
            'MESSAGE_TEXT'   => $message['MESSAGE_TEXT'],
        ]);
    }
}
catch (\Exception $e)
{
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
$itgdex1 = IblockTable::getList([
    'filter' => ['CODE' => 'delivery-city'],
    'select' => ['ID']
]);
$itgdex1datafirst = $itgdex1->fetch();
$iblockId = intval($itgdex1datafirst['ID']);
$itudex1result = IblockTable::update($iblockId, [
    'SECTIONS_NAME' => 'ST',
]);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$connection = \Bitrix\Main\Application::getConnection();
$queryResponse = $connection->query("
    SELECT ID FROM b_iblock WHERE CODE LIKE 'delivery-city'
")->fetch();
$id = intval($queryResponse['ID']);
// unlink to site
$istadex1result =  IblockSiteTable::delete([
    'IBLOCK_ID' => $id,
    'SITE_ID'   => 's1',
]);
$itddex1result = IblockTable::delete($id);
// delete message - 10 rows
foreach (static::$messageList as $message)
{
    IblockMessageTable::delete([
        'IBLOCK_ID'      => $id,
        'MESSAGE_ID'     => $message['MESSAGE_ID'],
    ]);
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

### Объектный стиль

#### Получение списка элементов

Пример 1:

```php
// use Bitrix\Main\Loader;
// Loader::includeModule("iblock");
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
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

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
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
$itu1 = IblockTable::getByPrimary(10)->fetchObject();
$itu1result = $itu1->setCode('computers-2022')
                     ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$itd1result = IblockTable::getByPrimary(10)->fetchObject()->delete();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






