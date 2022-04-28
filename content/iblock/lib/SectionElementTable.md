## Класс SectionElementTable

Пространство имён: `Bitrix\Iblock`



#### Оглавление:

* Методы:
    * Собственные методы [2]:

        * [Метод getTableName](#метод-getTableName)
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
$ttgtnex1 = SectionElementTable::getTableName();        // "b_iblock_section_element"

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
$ttgnex11keys = array_keys(SectionElementTable::getMap());
/* Array
(
    [0] => IBLOCK_SECTION_ID                // primary key
    [1] => IBLOCK_ELEMENT_ID                // primary key
    [2] => ADDITIONAL_PROPERTY_ID
    [3] => IBLOCK_SECTION                   // reference key
    [4] => IBLOCK_ELEMENT                   // reference key
    [5] => 0                                // reference key
)*/
$ttgnex11 = SectionElementTable::getMap();
/* keys:
    primary   => ID
    reference => [
        IBLOCK_SECTION_ID => Bitrix\Iblock\Section.ID,
        IBLOCK_ELEMENT_ID => Bitrix\Iblock\Element.ID,
        IBLOCK_ELEMENT_ID => Bitrix\Iblock\ORM\CommonElement.ID,
    ]
*/

```
Пример 2

```php
$SectionElementTable = new \ReflectionClass(SectionElementTable::class);
$lc = $SectionElementTable->getConstants();
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
$itgdex1 = SectionElementTable::getList([
    'select' => ['IBLOCK_SECTION_ID']
]);
$itgdex1datafirst = $itgdex1->fetchAll();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php

try
{
    $setaex1result = SectionElementTable::add([
        'IBLOCK_SECTION_ID' => 28,
        'IBLOCK_ELEMENT_ID' => 322,
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
try
{
    // not work
    $setuex1result = SectionElementTable::update([
        'IBLOCK_SECTION_ID' => 28,
        'IBLOCK_ELEMENT_ID' => 322,
    ],
    [
        'IBLOCK_ELEMENT_ID' => 324,
    ]);
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
$setdex1result = SectionElementTable::delete([
    'IBLOCK_SECTION_ID' => 28,
    'IBLOCK_ELEMENT_ID' => 322,
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
$setqex1 = SectionElementTable::query()
         ->setFilter(['IBLOCK_SECTION_ID' => 15])
         ->setSelect(['IBLOCK_ELEMENT_ID']);
$setqex1result1 = $setqex1->exec()->fetchAll();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$seta1 = SectionElementTable::createObject();
$seta1result =$seta1->setIblockSectionId(16)
                    ->setIblockElementId(320)
                    ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
$setu1 = SectionElementTable::getByPrimary([
    'IBLOCK_SECTION_ID' => 16,
    'IBLOCK_ELEMENT_ID' => 320,
])->fetchObject();
$setu1result = $setu1->setIblockElementId(120)
                     ->save();
// Setting value for Primary `IBLOCK_ELEMENT_ID` in `Bitrix\Iblock\EO_SectionElement`
// is not allowed, it is read-only field (0)
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
try
{
    $setd1 = SectionElementTable::getByPrimary([
        'IBLOCK_SECTION_ID' => 16,
        'IBLOCK_ELEMENT_ID' => 320,
    ])->fetchObject();
    $setd1result = $setd1->delete();
}
catch (\Throwable $e)
{
    //if $setd1 == null
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






