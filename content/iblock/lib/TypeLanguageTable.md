## Класс TypeLanguageTable

Пространство имён: `Bitrix\Iblock`

 
Class TypeLanguageTable 
 
@package Bitrix\Iblock 


#### Оглавление:

* Методы:
    * Собственные методы [8]:

        * [Метод getTableName](#метод-getTableName)
        * [Метод getMap](#метод-getMap)
        * [Метод validateIblockTypeId](#метод-validateIblockTypeId)
        * [Метод validateLanguageId](#метод-validateLanguageId)
        * [Метод validateName](#метод-validateName)
        * [Метод validateSectionsName](#метод-validateSectionsName)
        * [Метод validateElementsName](#метод-validateElementsName)
        * [Метод deleteByIblockTypeId](#метод-deleteByIblockTypeId)

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
$ttlgtnex1 = TypeLanguageTable::getTableName();        // "b_iblock_type_lang"

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
$ttlgnex11keys = array_keys(TypeLanguageTable::getMap());
/* Array
(
    [0] => IBLOCK_TYPE_ID       // primary key
    [1] => LANGUAGE_ID          // primary key, table name in db => LID
    [2] => NAME                 // required field
    [3] => SECTIONS_NAME
    [4] => ELEMENTS_NAME
    [5] => LANGUAGE             // reference key
) */
$ttlgnex11     =            TypeLanguageTable::getMap();
/* keys:
    primary   => ID, LANGUAGE_ID
    reference => [ LID => Bitrix\Main\Localization\Language.LID ]
*/

```
Пример 2

```php
$TypeTable = new \ReflectionClass(TypeLanguageTable::class);
$lc = $TypeTable->getConstants();
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


#### Метод **validateIblockTypeId**

Описание: 
Returns validators for IBLOCK_TYPE_ID field.

Сигнатура: 

```php
public static validateIblockTypeId()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateLanguageId**

Описание: 
Returns validators for LANGUAGE_ID field.

Сигнатура: 

```php
public static validateLanguageId()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

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


#### Метод **validateSectionsName**

Описание: 
Returns validators for SECTIONS_NAME field.

Сигнатура: 

```php
public static validateSectionsName()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateElementsName**

Описание: 
Returns validators for ELEMENTS_NAME field.

Сигнатура: 

```php
public static validateElementsName()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **deleteByIblockTypeId**

Описание: 
Deletes information blocks type messages. and language messages from TypeLanguageTable

Сигнатура: 

```php
public static deleteByIblockTypeId($iblockTypeId)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $iblockTypeId | string | Iblock type identifier. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| \Bitrix\Main\Entity\EventResult |  |

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
$tltglex1 = TypeLanguageTable::getList([
    'filter' => ['IBLOCK_TYPE_ID' => 'delivery'],
    // 'select' => ['NAME']
]);
$tltglex1result = $tltglex1->fetchAll();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$status = false;
try
{
    $tltaex1result1 = TypeLanguageTable::add([
        'IBLOCK_TYPE_ID' => 'delivery',
        'LANGUAGE_ID' => 'ru',
        'NAME' => 'Доставка',
        'SECTIONS_NAME' => 'Группа доставок',
        'ELEMENTS_NAME' => 'Доставка',
    ]);
    $tltaex1result2 = TypeLanguageTable::add([
        'IBLOCK_TYPE_ID' => 'delivery',
        'LANGUAGE_ID' => 'en',
        'NAME' => 'Delivery',
        'SECTIONS_NAME' => 'Delivery group',
        'ELEMENTS_NAME' => 'Delivery',
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
$tltuex1result1 = TypeLanguageTable::update(['IBLOCK_TYPE_ID' => 'delivery','LANGUAGE_ID' => 'ru'], [
    'NAME' => 'Доставка @',     // not update in adminpanel
]);
$tltuex1result1 = TypeLanguageTable::update(['IBLOCK_TYPE_ID' => 'delivery','LANGUAGE_ID' => 'en'], [
    'NAME' => 'Delivery @',     // not update in adminpanel
]);
```

Пример 2:

```php
   $tltdex1result = TypeLanguageTable::delete(['IBLOCK_TYPE_ID' => 'delivery']);
if($tltdex1result->isSuccess())
{
}
$tltaex1result1 = TypeLanguageTable::add([
    'IBLOCK_TYPE_ID' => 'delivery',
    'LANGUAGE_ID' => 'ru',
    'NAME' => 'Доставка #1',
    'SECTIONS_NAME' => 'Группа доставок #1',    // not update in adminpanel
    'ELEMENTS_NAME' => 'Доставка #1',           // but update in getList
    'SECTION_NAME' => 'Группа доставок #11',
    'ELEMENT_NAME' => 'Доставка #11',
]);
$tltaex1result2 = TypeLanguageTable::add([
    'IBLOCK_TYPE_ID' => 'delivery',
    'LANGUAGE_ID' => 'en',
    'NAME' => 'Delivery #1',
    'SECTIONS_NAME' => 'Delivery group #1',     // not update in adminpanel
    'ELEMENTS_NAME' => 'Delivery #1',           // but update in getList
]);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
   $tltdex1result = TypeLanguageTable::delete(['IBLOCK_TYPE_ID' => 'delivery']);
if($tltdex1result->isSuccess())
{
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
$tltqex1 = TypeLanguageTable::query()
         ->setFilter(['IBLOCK_TYPE_ID' => 'contragent'])
         ->setSelect([
             'IBLOCK_TYPE_ID',
             'LANGUAGE_ID',
             'NAME',
             'SECTIONS_NAME',
             'ELEMENTS_NAME',
         ]);
$tltqex1result1 = $tltqex1->exec();
$tltqex1result2 = $tltqex1->exec();
$tltqex1datafirst = $tltqex1result2->fetch();
$tltqex1data  = [];
$tltqex1count = 0;
while ($tltqex1row = $tltqex1result1->fetch())
{
    array_push($tltqex1data, $tltqex1row);
    $tltqex1count++;
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$tlta11 = TypeLanguageTable::createObject();
$tlta1result1 =  $tlta11->setIblockTypeId('contragent')
                      ->setLanguageId('ru')
                      ->setName('Контрагенты')
                      ->save();
$tlta12 = TypeLanguageTable::createObject();
$tlta1result2 =  $tlta12->setIblockTypeId('contragent')
                        ->setLanguageId('en')
                        ->setName('Contragent')
                        ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
$tltu11 = TypeLanguageTable::getByPrimary([
    'IBLOCK_TYPE_ID' => 'contragent','LANGUAGE_ID' => 'en'])->fetchObject();
$tltu1result1 = $tltu11->setSectionsName('Contragent Group #1')
                       ->setElementsName('Contragent #1')
                           ->save();    // not update in adminpanel
$tltu12 = TypeLanguageTable::getByPrimary([
    'IBLOCK_TYPE_ID' => 'contragent','LANGUAGE_ID' => 'ru'])->fetchObject();
$tltu1result2 = $tltu12->setSectionsName('Группы контрагентов #1')
                       ->setElementsName('Контрагент #1')
                            ->save();   // not update in adminpanel
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
try
{
    $tltd11 = TypeLanguageTable::getByPrimary([
        'IBLOCK_TYPE_ID' => 'contragent','LANGUAGE_ID' => 'en'])->fetchObject();
         $tltd1result1 = $tltd11->delete();
}
catch (\Throwable $e)
{
    //if $tltd1 == null
}
try
{
    $tltd12 = TypeLanguageTable::getByPrimary([
        'IBLOCK_TYPE_ID' => 'contragent','LANGUAGE_ID' => 'ru'])->fetchObject();
         $tltd1result2 = $tltd12->delete();
}
catch (\Throwable $e)
{
    //if $tltd2 == null
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






