## Класс IblockMessageTable

Пространство имён: `Bitrix\Iblock`

 
Class IblockMessageTable 
 
@package Bitrix\Iblock 


#### Оглавление:

* Методы:
    * Собственные методы [4]:

        * [Метод getTableName](#метод-getTableName)
        * [Метод getMap](#метод-getMap)
        * [Метод validateMessageId](#метод-validateMessageId)
        * [Метод validateMessageText](#метод-validateMessageText)

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
$itgtnex1 =  IblockMessageTable::getTableName();        // "b_iblock_messages"

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
$itgnex11     =  IblockMessageTable::getMap();
$itgnex11keys = array_keys( IblockMessageTable::getMap());      // Array, count = 35, in db table b_iblock have count = 43
/* Array (
        [0] => IBLOCK_ID            // primary key
        [1] => MESSAGE_ID           // primary key
        [2] => MESSAGE_TEXT
        [3] => IBLOCK               // reference key
) */
/* keys:
    primary   => IBLOCK_ID, MESSAGE_ID
    reference => [
        IBLOCK_ID => Bitrix\Iblock\Iblock.ID,
    ]
*/

```
Пример 2

```php
$IblockMessageTable = new \ReflectionClass( IblockMessageTable::class);
$lc = $IblockMessageTable->getConstants();
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


#### Метод **validateMessageId**

Описание: 
Returns validators for MESSAGE_ID field.

Сигнатура: 

```php
public static validateMessageId()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateMessageText**

Описание: 
Returns validators for MESSAGE_TEXT field.

Сигнатура: 

```php
public static validateMessageText()
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
$imtgdex1 =  IblockMessageTable::getList([
    'filter' => ['IBLOCK_ID' => 4],
    'select' => ['IBLOCK_ID', 'MESSAGE_ID', 'MESSAGE_TEXT']
]);
$imtgdex1data  = [];
while ($imtgdex1row = $imtgdex1->fetch())
{
    if(!is_array($imtgdex1data[$imtgdex1row['IBLOCK_ID']]))
    {
        $imtgdex1data[$imtgdex1row['IBLOCK_ID']] = [];
    }
        $imtgdex1data[$imtgdex1row['IBLOCK_ID']][$imtgdex1row['MESSAGE_ID']] = $imtgdex1row['MESSAGE_TEXT'];
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
try
{
    foreach (static::$messageList as $message)
    {
        IblockMessageTable::add([
            'IBLOCK_ID'      => 16,
            'MESSAGE_ID'     => $message['MESSAGE_ID'],
            'MESSAGE_TEXT'   => $message['MESSAGE_TEXT'],
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
$imtudex1result =  IblockMessageTable::update([
    'IBLOCK_ID'  => 16,
    'MESSAGE_ID' => 'ELEMENTS_NAME',
],
[
    'MESSAGE_TEXT'   => '# ..',
]);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
foreach (static::$messageList as $message)
{
    IblockMessageTable::delete([
        'IBLOCK_ID'      => 16,
        'MESSAGE_ID'     => $message['MESSAGE_ID'],
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
$imtqex1 =  IblockMessageTable::query()
         ->setFilter(['IBLOCK_ID' => 4])
         ->setSelect(['IBLOCK_ID', 'MESSAGE_ID', 'MESSAGE_TEXT']);
$imtqex1result1 = $imtqex1->exec();
$imtqex1data  = [];
while ($imtqex1row = $imtqex1result1->fetch())
{
    if(!is_array($imtqex1data[$imtqex1row['IBLOCK_ID']]))
    {
        $imtqex1data[$imtqex1row['IBLOCK_ID']] = [];
    }
        $imtqex1data[$imtqex1row['IBLOCK_ID']][$imtqex1row['MESSAGE_ID']] = $imtqex1row['MESSAGE_TEXT'];
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
foreach (static::$messageList as $message)
{
    $imta1  = IblockMessageTable::createObject();
    $imta1  ->setIblockId(8)
            ->setMessageId($message['MESSAGE_ID'])
            ->setMessageText($message['MESSAGE_TEXT'])
            ->save();
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
try
{
    $imtu1 =  IblockMessageTable::getByPrimary([
        'IBLOCK_ID'  => 8,
        'MESSAGE_ID' => 'ELEMENTS_NAME',
    ])->fetchObject();
    $imtu1result = $imtu1->setMessageText('## ..')
        ->save();
}
catch (\Exception $e)
{
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
foreach (static::$messageList as $message)
{
    IblockMessageTable::getByPrimary([
        'IBLOCK_ID'      => 8,
        'MESSAGE_ID'     => $message['MESSAGE_ID'],
    ])->fetchObject()->delete();
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






