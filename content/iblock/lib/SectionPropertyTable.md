## Класс SectionPropertyTable

Пространство имён: `Bitrix\Iblock`

 
Class SectionPropertyTable 
 
@package Bitrix\Iblock 


#### Оглавление:

* Методы:
    * Собственные методы [3]:

        * [Метод getTableName](#метод-getTableName)
        * [Метод getMap](#метод-getMap)
        * [Метод validateFilterHint](#метод-validateFilterHint)

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
$ptgtnex1 = SectionPropertyTable::getTableName();        // "b_iblock_section_property"

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
$ptgmex1keys = array_keys(SectionPropertyTable::getMap());
/* Array (
    [0] => IBLOCK_ID                // primary key
    [1] => SECTION_ID               // primary key
    [2] => PROPERTY_ID              // primary key
    [3] => SMART_FILTER
    [4] => DISPLAY_TYPE
    [5] => DISPLAY_EXPANDED
    [6] => FILTER_HINT
    [7] => IBLOCK                   // reference key, IBLOCK_ID   => Bitrix\Iblock\Iblock.ID
    [8] => PROPERTY                 // reference key, PROPERTY_ID => Bitrix\Iblock\Property.ID
    [9] => SECTION                  // reference key, SECTION_ID  => Bitrix\Iblock\Section.ID
) */

```
Пример 2

```php
$iblockTable = new \ReflectionClass(SectionPropertyTable::class);
$lc = $iblockTable->getConstants();
/* Array (
    [NUMBERS_WITH_SLIDER] => A
    [NUMBERS] => B
    [CHECKBOXES] => F
    [CHECKBOXES_WITH_PICTURES] => G
    [CHECKBOXES_WITH_PICTURES_AND_LABELS] => H
    [RADIO_BUTTONS] => K
    [DROPDOWN] => P
    [DROPDOWN_WITH_PICTURES_AND_LABELS] => R
    [CALENDAR] => U
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


#### Метод **validateFilterHint**

Описание: 
Returns validators for FILTER_HINT field.

Сигнатура: 

```php
public static validateFilterHint()
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
$ptglex1 = SectionPropertyTable::getList([
    'filter' => ['PROPERTY_ID' => 18],
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
    $ptaex1result = SectionPropertyTable::add([
        'IBLOCK_ID'     => 4,
        'SECTION_ID'    => 17,
        'PROPERTY_ID'   => 25,
        'SMART_FILTER'  => 'Y',
        'DISPLAY_TYPE'  => 'F',
        'DISPLAY_EXPANDED'  => 'N',
        'FILTER_HINT'       => '',
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
$ptuex1result = SectionPropertyTable::update([
    'IBLOCK_ID'     => 4,
    'SECTION_ID'    => 17,
    'PROPERTY_ID'   => 25,
],
[
    'DISPLAY_EXPANDED' => 'Y',
]);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$ptdex1result = SectionPropertyTable::delete([
    'IBLOCK_ID'     => 4,
    'SECTION_ID'    => 17,
    'PROPERTY_ID'   => 25,
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
$ptqex1 = SectionPropertyTable::query()
         ->setFilter(['PROPERTY_ID' => 18])
         ->setSelect([  'IBLOCK_ID',
                        'SECTION_ID',
                        'PROPERTY_ID',
                        'SMART_FILTER',
                        'DISPLAY_TYPE',
                        'DISPLAY_EXPANDED',
                        'FILTER_HINT' ]);
$ptqex1result = $ptqex1->exec()->fetch();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$pta1 = SectionPropertyTable::createObject();
$pta1result =  $pta1->setIblockId(4)
                      ->setSectionId(17)
                      ->setPropertyId(25)
                      ->setSmartFilter('Y')
                      ->setDisplayType('F')
                      ->setDisplayExpanded('N')
                      ->setFilterHint('N')
                      ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
$ptu1 = SectionPropertyTable::getByPrimary([
    'IBLOCK_ID'     => 4,
    'SECTION_ID'    => 17,
    'PROPERTY_ID'   => 25,
])->fetchObject();
$ptu1result = $ptu1->setFilterHint('Y')
                     ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
try
{
    $ptd1 = SectionPropertyTable::getByPrimary([
        'IBLOCK_ID'     => 4,
        'SECTION_ID'    => 17,
        'PROPERTY_ID'   => 25,
    ])->fetchObject();
         $ptd1result = $ptd1->delete();
}
catch (\Throwable $e)
{
    //if $ptd1 == null
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






