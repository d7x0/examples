## Класс IblockFieldTable

Пространство имён: `Bitrix\Iblock`

 
Class IblockFieldTable 
 
@package Bitrix\Iblock 


#### Оглавление:

* Методы:
    * Собственные методы [3]:

        * [Метод getTableName](#метод-getTableName)
        * [Метод getMap](#метод-getMap)
        * [Метод validateFieldId](#метод-validateFieldId)

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
$ptgtnex1 = IblockFieldTable::getTableName();        // "b_iblock_fields"

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
$ptgmex1keys = array_keys(IblockFieldTable::getMap());
/* Array (
    [0] => IBLOCK_ID                // primary key
    [1] => FIELD_ID                 // primary key
    [2] => IS_REQUIRED
    [3] => DEFAULT_VALUE
    [4] => IBLOCK                   // reference key, IBLOCK_ID  => Bitrix\Iblock\Iblock.ID
) */

```

![s](/asset/image/separator/30x30.png)


#### Метод **validateFieldId**

Описание: 
Returns validators for FIELD_ID field.

Сигнатура: 

```php
public static validateFieldId()
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
$ptglex1 = IblockFieldTable::getList([
    'filter' => ['IBLOCK_ID' => 2],
]);
$ptglex1result = [];
while($ptglex1row = $ptglex1->fetch())
{
    array_push($ptglex1result, $ptglex1row['FIELD_ID']);
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
try
{
    foreach (static::$fieldList as $field)
    {
        $ptaex1result = IblockFieldTable::add([
            'IBLOCK_ID'     => 4,
            'FIELD_ID'      => $field['FIELD_ID'],
            'IS_REQUIRED'   => $field['IS_REQUIRED'],
            'DEFAULT_VALUE' => $field['DEFAULT_VALUE'],
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
$ptuex1result = IblockFieldTable::update([
    'IBLOCK_ID'     => 4,
    'FIELD_ID'      => 'XML_ID',
],
[
    'IS_REQUIRED' => 'Y',
    'DEFAULT_VALUE' => md5('delivery-city'),
]);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
foreach (static::$fieldList as $field)
{
    IblockFieldTable::delete([
        'IBLOCK_ID'     => 4,
        'FIELD_ID'      => $field['FIELD_ID'],
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
$ptqex1 = IblockFieldTable::query()
         ->setFilter(['IBLOCK_ID' => 2])
         ->setSelect([  'IBLOCK_ID',
                        'FIELD_ID',
                        'IS_REQUIRED',
                        'DEFAULT_VALUE' ]);
$ptqex1result = $ptqex1->exec()->fetch();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
try
{
    foreach (static::$fieldList as $field)
    {
        $pta1 = IblockFieldTable::createObject();
        $pta1   ->setIblockId(4)
                ->setFieldId($field['FIELD_ID'])
                ->setIsRequired($field['IS_REQUIRED'])
                ->setDefaultValue($field['DEFAULT_VALUE'])
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
$ptu1 = IblockFieldTable::getByPrimary([
    'IBLOCK_ID'     => 4,
    'FIELD_ID'      => 'XML_ID',
])->fetchObject();
$ptu1result = $ptu1->setDefaultValue(md5('delivery-city'))
                     ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
foreach (static::$fieldList as $field)
{
    $ptd1 = IblockFieldTable::getByPrimary([
        'IBLOCK_ID'     => 4,
        'FIELD_ID'      => $field['FIELD_ID'],
    ])->fetchObject();
    $ptd1result = $ptd1->delete();
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






