## Класс PropertyTable

Пространство имён: `Bitrix\Iblock`

Class PropertyTable 

@package Bitrix\Iblock

#### Оглавление:

* Методы:
    * Собственные методы [12]:

        * [Метод getTableName](#метод-getTableName)
        * [Метод getMap](#метод-getMap)
        * [Метод validateName](#метод-validateName)
        * [Метод validateCode](#метод-validateCode)
        * [Метод validateXmlId](#метод-validateXmlId)
        * [Метод validateFileType](#метод-validateFileType)
        * [Метод validateTmpId](#метод-validateTmpId)
        * [Метод validateUserType](#метод-validateUserType)
        * [Метод validateHint](#метод-validateHint)
        * [Метод onBeforeAdd](#метод-onBeforeAdd)
        * [Метод onBeforeUpdate](#метод-onBeforeUpdate)
        * [Метод copyOldFields](#метод-copyOldFields)

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
$ptgtnex1 = PropertyTable::getTableName();        // "b_iblock_property"

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
$ptgmex1    = PropertyTable::getMap();
$ptgmex1keys = array_keys(PropertyTable::getMap());      // Array, count = 29
/* Array
(
    [0] => ID
    [1] => TIMESTAMP_X
    [2] => IBLOCK_ID
    [3] => NAME
    [4] => ACTIVE
    [5] => SORT
    [6] => CODE
    [7] => DEFAULT_VALUE
    [8] => PROPERTY_TYPE
    [9] => ROW_COUNT
    [10] => COL_COUNT
    [11] => LIST_TYPE
    [12] => MULTIPLE
    [13] => XML_ID
    [14] => FILE_TYPE
    [15] => MULTIPLE_CNT
    [16] => TMP_ID
    [17] => LINK_IBLOCK_ID
    [18] => WITH_DESCRIPTION
    [19] => SEARCHABLE
    [20] => FILTRABLE
    [21] => IS_REQUIRED
    [22] => VERSION
    [23] => USER_TYPE
    [24] => USER_TYPE_SETTINGS_LIST
    [25] => USER_TYPE_SETTINGS
    [26] => HINT
    [27] => LINK_IBLOCK                 // not found in db
    [28] => IBLOCK                      // not found in db
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


#### Метод **validateFileType**

Описание: 
Returns validators for FILE_TYPE field.

Сигнатура: 

```php
public static validateFileType()
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


#### Метод **validateUserType**

Описание: 
Returns validators for USER_TYPE field.

Сигнатура: 

```php
public static validateUserType()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateHint**

Описание: 
Returns validators for HINT field.

Сигнатура: 

```php
public static validateHint()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **onBeforeAdd**

Описание: 
Default onBeforeAdd handler. Absolutely necessary.

Сигнатура: 

```php
public static onBeforeAdd($event)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $event		Event | ORM\Event | object. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| ORM\EventResult |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **onBeforeUpdate**

Описание: 
Default onBeforeUpdate handler. Absolutely necessary.

Сигнатура: 

```php
public static onBeforeUpdate($event)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $event		Event | ORM\Event | object. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| ORM\EventResult |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **copyOldFields**

Описание: 
Remove values from old fields (for compatibility with old api).

Сигнатура: 

```php
private static copyOldFields($result, $data)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| &$result			Modified | array | data for addupdate property. |
| $data				Current | array | data for addupdate property. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| void |  |

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
$ptglex1 = PropertyTable::getList([
    'filter' => ['IBLOCK_ID' => 3],
    'select' => ['CODE', 'NAME']
]);
$ptglex1result = $ptglex1->fetchAll();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$status = false;
try
{
    $ptaex1result = PropertyTable::add([
        'IBLOCK_ID'      => 5,
    ]);
    $status = true;
}
catch (Exception $e)
{
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
$ptuex1result = PropertyTable::update(26, [
    'NAME' => 'Цвет'
]);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$ptdex1result = PropertyTable::delete(27);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

### Объектный стиль

#### Получение списка элементов

Пример 1:

```php
// use Bitrix\Main\Loader;
// Loader::includeModule("iblock");
$ptqex1 = PropertyTable::query()
         ->setFilter(['IBLOCK_ID' => 3])
         ->setSelect(['CODE', 'NAME']);
$ptqex1result1 = $ptqex1->exec();
$ptqex1result2 = $ptqex1->exec();
$ptqex1datafirst = $ptqex1result2->fetch();
$ptqex1data  = [];
$ptqex1count = 0;
while ($ptqex1row = $ptqex1result1->fetch())
{
    array_push($ptqex1data, $ptqex1row);
    $ptqex1count++;
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$pta1 = PropertyTable::createObject();
$pta1result =  $pta1->setIblockId(5)
                      ->setName('Артикул')
                      ->setCode('ARTICUL')
                      ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
$ptu1 = PropertyTable::getByPrimary(30)->fetchObject();
$ptu1result = $ptu1->setCode('ARTICUL_2022')
                     ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
try
{
    $ptd1 = PropertyTable::getByPrimary(30)->fetchObject();
         $ptd1result = $ptd1->delete();
}
catch (\Throwable $e)
{
    //if $ptd1 == null
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






