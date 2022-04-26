## Класс PropertyEnumerationTable

Пространство имён: `Bitrix\Iblock`

 
Class PropertyEnumerationTable 
 
@package Bitrix\Iblock 


#### Оглавление:

* Методы:
    * Собственные методы [5]:

        * [Метод getTableName](#метод-getTableName)
        * [Метод getMap](#метод-getMap)
        * [Метод validateValue](#метод-validateValue)
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
        * 
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
$ptgtnex1 = PropertyEnumerationTable::getTableName();        // "b_iblock_property_enum"

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
$ptgmex1keys = array_keys(PropertyEnumerationTable::getMap());
/* Array (
    [0] => ID                       // primary key
    [1] => PROPERTY_ID              // primary key
    [2] => VALUE                    // required field
    [3] => DEF
    [4] => SORT
    [5] => XML_ID
    [6] => TMP_ID
    [7] => PROPERTY                 // reference key
)
keys:
    primary   => ID, PROPERTY_ID
    reference => [
        PROPERTY_ID => Bitrix\Iblock\Property.ID,
    ]
*/

```

![s](/asset/image/separator/30x30.png)


#### Метод **validateValue**

Описание: 
Returns validators for VALUE field.

Сигнатура: 

```php
public static validateValue()
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

#### 

Пример 1:

```php
// use Bitrix\Main\Loader;
// Loader::includeModule("iblock");
$petglex1 = PropertyEnumerationTable::getList([
    'filter' => ['PROPERTY_ID' => 23],
    'select' => ['PROPERTY_ID', 'VALUE']
]);
$petglex1result = $petglex1->fetchAll();
```

Пример 2:

```php
$petglex1 = PropertyEnumerationTable::getList([
    'filter' => [
        'ID'          => 29,
        'PROPERTY_ID' => 28
    ],
    'select' => ['ID', 'PROPERTY_ID', 'VALUE']
]);
$petglex1result = $petglex1->fetchAll();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
/*
private static $propertyEnumList = [
    [
        'NAME' => 'бензин',
        'SORT' => 100
    ],
    [
        'NAME' => 'дизель',
        'SORT' => 200
    ],
    [
        'NAME' => 'электричество',
        'SORT' => 300
    ],
    [
        'NAME' => 'гибрид',
        'SORT' => 400
    ],
    [
        'NAME' => 'водород',
        'SORT' => 500
    ],
];
*/
try
{
    $petaex1result = PropertyTable::add([
        'IBLOCK_ID' => 4,
        'CODE'      => 'FUEL_TYPE',
        'NAME'      => 'Вид топлива',
        'PROPERTY_TYPE' => 'L',
    ]);
    $prId = $petaex1result->getId();
    foreach (static::$propertyEnumList  as $propertyEnum)
    {
        $xmlId = md5('FUEL_TYPE' . $propertyEnum['NAME']);
        $valDef = $propertyEnum['NAME'] == 'бензин' ? 'Y' : 'N';
        $petaex1result = PropertyEnumerationTable::add([
            'PROPERTY_ID' => $prId,
            'SORT'   => $propertyEnum['SORT'],
            'DEF'    => $valDef,
            'VALUE'  => $propertyEnum['NAME'],
            'XML_ID' => $xmlId,
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
$petuex1result = PropertyEnumerationTable::update([
    'ID'          => 29,
    'PROPERTY_ID' => 28
],
[
    'VALUE' => 'дизель',
]);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$petglex1 = PropertyEnumerationTable::getList([
    'filter' => [
        'PROPERTY_ID' => 28
    ],
    'select' => ['ID', 'PROPERTY_ID']
]);
$petglex1result = $petglex1->fetchAll();
foreach ($petglex1result  as $propertyEnum)
{
    $petdex1result = PropertyEnumerationTable::delete([
        'ID'          => $propertyEnum['ID'],
        'PROPERTY_ID' => $propertyEnum['PROPERTY_ID']
    ]);
}
$petaex1result = PropertyTable::getList([
    'filter' => [
        'IBLOCK_ID' => 4,
        'CODE'      => 'FUEL_TYPE',
    ],
    'select' => ['ID']
]);
$propId = $petaex1result->fetch();
$petdex1result = PropertyTable::delete($propId);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

### Объектный стиль

#### Получение списка элементов

Пример 1:

```php
// use Bitrix\Main\Loader;
// Loader::includeModule("iblock");
$petglex1   = PropertyEnumerationTable::query();
$petglex1   ->setFilter(['PROPERTY_ID' => 23])
            ->setSelect(['ID', 'PROPERTY_ID', 'VALUE']);
$petglex1result = $petglex1->exec()->fetchAll();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
/*
private static $propertyEnumList = [
    [
        'NAME' => 'бензин',
        'SORT' => 100
    ],
    [
        'NAME' => 'дизель',
        'SORT' => 200
    ],
    [
        'NAME' => 'электричество',
        'SORT' => 300
    ],
    [
        'NAME' => 'гибрид',
        'SORT' => 400
    ],
    [
        'NAME' => 'водород',
        'SORT' => 500
    ],
];
*/
try
{
    $peta1result = PropertyTable::createObject();
    $peta1result->setIblockId(4)
                ->setCode('FUEL_TYPE')
                ->setName('Вид топлива')
                ->setPropertyType('L')
                ->save();
    $prId = $peta1result->getId();
    foreach (static::$propertyEnumList  as $propertyEnum)
    {
        $xmlId = md5('FUEL_TYPE' . $propertyEnum['NAME']);
        $valDef = $propertyEnum['NAME'] == 'бензин' ? 'Y' : 'N';
        $petaex1result  = PropertyEnumerationTable::createObject()
                        ->setPropertyId($prId)
                        ->setSort($propertyEnum['SORT'])
                        ->setDef($valDef)
                        ->setValue($propertyEnum['NAME'])
                        ->setXmlId($xmlId)
                        ->save();
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
$petu1 = PropertyEnumerationTable::getByPrimary([
    'ID'          => 34,
    'PROPERTY_ID' => 29
])->fetchObject();
$petu1result = $petu1->setValue('diesel')
                     ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$petglex1   = PropertyEnumerationTable::query();
$petglex1   ->setFilter(['PROPERTY_ID' => 29])
            ->setSelect(['ID', 'PROPERTY_ID']);
$petglex1result = $petglex1->exec()->fetchAll();
foreach ($petglex1result  as $propertyEnum)
{
    $petdex1qu = PropertyEnumerationTable::getByPrimary([
        'ID'          => $propertyEnum['ID'],
        'PROPERTY_ID' => $propertyEnum['PROPERTY_ID']
    ])->fetchObject();
    $petdex1result = $petdex1qu->delete();
}
$petaex1result = PropertyTable::query();
$petaex1result  ->setFilter(['IBLOCK_ID' => 4, 'CODE' => 'FUEL_TYPE',])
                ->setSelect(['ID']);
$propId = $petaex1result->exec()->fetch();
$petdex1result = PropertyTable::getByPrimary($propId)->fetchObject()->delete();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






