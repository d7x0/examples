## Класс IblockSiteTable

Пространство имён: `Bitrix\Iblock`

 
Class IblockSiteTable 
 
@package Bitrix\Iblock 


#### Оглавление:

* Методы:
    * Собственные методы [3]:

        * [Метод getTableName](#метод-getTableName)
        * [Метод getMap](#метод-getMap)
        * [Метод validateSiteId](#метод-validateSiteId)

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
$itgtnex1 =  IblockSiteTable::getTableName();        // "b_iblock_site"

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
$itgnex11     =  IblockSiteTable::getMap();
$itgnex11keys = array_keys( IblockSiteTable::getMap());      // Array, count = 35, in db table b_iblock have count = 43
/* Array (
    [0] => IBLOCK_ID        // primary key
    [1] => SITE_ID          // primary key
    [2] => IBLOCK           // reference key
    [3] => SITE             // reference key
) */
/* keys:
    primary   => IBLOCK_ID, SITE_ID
    reference => [
        IBLOCK_ID => Bitrix\Iblock\Iblock.ID,
        SITE_ID => Bitrix\Main\Site.ID,
    ]
*/

```
Пример 2

```php
$IblockSiteTable = new \ReflectionClass( IblockSiteTable::class);
$lc = $IblockSiteTable->getConstants();
/* Array (
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


#### Метод **validateSiteId**

Описание: 
Returns validators for SITE_ID field.

Сигнатура: 

```php
public static validateSiteId()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

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
$istgdex1 =  IblockSiteTable::getList([
    'select' => ['IBLOCK_ID', 'SITE_ID']
]);
$istgdex1datafirst = $istgdex1->fetch();
$istgdex1data  = [];
$istgdex1count = 0;
while ($istgdex1row = $istgdex1->fetch())
{
    array_push($istgdex1data, $istgdex1row);
    $istgdex1count++;
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
try
{
    $istadex1result =  IblockSiteTable::add([
        'IBLOCK_ID' => 16,
        'SITE_ID'   => 's1',
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
$istudex1result =  IblockSiteTable::update([
    'IBLOCK_ID' => 16,
    'SITE_ID'   => 's1',
],
[
    'SITE_ID'   => 's2',
]);
// $istudex1result->getId() = null
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$istddex1result =  IblockSiteTable::delete([
    'IBLOCK_ID' => 16,
    'SITE_ID'   => 's1',
]);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

### Объектный стиль

#### Получение списка элементов

Пример 1:

```php
// use Bitrix\Main\Loader;
// Loader::includeModule("iblock");
$istqex1 =  IblockSiteTable::query()
         ->setSelect(['IBLOCK_ID', 'SITE_ID']);
$istqex1result1 = $istqex1->exec();
$istqex1result2 = $istqex1->exec();
$istqex1datafirst = $istqex1result2->fetch();
$istqex1data  = [];
$istqex1count = 0;
while ($istqex1row = $istqex1result1->fetch())
{
    array_push($istqex1data, $istqex1row);
    $istqex1count++;
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$ista1 =  IblockSiteTable::createObject();
$ista1result =  $ista1->setIblockId(8)
                      ->setSiteId('s2')
                      ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
try
{
    $istu1 =  IblockSiteTable::getByPrimary([
        'IBLOCK_ID' => 8,
        'SITE_ID'   => 's2',
    ])->fetchObject();
    $istu1result = $istu1->setSiteId('s8')
        ->save();
}
catch (\Exception $e)
{
    // Setting value for Primary `SITE_ID` in `Bitrix\Iblock\EO_IblockSite`
    // is not allowed, it is read-only field
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$istd1result =  IblockSiteTable::getByPrimary([
    'IBLOCK_ID' => 8,
    'SITE_ID'   => 's2',
])->fetchObject()->delete();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






