## Класс SectionTable

Пространство имён: `Bitrix\Iblock`

 
Class SectionTable 
 
@package Bitrix\Iblock 


#### Оглавление:

* Методы:
    * Собственные методы [6]:

        * [Метод getTableName](#метод-getTableName)
        * [Метод getMap](#метод-getMap)
        * [Метод validateName](#метод-validateName)
        * [Метод validateCode](#метод-validateCode)
        * [Метод validateXmlId](#метод-validateXmlId)
        * [Метод validateTmpId](#метод-validateTmpId)

    * Унаследованные методы [7]:

        * [Метод getList](/doc/main/lib/orm/data/DataManager.md#метод-getList)
        * [Метод add](/doc/main/lib/orm/data/DataManager.md#метод-add)
        * [Метод update](/doc/main/lib/orm/data/DataManager.md#метод-update)
        * [Метод delete](/doc/main/lib/orm/data/DataManager.md#метод-delete)
        * [Метод query](/doc/main/lib/orm/data/DataManager.md#метод-query)
        * [Метод getByPrimary](/doc/main/lib/orm/data/DataManager.md#метод-getByPrimary)
        * [Метод createObject](/doc/main/lib/orm/data/DataManager.md#метод-createObject)

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
$ttgtnex1 = SectionTable::getTableName();        // "b_iblock_section"

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
$ttgnex11keys = array_keys(SectionTable::getMap());
/* Array
(
    [0] => ID                           // primary key
    [1] => TIMESTAMP_X                  // required field, format:
    [2] => MODIFIED_BY
    [3] => DATE_CREATE
    [4] => CREATED_BY
    [5] => IBLOCK_ID                    // required filed
    [6] => IBLOCK_SECTION_ID
    [7] => ACTIVE
    [8] => GLOBAL_ACTIVE
    [9] => SORT
    [10] => NAME                        // required field
    [11] => PICTURE
    [12] => LEFT_MARGIN
    [13] => RIGHT_MARGIN
    [14] => DEPTH_LEVEL
    [15] => DESCRIPTION
    [16] => DESCRIPTION_TYPE            // required field
    [17] => SEARCHABLE_CONTENT
    [18] => CODE
    [19] => XML_ID
    [20] => TMP_ID
    [21] => DETAIL_PICTURE
    [22] => SOCNET_GROUP_ID
    [23] => IBLOCK                      // reference key
    [24] => PARENT_SECTION              // reference key
    [25] => CREATED_BY_USER             // reference key
    [26] => MODIFIED_BY_USER            // reference key
)*/
$ttgnex11 = SectionTable::getMap();
/* keys:
    primary   => ID
    reference => [
        IBLOCK_ID           => Bitrix\Iblock\Iblock.ID,     - ! not IBLOCK
        IBLOCK_SECTION_ID   => Bitrix\Iblock\Section.ID,    - ! not PARENT_SECTION
        CREATED_BY  => Bitrix\Main\User.ID,                 - ! not CREATED_BY_USER
        MODIFIED_BY => Bitrix\Main\User.ID,                 - ! not MODIFIED_BY_USER
    ]
*/

```
Пример 2

```php
$SectionTable = new \ReflectionClass(SectionTable::class);
$lc = $SectionTable->getConstants();
/* Array
(
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



## Унаследованные методы
Описание методов см. класс [`Bitrix\Main\ORM\Data\DataManager`](/doc/main/lib/orm/data/DataManager.md)

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
$stglex1 = SectionTable::getList([
    'filter' => ['CODE' => 'CAO', 'IBLOCK_ID' => $itgdex1datafirst['ID']],
     'select' => ['ID']
]);
$stglex1result = $stglex1->fetch();
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
$id = intval($itgdex1datafirst['ID']);
$status = false;
try
{
    $staex1result = SectionTable::add([
        'TIMESTAMP_X' => new \Bitrix\Main\Type\DateTime(),
        'IBLOCK_ID'   => $id,
        'NAME' => "Центральный округ",
        'CODE' => "CAO",
        'DESCRIPTION_TYPE' => "text",
    ]);
    $status = true;
}
catch (\Exception $e)
{
}
```

Пример 2:

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
$iblockSectionId = intval($stglex1result['ID']);
$status = false;
try
{
    $staex1result = SectionTable::add([
        'TIMESTAMP_X' => new \Bitrix\Main\Type\DateTime(),
        'IBLOCK_ID'   => $iblockId,
        'IBLOCK_SECTION_ID' => $iblockSectionId,
        'NAME' => "Улицы А-М",
        'CODE' => "street-A-M",
        'DESCRIPTION_TYPE' => "text",
    ]);
    $status = true;
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
$stglex1 = SectionTable::getList([
    'filter' => ['CODE' => 'CAO', 'IBLOCK_ID' => $iblockId],
    'select' => ['ID']
]);
$stglex1result = $stglex1->fetch();
$iblockSectionId = intval($stglex1result['ID']);
try
{
    $stuex1result = SectionTable::update($iblockSectionId,[
        'NAME' => "Центральный округ",
        'CODE' => "CAO",
    ]);
    // Issue: MySQL Query Error!
}
catch (\Exception $e)
{
    //
}
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
$iblockSectionId = intval($stglex1result['ID']);
// Issue: MySQL Query Error!
$stdex1result = SectionTable::delete($iblockSectionId);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

### Объектный стиль

#### Получение списка элементов

Пример 1:

```php
// use Bitrix\Main\Loader;
// Loader::includeModule("iblock");
$stqex1 = SectionTable::query()
         ->setFilter(['ID' => 'catalog'])
         ->setSelect(['SECTIONS', 'EDIT_FILE_BEFORE']);
$stqex1result1 = $stqex1->exec();
$stqex1result2 = $stqex1->exec();
$stqex1datafirst = $stqex1result2->fetch();
$stqex1data  = [];
$stqex1count = 0;
while ($stqex1row = $stqex1result1->fetch())
{
    array_push($stqex1data, $stqex1row);
    $stqex1count++;
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
$sta1 = SectionTable::createObject();
$sta1result = $sta1->setTimestampX(new \Bitrix\Main\Type\DateTime())
                   ->setIblockId($iblockId)
                   ->setName('Центральный округ')
                   ->setCode('CAO')
                   ->setDescriptionType('text')
                   ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
$itqex1 = IblockTable::query()
    ->setFilter(['CODE' => 'delivery-city'])
    ->setSelect(['ID']);
$itqex1result1 = $itqex1->exec()->fetch();
$iblockId = $itqex1result1['ID'];
$stqex1 = SectionTable::query()
    ->setFilter(['CODE' => 'CAO', 'IBLOCK_ID' => $iblockId])
    ->setSelect(['ID']);
$stqex1result1 = $stqex1->exec()->fetch();
$id = $stqex1result1['ID'];
$stu1 = SectionTable::getByPrimary($id)->fetchObject();
$stu1result = $stu1->setDescription('Some CAO short description')
                     ->save();
// Issue: save second time
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$itqex1 = IblockTable::query()
    ->setFilter(['CODE' => 'delivery-city'])
    ->setSelect(['ID']);
$itqex1result1 = $itqex1->exec()->fetch();
$iblockId = $itqex1result1['ID'];
$stqex1 = SectionTable::query()
    ->setFilter(['CODE' => 'CAO', 'IBLOCK_ID' => $iblockId])
    ->setSelect(['ID']);
$stqex1result1 = $stqex1->exec()->fetch();
$id = $stqex1result1['ID'];
try
{
    $std1 = SectionTable::getByPrimary($id)->fetchObject();
    $std1result = $std1->delete();
}
catch (\Throwable $e)
{
    //if $std1 == null
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






