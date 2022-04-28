## Класс IblockGroupTable

Пространство имён: `Bitrix\Iblock`

 
Class IblockGroupTable 
 
@package Bitrix\Iblock 


#### Оглавление:

* Методы:
    * Собственные методы [3]:

        * [Метод getTableName](#метод-getTableName)
        * [Метод getMap](#метод-getMap)
        * [Метод validatePermission](#метод-validatePermission)

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

![s](/asset/image/separator/30x30.png)


#### Метод **validatePermission**

Описание: 
Returns validators for PERMISSION field.

Сигнатура: 

```php
public static validatePermission()
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
$igtglex1 = IblockGroupTable::getList([
    'filter' => ['IBLOCK_ID' => 5],
    'select' => ['GROUP_ID', 'PERMISSION']
]);
$igtglex1result = $igtglex1->fetchAll();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$status = false;
try
{
    $igtaex1result = IblockGroupTable::add([
        'IBLOCK_ID' => 5,
        'GROUP_ID'  => 3,
        'PERMISSION' => 'R',
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
$igtuex1result = IblockGroupTable::update(['IBLOCK_ID' => 5,'GROUP_ID'  => 3],[
    'PERMISSION' => 'X',
]);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$igtdex1result = IblockGroupTable::delete([
    'IBLOCK_ID' => 5,
    'GROUP_ID'  => 3,
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
$igtqex1 = IblockGroupTable::query()
         ->setFilter(['IBLOCK_ID' => 5])
         ->setSelect(['GROUP_ID', 'PERMISSION']);
$igtqex1result1 = $igtqex1->exec();
$igtqex1result2 = $igtqex1->exec();
$igtqex1datafirst = $igtqex1result2->fetch();
$igtqex1data  = [];
$igtqex1count = 0;
while ($igtqex1row = $igtqex1result1->fetch())
{
    array_push($igtqex1data, $igtqex1row);
    $igtqex1count++;
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$igta1 = IblockGroupTable::createObject();
$igta1result =  $igta1->setIblockId(5)
                      ->setGroupId(3)
                      ->setPermission('S')
                      ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
$igtu1 = IblockGroupTable::getByPrimary(['IBLOCK_ID' => 5,'GROUP_ID'  => 3])->fetchObject();
$igtu1result = $igtu1->setPermission('R')
                     ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
try
{
    $igtd1 = IblockGroupTable::getByPrimary(['IBLOCK_ID' => 5,'GROUP_ID'  => 3])->fetchObject();
         $igtd1result = $igtd1->delete();
}
catch (\Throwable $e)
{
    //if $igtd1 == null
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






