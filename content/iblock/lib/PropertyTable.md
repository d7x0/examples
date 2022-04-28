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
    [0] => ID                        // primary key
    [1] => TIMESTAMP_X
    [2] => IBLOCK_ID
    [3] => NAME
    [4] => ACTIVE                   // values: Y | N
    [5] => SORT
    [6] => CODE
    [7] => DEFAULT_VALUE
    [8] => PROPERTY_TYPE
    [9] => ROW_COUNT
    [10] => COL_COUNT
    [11] => LIST_TYPE
    [12] => MULTIPLE                // values: Y | N
    [13] => XML_ID
    [14] => FILE_TYPE
    [15] => MULTIPLE_CNT
    [16] => TMP_ID
    [17] => LINK_IBLOCK_ID
    [18] => WITH_DESCRIPTION        // values: Y | N
    [19] => SEARCHABLE              // values: Y | N
    [20] => FILTRABLE               // values: Y | N
    [21] => IS_REQUIRED             // values: Y | N
    [22] => VERSION                 // values: 1 | 2
    [23] => USER_TYPE
    [24] => USER_TYPE_SETTINGS_LIST
    [25] => USER_TYPE_SETTINGS
    [26] => HINT
    [27] => LINK_IBLOCK              // reference key
    [28] => IBLOCK                   // reference key
) */
/* keys:
    primary   => ID
    reference => [
        IBLOCK_ID      => Bitrix\Iblock\Iblock.ID,
        LINK_IBLOCK_ID => Bitrix\Iblock\Iblock.ID
    ]
*/

```
Пример 2

```php
$iblockTable = new \ReflectionClass(PropertyTable::class);
$lc = $iblockTable->getConstants();
/* Array (
# LIST_TYPE
    [CHECKBOX]          => C
    [LISTBOX]           => L
# PROPERTY_TYPE
    [TYPE_STRING]       => S    Строка
    [TYPE_NUMBER]       => N    Число
    [TYPE_FILE]         => F    Файл
    [TYPE_ELEMENT]      => E    Привязка к элементам
    [TYPE_SECTION]      => G    Привязка к разделам
    [TYPE_LIST]         => L    Список
# MULTIPLE_CNT
    [DEFAULT_MULTIPLE_CNT] => 5
# CALLBACK
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
Пример 3

```php
/*
Пользовательские свойства
-
Название            PROPERTY_TYPE       USER_TYPE       USER_TYPE_SETTINGS      DEFAULT_VALUE
HTML/текст          S                   HTML            a:1:{s:6:"height";i:200;}
                                                                                a:2:{s:4:"TEXT";s:0:"";s:4:"TYPE";s:4:"HTML";}
Дата                S                   Date
Дата/Время          S                   DateTime
Деньги              S                   Money
Привязка к Яндекс.Карте  S              map_yandex      a:0:{}
Привязка к карте Google Maps  S         map_google      a:1:{s:7:"API_KEY";s:0:"";}
Привязка к пользователю  S              UserID
Привязка к разделам с автозаполнением  G  SectionAuto   a:9:{s:4:"VIEW";s:1:"A";s:8:"SHOW_ADD";s:1:"N";s:9:"MAX_WIDTH";i:0;s:10:"MIN_HEIGHT";
                                                        i:24;s:10:"MAX_HEIGHT";i:1000;s:7:"BAN_SYM";s:2:",;";s:7:"REP_SYM";s:1:" ";
                                                        s:13:"OTHER_REP_SYM";s:0:"";s:11:"IBLOCK_MESS";s:1:"N";}
Привязка к теме форума  S               TopicID
Привязка к товарам (SKU)  E             SKU             a:9:{s:4:"VIEW";s:1:"A";s:8:"SHOW_ADD";s:1:"N";s:9:"MAX_WIDTH";i:0;s:10:"MIN_HEIGHT";
                                                        i:24;s:10:"MAX_HEIGHT";i:1000;s:7:"BAN_SYM";s:2:",;";s:7:"REP_SYM";s:1:" ";
                                                        s:13:"OTHER_REP_SYM";s:0:"";s:11:"IBLOCK_MESS";s:1:"N";}
Привязка к файлу (на сервере)  S        FileMan
Привязка к элементам в виде списка  E   EList           a:4:{s:4:"size";i:1;s:5:"width";i:0;s:5:"group";s:1:"N";s:8:"multiple";s:1:"N";}
Привязка к элементам по XML_ID  S       ElementXmlID
Привязка к элементам с автозаполнением  E  EAutocomplete    a:9:{s:4:"VIEW";s:1:"A";s:8:"SHOW_ADD";s:1:"N";s:9:"MAX_WIDTH";i:0;s:10:"MIN_HEIGHT";
                                                            i:24;s:10:"MAX_HEIGHT";i:1000;s:7:"BAN_SYM";s:2:",;";s:7:"REP_SYM";s:1:" ";
                                                            s:13:"OTHER_REP_SYM";s:0:"";s:11:"IBLOCK_MESS";s:1:"N";}
Справочник              S               directory       a:5:{s:4:"size";i:1;s:5:"width";i:0;s:5:"group";s:1:"N";s:8:"multiple";s:1:"N";s:10:"TABLE_NAME";s:0:"";}
Счетчик                 N               Sequence        a:1:{s:5:"write";s:1:"N";}
*/

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
$connection = \Bitrix\Main\Application::getConnection();
$queryResponse = $connection->query("
    SELECT ID FROM b_iblock WHERE CODE LIKE 'delivery-city'
")->fetch();
$id = intval($queryResponse['ID']);
$status = false;
try
{
    $ptaex1result = PropertyTable::add([
        'IBLOCK_ID' => $id,
        'CODE'      => 'FUEL_COUNT',
        'NAME'      => 'Расход топлива',
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
$connection = \Bitrix\Main\Application::getConnection();
$queryResponse = $connection->query("
    SELECT ID FROM b_iblock WHERE CODE LIKE 'delivery-city'
")->fetch();
$id = intval($queryResponse['ID']);
$connection = \Bitrix\Main\Application::getConnection();
$queryResponse = $connection->query("
    SELECT MAX(ID) AS ID_MAX FROM b_iblock_property WHERE IBLOCK_ID = $id
")->fetch();
$idMax = intval($queryResponse['ID_MAX']);
$ptuex1result = PropertyTable::update($idMax,
[
    'ACTIVE'        => 'Y',
    'PROPERTY_TYPE' => 'S',
    'LINK_IBLOCK_ID' => null,
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
$queryResponse = $connection->query("
    SELECT ID FROM b_iblock_property WHERE IBLOCK_ID = $id
");
while($qri = $queryResponse->fetch())
{
    $ptdex1result = PropertyTable::delete($qri['ID']);
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






