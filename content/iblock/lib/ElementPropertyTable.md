## Класс ElementPropertyTable

Пространство имён: `Bitrix\Iblock`

 
@package    bitrix 
@subpackage iblock 


#### Оглавление:

* Методы:
    * Собственные методы [1]:

        * [Метод getMap](#метод-getMap)

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
$ttgnex11keys = array_keys(ElementPropertyTable::getMap());
/* Array
(
    [0] => ID                       // primary key
    [1] => IBLOCK_PROPERTY_ID
    [2] => IBLOCK_ELEMENT_ID
    [3] => ELEMENT                  // reference
    [4] => VALUE
    [5] => VALUE_TYPE
    [6] => VALUE_ENUM
    [7] => VALUE_NUM
    [8] => DESCRIPTION
    [9] => ENUM                     // reference
)*/
$ttgnex11 = ElementPropertyTable::getMap();
/* keys:
    primary   => ID
    reference => [
        IBLOCK_ELEMENT_ID => Bitrix\Iblock\ElementTable.ID,
        VALUE_ENUM        => Bitrix\Iblock\PropertyEnumerationTable.ID,
    ]
*/

```

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
$eptglex1 = ElementTable::getList([
    'filter' => ['IBLOCK_SECTION_ID' => 17, 'IBLOCK_ID' => $iblockId],
    'select' => ['ID', 'NAME']
]);
$eptglex1res = [];
while($eptglex1row = $eptglex1->fetch())
{
    if(is_array($eptglex1res[$eptglex1row['ID']]))
    {
        $eptglex1res[$eptglex1row['ID']] = [];
    }
        $eptglex1res[$eptglex1row['ID']]['NAME'] = $eptglex1row['NAME'];
    $eptglex1prq = ElementPropertyTable::getList([
        'filter' => ['IBLOCK_ELEMENT_ID' => $eptglex1row['ID']],
        'select' => ['IBLOCK_PROPERTY_ID', 'VALUE']
    ]);
    $eptglex1res[$eptglex1row['ID']]['PROP'] = $eptglex1prq->fetchAll();
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
try
{
    // add new element
    $eptaex1result = ElementPropertyTable::add([
        'IBLOCK_ELEMENT_ID'   => 320,
        'IBLOCK_PROPERTY_ID'  => 25,
        'VALUE'               => "64 000",
        'VALUE_TYPE'          => "text",
    ]);
    $eptaIdInsert = $eptaex1result->getId();
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
$eptglex1prq = ElementPropertyTable::getList([
    'filter' => ['IBLOCK_ELEMENT_ID' => 320, 'IBLOCK_PROPERTY_ID' => 25],
    'select' => ['ID']
]);
$eptglex1prqres = $eptglex1prq->fetch();
$prId = $eptglex1prqres['ID'];
$eptuex1result = ElementPropertyTable::update($prId, [
    'VALUE' => '132 000'
]);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$eptglex1prq = ElementPropertyTable::getList([
    'filter' => ['IBLOCK_ELEMENT_ID' => 320, 'IBLOCK_PROPERTY_ID' => 25],
    'select' => ['ID']
]);
$eptglex1prqres = $eptglex1prq->fetch();
$prId = $eptglex1prqres['ID'];
$eptuex1result = ElementPropertyTable::delete($prId);
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
    ->setFilter(['CODE' => 'delivery-city'])
    ->setSelect(['CODE', 'ID']);
$itqex1result1 = $itqex1->exec()->fetch();
$iblockId = $itqex1result1['ID'];
$etqex1 = ElementTable::query()
         ->setFilter(['IBLOCK_SECTION_ID' => 17, 'IBLOCK_ID' => $iblockId])
         ->setSelect(['ID', 'NAME']);
$etqex1result1 = $etqex1->exec();
$eptglex1res = [];
while($eptglex1row = $etqex1result1->fetch())
{
    if(is_array($eptglex1res[$eptglex1row['ID']]))
    {
        $eptglex1res[$eptglex1row['ID']] = [];
    }
    $eptglex1res[$eptglex1row['ID']]['NAME'] = $eptglex1row['NAME'];
    $eptglex1prq = ElementPropertyTable::query()
                ->setFilter(['IBLOCK_ELEMENT_ID' => $eptglex1row['ID']])
                ->setSelect(['IBLOCK_PROPERTY_ID', 'VALUE']);
    $eptglex1res[$eptglex1row['ID']]['PROP'] = $eptglex1prq->fetchAll();
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$eta1 = ElementPropertyTable::createObject();
$eta1result = $eta1 ->setIblockElementId(320)
                    ->setIblockPropertyId(25)
                    ->setValue('64 000')
                    ->setValueType('text')
                    ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
$eptglex1prq = ElementPropertyTable::query()
            ->setFilter(['IBLOCK_ELEMENT_ID' => 320, 'IBLOCK_PROPERTY_ID' => 25])
            ->setSelect(['ID']);
$eptglex1res = $eptglex1prq->fetch();
$prId = $eptglex1res['ID'];
$itu1 = ElementPropertyTable::getByPrimary($prId)->fetchObject();
$itu1result = $itu1 ->setValue('128 000')
                    ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$eptglex1prq = ElementPropertyTable::query()
            ->setFilter(['IBLOCK_ELEMENT_ID' => 320, 'IBLOCK_PROPERTY_ID' => 25])
            ->setSelect(['ID']);
$eptglex1res = $eptglex1prq->fetch();
$prId = $eptglex1res['ID'];
$itu1result = ElementPropertyTable::getByPrimary($prId)->fetchObject()->delete();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






