## Класс PropertyFeatureTable

Пространство имён: `Bitrix\Iblock`

 
Class PropertyFeatureTable 
 
@package Bitrix\Iblock 


#### Оглавление:

* Методы:
    * Собственные методы [5]:

        * [Метод getTableName](#метод-getTableName)
        * [Метод getMap](#метод-getMap)
        * [Метод validateModuleId](#метод-validateModuleId)
        * [Метод validateFeatureId](#метод-validateFeatureId)
        * [Метод deleteByProperty](#метод-deleteByProperty)

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
Returns DB table name for entity.

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
$ptgtnex1 = PropertyFeatureTable::getTableName();        // "b_iblock_property_feature"

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
$ptgmex1keys = array_keys(PropertyFeatureTable::getMap());
/* Array (
    [0] => ID               // primary key
    [1] => PROPERTY_ID
    [2] => MODULE_ID
    [3] => FEATURE_ID
    [4] => IS_ENABLED
    [5] => PROPERTY         // reference key, PROPERTY_ID => Bitrix\Iblock\Property.ID
) */

```

![s](/asset/image/separator/30x30.png)


#### Метод **validateModuleId**

Описание: 
Returns validators for MODULE_ID field.

Сигнатура: 

```php
public static validateModuleId()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validateFeatureId**

Описание: 
Returns validators for FEATURE_ID field.

Сигнатура: 

```php
public static validateFeatureId()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **deleteByProperty**

Описание: 
Delete all features for property.

Сигнатура: 

```php
public static deleteByProperty($property)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $property		Property | int | Id. |

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
$ptglex1 = PropertyFeatureTable::getList([
    'filter' => ['PROPERTY_ID' => 20],
    'select' => ['PROPERTY_ID', 'MODULE_ID', 'FEATURE_ID', 'IS_ENABLED']
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
    $ptaex1result = PropertyFeatureTable::add([
        'PROPERTY_ID'  => 64,
        'MODULE_ID'    => 'catalog',
        'FEATURE_ID'   => 'OFFER_TREE',
        'IS_ENABLED'   => 'Y',
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
$ptuex1result = PropertyFeatureTable::update(16,
[
    'IS_ENABLED' => 'N',
]);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
$ptdex1result = PropertyFeatureTable::delete(16);
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

### Объектный стиль

#### Получение списка элементов

Пример 1:

```php
// use Bitrix\Main\Loader;
// Loader::includeModule("iblock");
$ptqex1 = PropertyFeatureTable::query()
         ->setFilter(['PROPERTY_ID' => 20])
         ->setSelect(['PROPERTY_ID', 'MODULE_ID', 'FEATURE_ID', 'IS_ENABLED']);
$ptqex1result = $ptqex1->exec()->fetchAll();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Добавление нового элемента

Пример 1:

```php
$pta1 = PropertyFeatureTable::createObject();
$pta1result =  $pta1->setPropertyId(64)
                      ->setModuleId('catalog')
                      ->setFeatureId('OFFER_TREE')
                      ->setIsEnabled('N')
                      ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Обновление существующего элемента

Пример 1:

```php
$ptu1 = PropertyFeatureTable::getByPrimary(17)->fetchObject();
$ptu1result = $ptu1->setIsEnabled('Y')
                     ->save();
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)

#### Удаление существующего элемента

Пример 1:

```php
try
{
    $ptd1 = PropertyFeatureTable::getByPrimary(17)->fetchObject();
         $ptd1result = $ptd1->delete();
}
catch (\Throwable $e)
{
    //if $ptd1 == null
}
```
[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)






