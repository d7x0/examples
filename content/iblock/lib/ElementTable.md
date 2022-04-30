## Класс ElementTable

Пространство имён: `Bitrix\Iblock`

 
Class ElementTable 
 
Методы `add`, `update`, `delete` заблокированы, поэтому вместо класса `ElementTable` 
нужно создать новый класс сущности для таблицы `b_iblock_element` 
см. [документацию по ORM](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=4803). 
Cущность должна иметь два метода `getTableName` и `getMap` 
 
@package Bitrix\Iblock 


#### Оглавление:

* Методы:
    * Собственные методы [10]:

        * [Метод getTableName](#метод-getTableName)
        * [Метод getMap](#метод-getMap)
        * [Метод validateName](#метод-validateName)
        * [Метод validateXmlId](#метод-validateXmlId)
        * [Метод validateCode](#метод-validateCode)
        * [Метод validateTags](#метод-validateTags)
        * [Метод validateTmpId](#метод-validateTmpId)
        * [Метод add](#метод-add)
        * [Метод update](#метод-update)
        * [Метод delete](#метод-delete)

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
Returns DB table name for entity.

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
$ttgtnex1 = ElementTable::getTableName();        // "b_iblock_element"

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

[к оглавлению](#оглавление)

Примеры использования: 

Пример 1

```php
$ttgnex11keys = array_keys(ElementTable::getMap());
/* Array
(
    [0] => ID                               // primary key
    [1] => TIMESTAMP_X
    [2] => MODIFIED_BY
    [3] => DATE_CREATE
    [4] => CREATED_BY
    [5] => IBLOCK_ID                        // required filed
    [6] => IBLOCK_SECTION_ID
    [7] => ACTIVE
    [8] => ACTIVE_FROM
    [9] => ACTIVE_TO
    [10] => SORT
    [11] => NAME                            // required filed
    [12] => PREVIEW_PICTURE
    [13] => PREVIEW_TEXT
    [14] => PREVIEW_TEXT_TYPE
    [15] => DETAIL_PICTURE
    [16] => DETAIL_TEXT
    [17] => DETAIL_TEXT_TYPE
    [18] => SEARCHABLE_CONTENT
    [19] => WF_STATUS_ID
    [20] => WF_PARENT_ELEMENT_ID
    [21] => WF_NEW
    [22] => WF_LOCKED_BY
    [23] => WF_DATE_LOCK
    [24] => WF_COMMENTS
    [25] => IN_SECTIONS
    [26] => XML_ID
    [27] => CODE
    [28] => TAGS
    [29] => TMP_ID
    [30] => SHOW_COUNTER
    [31] => SHOW_COUNTER_START
    [32] => IBLOCK                              // reference key
    [33] => WF_PARENT_ELEMENT                   // reference key
    [34] => IBLOCK_SECTION                      // reference key
    [35] => MODIFIED_BY_USER                    // reference key
    [36] => CREATED_BY_USER                     // reference key
    [37] => WF_LOCKED_BY_USER                   // reference key
)*/
$ttgnex11 = ElementTable::getMap();
/* keys:
    primary   => ID
    reference => [
        IBLOCK_ID            => Bitrix\Iblock\Iblock.ID,
        WF_PARENT_ELEMENT_ID => Bitrix\Iblock\Element.ID
        IBLOCK_SECTION_ID    => Bitrix\Iblock\Section.ID
        MODIFIED_BY          => Bitrix\Main\User.ID
        CREATED_BY           => Bitrix\Main\User.ID
        WF_LOCKED_BY         => Bitrix\Main\User.ID
    ]
*/

```
Пример 2

```php
$ElementTable = new \ReflectionClass(ElementTable::class);
$lc = $ElementTable->getConstants();
/* Array
(
    [TYPE_TEXT] => text
    [TYPE_HTML] => html
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


#### Метод **validateTags**

Описание: 
Returns validators for TAGS field.

Сигнатура: 

```php
public static validateTags()
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


#### Метод **add**

Описание: 
Add iblock element.

Сигнатура: 

```php
public static add($data)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $data			Element | array | data. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| ORM\Data\AddResult |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **update**

Описание: 
Updates iblock element by primary key.

Сигнатура: 

```php
public static update($primary, $data)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $primary		Element | mixed | primary key. |
| $data			Element | array | data. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| ORM\Data\UpdateResult |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **delete**

Описание: 
Deletes iblock element by primary key.

Сигнатура: 

```php
public static delete($primary)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $primary		Element | mixed | primary key. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| ORM\Data\DeleteResult |  |

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
    'filter' => ['CODE' => 'delivery-city'],
    'select' => ['ID']
]);
$itgdex1datafirst = $itgdex1->fetch();
$iblockId = $itgdex1datafirst['ID'];
$etglex1 = ElementTable::getList([
    'filter' => ['IBLOCK_SECTION_ID' => 17, 'IBLOCK_ID' => $iblockId],
    'select' => ['ID', 'NAME']
]);
$etglex1result = $etglex1->fetch();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$itgdex1 = IblockTable::getList([
    'filter' => ['CODE' => 'delivery-city'],
    'select' => ['ID']
]);
$itgdex1datafirst = $itgdex1->fetch();
$iblockId = intval($itgdex1datafirst['ID']);
$stglex1 = SectionTable::getList([
    'filter' => ['CODE' => 'CAO', 'IBLOCK_ID' => $iblockId],
    'select' => ['ID']
]);
$stglex1result = $stglex1->fetch();
$iblockSectionId1 = intval($stglex1result['ID']);
$stglex2 = SectionTable::getList([
    'filter' => ['CODE' => 'street-A-M', 'IBLOCK_ID' => $iblockId, 'IBLOCK_SECTION_ID' => $iblockSectionId1],
    'select' => ['ID']
]);
$stglex2result = $stglex2->fetch();
$iblockSectionId = intval($stglex2result['ID']);
try
{
    // add new element
    $etaex1result = ElementTable::add([
        'TIMESTAMP_X' => new \Bitrix\Main\Type\DateTime(),
        'IBLOCK_ID'           => $iblockId,
        'IBLOCK_SECTION_ID'   => $iblockSectionId,
        'IN_SECTIONS'         => 'Y',
        'NAME'             => "Мира пр 8а",
        'DETAIL_TEXT_TYPE' => "text",
    ]);
    $etaIdInsert = $etaex1result->getId();
    // update exist element XML_ID
    $etuex1result = ElementTable::update($etaIdInsert, [
        'XML_ID' => $etaIdInsert
    ]);
    // link sections to element
    $setaex1result = SectionElementTable::add([
        'IBLOCK_SECTION_ID' => $iblockSectionId,
        'IBLOCK_ELEMENT_ID' => $etaIdInsert,
        'ADDITIONAL_PROPERTY_ID' => null
    ]);
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
$connection = \Bitrix\Main\Application::getConnection();
$queryResponse = $connection->query("
    SELECT MAX(ID) AS ID_MAX FROM b_iblock_element WHERE IBLOCK_ID = $iblockId
")->fetch();
$idMax = intval($queryResponse['ID_MAX']);
$etuex1result = ElementTable::update($idMax, [
    'NAME' => 'Мира, пр-т, 8-a'
]);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$itgdex1 = IblockTable::getList([
    'filter' => ['CODE' => 'delivery-city'],
    'select' => ['ID']
]);
$itgdex1datafirst = $itgdex1->fetch();
$iblockId = intval($itgdex1datafirst['ID']);
$stglex1 = SectionTable::getList([
    'filter' => ['CODE' => 'CAO', 'IBLOCK_ID' => $iblockId],
    'select' => ['ID']
]);
$stglex1result = $stglex1->fetch();
$iblockSectionId1 = intval($stglex1result['ID']);
$connection = \Bitrix\Main\Application::getConnection();
$queryResponse = $connection->query("
    SELECT MAX(ID) AS ID_MAX FROM b_iblock_element WHERE IBLOCK_ID = $iblockId
")->fetch();
$idMax = intval($queryResponse['ID_MAX']);
// unlink sections to element
$setaex1result = SectionElementTable::delete([
    'IBLOCK_SECTION_ID' => $iblockSectionId1,
    'IBLOCK_ELEMENT_ID' => $idMax,
]);
// delete element
$etuex1result = ElementTable::delete($idMax);
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
    ->setFilter(['CODE' => 'supplier-steel'])
    ->setSelect(['CODE', 'ID']);
$itqex1result1 = $itqex1->exec()->fetch();
$iblockId = $itqex1result1['ID'];
$etqex1 = ElementTable::query()
         ->setFilter(['IBLOCK_ID' => $iblockId])
         ->setSelect(['NAME', 'XML_ID']);
$etqex1result1 = $etqex1->exec();
$etqex1data  = [];
while ($etqex1row = $etqex1result1->fetch())
{
    array_push($etqex1data, $etqex1row);
}
```

Пример 2:

```php
// один запрос с созданием динамического поля IB
$itqex1 = ElementTable::query()
    ->registerRuntimeField('IB', [
        "data_type" => "Bitrix\Iblock\Iblock",
        'reference' => ['=this.IBLOCK_ID' => 'ref.ID'],
    ])
    ->setFilter(['IB.CODE' => 'supplier-steel'])
    ->setSelect(['ID', 'NAME', 'IBLOCK_SECTION_ID'])
    ->exec();
$etqex1data  = [];
while ($etqex1row = $itqex1->fetch())
{
    array_push($etqex1data, $etqex1row);
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$itqex1 = IblockTable::query()
    ->setFilter(['CODE' => 'delivery-city'])
    ->setSelect(['ID']);
$itqex1result1 = $itqex1->exec()->fetch();
$iblockId = $itqex1result1['ID'];
$eta1 = ElementTable::createObject();
$eta1result = $eta1 ->setTimestampX(new \Bitrix\Main\Type\DateTime())
                    ->setIblockId($iblockId)
                    ->setIblockSectionId(17)
                    ->setInSections('Y')
                    ->setName('Мира пр. 36')
                    ->setDetailTextType('text')
                    ->save();
$seta1 = SectionElementTable::createObject();
$seta1result =$seta1->setIblockSectionId(17)
                    ->setIblockElementId(322)
                    ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
$itu1 = ElementTable::getByPrimary(322)->fetchObject();
$itu1result = $itu1 ->setName('Маркса 64')
                    ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$itu1result = SectionElementTable::getByPrimary([
    'IBLOCK_SECTION_ID' => 17,
    'IBLOCK_ELEMENT_ID' => 321,
])->fetchObject()->delete();
$itu1result = ElementTable::getByPrimary(321)->fetchObject()->delete();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






