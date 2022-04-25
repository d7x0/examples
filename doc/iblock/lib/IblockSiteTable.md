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








