## Класс TypeTable

Пространство имён: `Bitrix\Iblock`

 
Class TypeTable 
 
@package Bitrix\Iblock 


#### Оглавление:

* Методы:
    * Собственные методы [6]:

        * [Метод getTableName](#метод-getTableName)
        * [Метод getMap](#метод-getMap)
        * [Метод validateId](#метод-validateId)
        * [Метод validateEditFileBefore](#метод-validateEditFileBefore)
        * [Метод validateEditFileAfter](#метод-validateEditFileAfter)
        * [Метод onDelete](#метод-onDelete)

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
$ttgtnex1 = TypeTable::getTableName();        // "b_iblock"

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
$ttgnex11keys = array_keys(TypeTable::getMap());
/* Array
(
    [0] => ID                       // primary key
    [1] => SECTIONS
    [2] => EDIT_FILE_BEFORE
    [3] => EDIT_FILE_AFTER
    [4] => IN_RSS
    [5] => SORT
    [6] => LANG_MESSAGE             // reference key
)*/
$ttgnex11     =            TypeTable::getMap();
/* keys:
    primary   => ID
    reference => [ ID => Bitrix\Iblock\TypeLanguage.IBLOCK_TYPE_ID ]
*/

```
Пример 2

```php
$TypeTable = new \ReflectionClass(TypeTable::class);
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


#### Метод **validateId**

Описание: 
Returns validators for ID field. @noinspection PhpUnused

Сигнатура: 

```php
public static validateId()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateEditFileBefore**

Описание: 
Returns validators for EDIT_FILE_BEFORE field. @noinspection PhpUnused

Сигнатура: 

```php
public static validateEditFileBefore()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateEditFileAfter**

Описание: 
Returns validators for EDIT_FILE_AFTER field. @noinspection PhpUnused

Сигнатура: 

```php
public static validateEditFileAfter()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **onDelete**

Описание: 
Deletes information blocks of given type and language messages from TypeLanguageTable

Сигнатура: 

```php
public static onDelete($event)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $event | ORM\Event | Contains information about iblock type being deleted. |

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
$ttglex1 = TypeTable::getList([
    'filter' => ['ID' => 'catalog'],
    // 'select' => ['SECTIONS']
]);
$ttglex1result = $ttglex1->fetchAll();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$status = false;
try
{
    $ttaex1result = TypeTable::add([
        'ID' => 'delivery',
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
$ttuex1result = TypeTable::update('delivery',[
    'EDIT_FILE_BEFORE' => 'iblock_exec_before.php',
]);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$ttdex1result = TypeTable::delete('delivery');
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

### Объектный стиль

#### Получение списка элементов

Пример 1:

```php
// use Bitrix\Main\Loader;
// Loader::includeModule("iblock");
$ttqex1 = TypeTable::query()
         ->setFilter(['ID' => 'catalog'])
         ->setSelect(['SECTIONS', 'EDIT_FILE_BEFORE']);
$ttqex1result1 = $ttqex1->exec();
$ttqex1result2 = $ttqex1->exec();
$ttqex1datafirst = $ttqex1result2->fetch();
$ttqex1data  = [];
$ttqex1count = 0;
while ($ttqex1row = $ttqex1result1->fetch())
{
    array_push($ttqex1data, $ttqex1row);
    $ttqex1count++;
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$tta1 = TypeTable::createObject();
$tta1result =  $tta1->setId('contragent')
                      ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
$ttu1 = TypeTable::getByPrimary('catalog')->fetchObject();
$ttu1result = $ttu1->setEditFileBefore('iblock_exec_before.php')
                     ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
try
{
    $ttd1 = TypeTable::getByPrimary('catalog')->fetchObject();
         $ttd1result = $ttd1->delete();
}
catch (\Throwable $e)
{
    //if $ttd1 == null
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






