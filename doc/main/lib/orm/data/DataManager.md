## Класс DataManager

Пространство имён: `Bitrix\Main\ORM\Data`

Base entity data manager

#### Оглавление:

* Методы:
    * Собственные методы:

        1. [Метод getEntity](#метод-getEntity)
        2. [Метод getTableName](#метод-getTableName)
        3. [Метод getConnectionName](#метод-getConnectionName)
        4. [Метод getTitle](#метод-getTitle)
        5. [Метод getObjectClass](#метод-getObjectClass)
        6. [Метод getObjectClassName](#метод-getObjectClassName)
        7. [Метод getCollectionClass](#метод-getCollectionClass)
        8. [Метод getCollectionClassName](#метод-getCollectionClassName)
        9. [Метод getObjectParentClass](#метод-getObjectParentClass)
        10. [Метод getCollectionParentClass](#метод-getCollectionParentClass)
        11. [Метод getQueryClass](#метод-getQueryClass)
        12. [Метод getEntityClass](#метод-getEntityClass)
        13. [Метод createObject](#метод-createObject)
        14. [Метод createCollection](#метод-createCollection)
        15. [Метод wakeUpObject](#метод-wakeUpObject)
        16. [Метод wakeUpCollection](#метод-wakeUpCollection)
        17. [Метод getMap](#метод-getMap)
        18. [Метод setDefaultScope](#метод-setDefaultScope)
        19. [Метод postInitialize](#метод-postInitialize)
        20. [Метод getByPrimary](#метод-getByPrimary)
        21. [Метод getById](#метод-getById)
        22. [Метод getRowById](#метод-getRowById)
        23. [Метод getRow](#метод-getRow)
        24. [Метод getList](#метод-getList)
        25. [Метод getCount](#метод-getCount)
        26. [Метод query](#метод-query)
        27. [Метод replaceFieldName](#метод-replaceFieldName)
        28. [Метод normalizePrimary](#метод-normalizePrimary)
        29. [Метод validatePrimary](#метод-validatePrimary)
        30. [Метод checkFields](#метод-checkFields)
        31. [Метод convertArrayToObject](#метод-convertArrayToObject)
        32. [Метод checkUfFields](#метод-checkUfFields)
        33. [Метод add](#метод-add)
        34. [Метод addMulti](#метод-addMulti)
        35. [Метод update](#метод-update)
        36. [Метод updateMulti](#метод-updateMulti)
        37. [Метод delete](#метод-delete)
        38. [Метод callOnBeforeAddEvent](#метод-callOnBeforeAddEvent)
        39. [Метод callOnAddEvent](#метод-callOnAddEvent)
        40. [Метод callOnAfterAddEvent](#метод-callOnAfterAddEvent)
        41. [Метод callOnBeforeUpdateEvent](#метод-callOnBeforeUpdateEvent)
        42. [Метод callOnUpdateEvent](#метод-callOnUpdateEvent)
        43. [Метод callOnAfterUpdateEvent](#метод-callOnAfterUpdateEvent)
        44. [Метод callOnBeforeDeleteEvent](#метод-callOnBeforeDeleteEvent)
        45. [Метод callOnDeleteEvent](#метод-callOnDeleteEvent)
        46. [Метод callOnAfterDeleteEvent](#метод-callOnAfterDeleteEvent)
        47. [Метод enableCrypto](#метод-enableCrypto)
        48. [Метод cryptoEnabled](#метод-cryptoEnabled)

![s](/asset/image/separator/30x30.png)

# Методы
## Собственные методы


#### Метод **getEntity**

Описание: 
Returns entity object

Сигнатура: 

```php
public static getEntity()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Entity |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


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


#### Метод **getConnectionName**

Описание: 
Returns connection name for entity

Сигнатура: 

```php
public static getConnectionName()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getTitle**

Сигнатура: 

```php
public static getTitle()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getObjectClass**

Описание: 
Returns class of Object for current entity.

Сигнатура: 

```php
public static getObjectClass()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string, EntityObject |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getObjectClassName**

Описание: 
Returns class name (without namespace) of Object for current entity.

Сигнатура: 

```php
final public static getObjectClassName()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getCollectionClass**

Описание: 
Returns class of Object collection for current entity.

Сигнатура: 

```php
public static getCollectionClass()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string, Collection |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getCollectionClassName**

Описание: 
Returns class name (without namespace) of Object collection for current entity.

Сигнатура: 

```php
final public static getCollectionClassName()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getObjectParentClass**

Сигнатура: 

```php
public static getObjectParentClass()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| EntityObject, string |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getCollectionParentClass**

Сигнатура: 

```php
public static getCollectionParentClass()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Collection, string |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getQueryClass**

Сигнатура: 

```php
public static getQueryClass()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Query, string |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getEntityClass**

Сигнатура: 

```php
public static getEntityClass()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Entity, string |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **createObject**

Сигнатура: 

```php
final public static createObject($setDefaultValues)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $setDefaultValues | bool |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| null | Actual type should be annotated by orm:annotate |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **createCollection**

Сигнатура: 

```php
final public static createCollection()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| null | Actual type should be annotated by orm:annotate |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **wakeUpObject**

Описание: 
@see EntityObject::wakeUp()

Сигнатура: 

```php
final public static wakeUpObject($row)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $row |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| null | Actual type should be annotated by orm:annotate |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **wakeUpCollection**

Описание: 
@see Collection::wakeUp()

Сигнатура: 

```php
final public static wakeUpCollection($rows)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $rows |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| null | Actual type should be annotated by orm:annotate |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getMap**

Описание: 
Returns entity map definition. To get initialized fields @see \Bitrix\Main\ORM\Entity::getFields() and \Bitrix\Main\ORM\Entity::getField()

Сигнатура: 

```php
public static getMap()
```

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **setDefaultScope**

Сигнатура: 

```php
public static setDefaultScope($query)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $query | Query |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Query |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **postInitialize**

Сигнатура: 

```php
public static postInitialize($entity)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $entity | Entity |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| null |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getByPrimary**

Описание: 
Returns selection by entity's primary key and optional parameters for getList()

Сигнатура: 

```php
public static getByPrimary($primary, $parameters)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $primary | mixed |    Primary key of the entity |
| $parameters | array | Additional parameters for getList() |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| QueryResult |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\ObjectPropertyException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getById**

Описание: 
Returns selection by entity's primary key

Сигнатура: 

```php
public static getById($id)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $id | mixed | Primary key of the entity |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| QueryResult |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\ObjectPropertyException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getRowById**

Описание: 
Returns one row (or null) by entity's primary key

Сигнатура: 

```php
public static getRowById($id)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $id | mixed | Primary key of the entity |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array, null |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\ObjectPropertyException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getRow**

Описание: 
Returns one row (or null) by parameters for getList()

Сигнатура: 

```php
public static getRow($parameters)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $parameters | array | Primary key of the entity |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array, null |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\ObjectPropertyException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getList**

Описание: 
Executes the query and returns selection by parameters of the query. This function is an alias to the Query object functions 		"select" => array of fields in the SELECT part of the query, aliases are possible in the form of "alias"=>"field";<br> 		"filter" => array of filters in the WHEREHAVING part of the query in the form of "(condition)field"=>"value"; 			also could be an instance of Filter;<br> 		"group" => array of fields in the GROUP BY part of the query;<br> 		"order" => array of fields in the ORDER BY part of the query in the form of "field"=>"asc|desc";<br> 		"limit" => integer indicating maximum number of rows in the selection (like LIMIT n in MySql);<br> 		"offset" => integer indicating first row number in the selection (like LIMIT n, 100 in MySql);<br> 	"runtime" => array of entity fields created dynamically;<br> 		"cache => array of cache options:<br> 			"ttl" => integer indicating cache TTL;<br> 			"cache_joins" => boolean enabling to cache joins, false by default. @see Query::filter()

Сигнатура: 

```php
public static getList($parameters)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $parameters | array | An array of query parameters, available keys are:<br> |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| QueryResult |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\ObjectPropertyException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getCount**

Описание: 
Performs COUNT query on entity and returns the result. 		"ttl" => integer indicating cache TTL

Сигнатура: 

```php
public static getCount($filter, $cache)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $filter | array, Filter |  |
| $cache | array | An array of cache options |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| int |  |

Исключения: 

| Класс |
| :--- |
| `Main\ObjectPropertyException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **query**

Описание: 
Creates and returns the Query object for the entity

Сигнатура: 

```php
public static query()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Query |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **replaceFieldName**

Сигнатура: 

```php
protected static replaceFieldName($data)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $data | array |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **normalizePrimary**

Сигнатура: 

```php
protected static normalizePrimary($primary, $data)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  |  |     $primary |
| $data | array |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **validatePrimary**

Сигнатура: 

```php
protected static validatePrimary($primary)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $primary |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **checkFields**

Описание: 
Checks the data fields before saving to DB. Result stores in the $result object

Сигнатура: 

```php
public static checkFields($result, $primary, $data)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $result | Result |  |
|  | array | $data |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **convertArrayToObject**

Сигнатура: 

```php
protected static convertArrayToObject($fields, $setDefaultValues, $primary)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $fields | array |  |
|  | bool | $setDefaultValues |
| $primary | array |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| EntityObject |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **checkUfFields**

Сигнатура: 

```php
protected static checkUfFields($object, $ufdata, $result)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  |  |                            $ufdata |
| $result | \Bitrix\Main\ORM\Data\Result |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **add**

Описание: 
Adds row to entity table 	array( 		"fields" => array( 			"FIELD1" => "value1", 			"FIELD2" => "value2", 		"auth_context" => \Bitrix\Main\Authentication\Context object or just a plain array of fields.

Сигнатура: 

```php
public static add($data)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $data | array | An array with fields like |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| AddResult | Contains ID of inserted row |

Исключения: 

| Класс |
| :--- |
| `\Exception` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **addMulti**

Сигнатура: 

```php
public static addMulti($rows, $ignoreEvents)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  |  |    $rows |
| $ignoreEvents | bool |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| AddResult |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **update**

Описание: 
Updates row in entity table by primary key 	array( 		"fields" => array( 			"FIELD1" => "value1", 			"FIELD2" => "value2", 		"auth_context" => \Bitrix\Main\Authentication\Context object or just a plain array of fields.

Сигнатура: 

```php
public static update($primary, $data)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $primary | mixed |  |
| $data | array | An array with fields like |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| UpdateResult |  |

Исключения: 

| Класс |
| :--- |
| `\Exception` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **updateMulti**

Сигнатура: 

```php
public static updateMulti($primaries, $data, $ignoreEvents)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $primaries | array |  |
| $data | array |  |
|  | bool | $ignoreEvents |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| UpdateResult |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **delete**

Описание: 
Deletes row in entity table by primary key

Сигнатура: 

```php
public static delete($primary)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $primary | mixed |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| DeleteResult |  |

Исключения: 

| Класс |
| :--- |
| `\Exception` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **callOnBeforeAddEvent**

Сигнатура: 

```php
protected static callOnBeforeAddEvent($object, $fields, $result)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $object | EntityObject |  |
|  |  |            $result |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **callOnAddEvent**

Сигнатура: 

```php
protected static callOnAddEvent($object, $fields, $ufdata)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $ufdata |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **callOnAfterAddEvent**

Сигнатура: 

```php
protected static callOnAfterAddEvent($object, $fields, $id)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $object | EntityObject |  |
|  | int |         $id |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **callOnBeforeUpdateEvent**

Сигнатура: 

```php
protected static callOnBeforeUpdateEvent($object, $fields, $result)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $object | EntityObject |  |
|  |  |            $result |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **callOnUpdateEvent**

Сигнатура: 

```php
protected static callOnUpdateEvent($object, $fields, $ufdata)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $object | EntityObject |  |
|  |  |            $ufdata |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **callOnAfterUpdateEvent**

Сигнатура: 

```php
protected static callOnAfterUpdateEvent($object, $fields)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $object | EntityObject |  |
|  |  |            $fields |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **callOnBeforeDeleteEvent**

Сигнатура: 

```php
protected static callOnBeforeDeleteEvent($primary, $entity, $result)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $result |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **callOnDeleteEvent**

Сигнатура: 

```php
protected static callOnDeleteEvent($primary, $entity)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $entity |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **callOnAfterDeleteEvent**

Сигнатура: 

```php
protected static callOnAfterDeleteEvent($primary, $entity)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $entity |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **enableCrypto**

Описание: 
Sets a flag indicating crypto support for a field.

Сигнатура: 

```php
public static enableCrypto($field, $table, $mode)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $field | string |  |
| $table | string |  |
|  | bool |  $mode |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentNullException` |
| `Main\ArgumentOutOfRangeException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **cryptoEnabled**

Описание: 
Returns true if crypto is enabled for a field.

Сигнатура: 

```php
public static cryptoEnabled($field, $table)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $field | string |  |
| $table | string |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| bool |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentNullException` |
| `Main\ArgumentOutOfRangeException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)




