## Класс Query

Пространство имён: `Bitrix\Main\ORM\Query`

Query builder for Entities. 

Virtual WHERE methods (proxy to Filter): 

@method $this where(...$filter) 

@see Filter::where() 

@method $this whereNot(...$filter) 

@see Filter::whereNot() 

@method $this whereColumn(...$filter) 

@see Filter::whereColumn() 

@method $this whereNull($column) 

@see Filter::whereNull() 

@method $this whereNotNull($column) 

@see Filter::whereNotNull() 

@method $this whereIn($column, $values) 

@see Filter::whereIn() 

@method $this whereNotIn($column, $values) 

@see Filter::whereNotIn() 

@method $this whereBetween($column, $valueMin, $valueMax) 

@see Filter::whereBetween() 

@method $this whereNotBetween($column, $valueMin, $valueMax) 

@see Filter::whereNotBetween() 

@method $this whereLike($column, $value) 

@see Filter::whereLike() 

@method $this whereNotLike($column, $value) 

@see Filter::whereNotLike() 

@method $this whereExists($query) 

@see Filter::whereExists() 

@method $this whereNotExists($query) 

@see Filter::whereNotExists() 

@method $this whereMatch($column, $value) 

@see Filter::whereMatch() 

@method $this whereNotMatch($column, $value) 

@see Filter::whereNotMatch() 

@method $this whereExpr($expr, $arguments) 

@see Filter::whereExpr() 

Virtual HAVING methods (proxy to Filter): 

@method $this having(...$filter) 

@see Filter::where() 

@method $this havingNot(...$filter) 

@see Filter::whereNot() 

@method $this havingColumn(...$filter) 

@see Filter::whereColumn() 

@method $this havingNull($column) 

@see Filter::whereNull() 

@method $this havingNotNull($column) 

@see Filter::whereNotNull() 

@method $this havingIn($column, $values) 

@see Filter::whereIn() 

@method $this havingNotIn($column, $values) 

@see Filter::whereNotIn() 

@method $this havingBetween($column, $valueMin, $valueMax) 

@see Filter::whereBetween() 

@method $this havingNotBetween($column, $valueMin, $valueMax) 

@see Filter::whereNotBetween() 

@method $this havingLike($column, $value) 

@see Filter::whereLike() 

@method $this havingNotLike($column, $value) 

@see Filter::whereNotLike() 

@method $this havingExists($query) 

@see Filter::whereExists() 

@method $this havingNotExists($query) 

@see Filter::whereNotExists() 

@package Bitrix\Main\ORM

#### Оглавление:

* Методы:
    * Собственные методы:

        1. [Метод __construct](#метод-__construct)
        1. [Метод __call](#метод-__call)
        1. [Метод getSelect](#метод-getSelect)
        1. [Метод setSelect](#метод-setSelect)
        1. [Метод addSelect](#метод-addSelect)
        1. [Метод getFilter](#метод-getFilter)
        1. [Метод setFilter](#метод-setFilter)
        1. [Метод addFilter](#метод-addFilter)
        1. [Метод getFilterHandler](#метод-getFilterHandler)
        1. [Метод getGroup](#метод-getGroup)
        1. [Метод setGroup](#метод-setGroup)
        1. [Метод addGroup](#метод-addGroup)
        1. [Метод getOrder](#метод-getOrder)
        1. [Метод setOrder](#метод-setOrder)
        1. [Метод addOrder](#метод-addOrder)
        1. [Метод getLimit](#метод-getLimit)
        1. [Метод setLimit](#метод-setLimit)
        1. [Метод getOffset](#метод-getOffset)
        1. [Метод setOffset](#метод-setOffset)
        1. [Метод union](#метод-union)
        1. [Метод unionAll](#метод-unionAll)
        1. [Метод setUnionOrder](#метод-setUnionOrder)
        1. [Метод addUnionOrder](#метод-addUnionOrder)
        1. [Метод setUnionLimit](#метод-setUnionLimit)
        1. [Метод setUnionOffset](#метод-setUnionOffset)
        1. [Метод enableDataDoubling](#метод-enableDataDoubling)
        1. [Метод disableDataDoubling](#метод-disableDataDoubling)
        1. [Метод enablePrivateFields](#метод-enablePrivateFields)
        1. [Метод disablePrivateFields](#метод-disablePrivateFields)
        1. [Метод isPrivateFieldsEnabled](#метод-isPrivateFieldsEnabled)
        1. [Метод isFieldPrivate](#метод-isFieldPrivate)
        1. [Метод registerRuntimeField](#метод-registerRuntimeField)
        1. [Метод setCustomBaseTableAlias](#метод-setCustomBaseTableAlias)
        1. [Метод filter](#метод-filter)
        1. [Метод expr](#метод-expr)
        1. [Метод exec](#метод-exec)
        1. [Метод fetch](#метод-fetch)
        1. [Метод fetchAll](#метод-fetchAll)
        1. [Метод fetchObject](#метод-fetchObject)
        1. [Метод fetchCollection](#метод-fetchCollection)
        1. [Метод addToSelectChain](#метод-addToSelectChain)
        1. [Метод setFilterChains](#метод-setFilterChains)
        1. [Метод setFilterHandlerChains](#метод-setFilterHandlerChains)
        1. [Метод divideFilter](#метод-divideFilter)
        1. [Метод divideFilterHandler](#метод-divideFilterHandler)
        1. [Метод checkFilterAggregation](#метод-checkFilterAggregation)
        1. [Метод checkFilterHandlerAggregation](#метод-checkFilterHandlerAggregation)
        1. [Метод rewriteDataDoubling](#метод-rewriteDataDoubling)
        1. [Метод addToGroupChain](#метод-addToGroupChain)
        1. [Метод addToOrderChain](#метод-addToOrderChain)
        1. [Метод buildJoinMap](#метод-buildJoinMap)
        1. [Метод buildJoin](#метод-buildJoin)
        1. [Метод buildWhere](#метод-buildWhere)
        1. [Метод buildGroup](#метод-buildGroup)
        1. [Метод buildHaving](#метод-buildHaving)
        1. [Метод buildOrder](#метод-buildOrder)
        1. [Метод buildQuery](#метод-buildQuery)
        1. [Метод getFilterCswFields](#метод-getFilterCswFields)
        1. [Метод prepareJoinReference](#метод-prepareJoinReference)
        1. [Метод prepareJoinFilterReference](#метод-prepareJoinFilterReference)
        1. [Метод checkChainsAggregation](#метод-checkChainsAggregation)
        1. [Метод collectExprChains](#метод-collectExprChains)
        1. [Метод getUnionHandler](#метод-getUnionHandler)
        1. [Метод getRegisteredChain](#метод-getRegisteredChain)
        1. [Метод query](#метод-query)
        1. [Метод fetchDataModificationCallback](#метод-fetchDataModificationCallback)
        1. [Метод isFetchModificationRequired](#метод-isFetchModificationRequired)
        1. [Метод replaceSelectAliases](#метод-replaceSelectAliases)
        1. [Метод quoteTableSource](#метод-quoteTableSource)
        1. [Метод hasBackReference](#метод-hasBackReference)
        1. [Метод getChains](#метод-getChains)
        1. [Метод getGroupChains](#метод-getGroupChains)
        1. [Метод getHiddenChains](#метод-getHiddenChains)
        1. [Метод getHavingChains](#метод-getHavingChains)
        1. [Метод getFilterChains](#метод-getFilterChains)
        1. [Метод getOrderChains](#метод-getOrderChains)
        1. [Метод getSelectChains](#метод-getSelectChains)
        1. [Метод getWhereChains](#метод-getWhereChains)
        1. [Метод getRuntimeChains](#метод-getRuntimeChains)
        1. [Метод getQuery](#метод-getQuery)
        1. [Метод getLastQuery](#метод-getLastQuery)
        1. [Метод buildFilterSql](#метод-buildFilterSql)
        1. [Метод getInitAlias](#метод-getInitAlias)
        1. [Метод cacheJoins](#метод-cacheJoins)

# Методы
## Собственные методы


#### Метод **__construct**

Сигнатура: 

```php
public __construct($source)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $source | Entity, Query, string |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **__call**

Сигнатура: 

```php
public __call($method, $arguments)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $arguments |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getSelect**

Описание: 
Returns an array of fields for SELECT clause

Сигнатура: 

```php
public getSelect()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **setSelect**

Описание: 
Sets a list of fields for SELECT clause

Сигнатура: 

```php
public setSelect($select)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $select | array |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Query |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **addSelect**

Описание: 
Adds a field for SELECT clause

Сигнатура: 

```php
public addSelect($definition, $alias)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $definition | mixed | Field |
| $alias | string | Field alias like SELECT field AS alias |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getFilter**

Описание: 
Returns an array of filters for WHERE clause

Сигнатура: 

```php
public getFilter()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **setFilter**

Описание: 
Sets a list of filters for WHERE clause

Сигнатура: 

```php
public setFilter($filter)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $filter | array |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **addFilter**

Описание: 
Adds a filter for WHERE clause

Сигнатура: 

```php
public addFilter($key, $value)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $key | string |  |
| $value | mixed |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getFilterHandler**

Сигнатура: 

```php
public getFilterHandler()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Filter |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getGroup**

Описание: 
Returns an array of fields for GROUP BY clause

Сигнатура: 

```php
public getGroup()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **setGroup**

Описание: 
Sets a list of fields in GROUP BY clause

Сигнатура: 

```php
public setGroup($group)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $group | mixed |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **addGroup**

Описание: 
Adds a field to the list of fields for GROUP BY clause

Сигнатура: 

```php
public addGroup($group)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $group |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getOrder**

Описание: 
Returns an array of fields for ORDER BY clause

Сигнатура: 

```php
public getOrder()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **setOrder**

Описание: 
Sets a list of fields for ORDER BY clause. Format:

Сигнатура: 

```php
public setOrder($order)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $order | mixed |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **addOrder**

Описание: 
Adds a filed to the list of fields for ORDER BY clause

Сигнатура: 

```php
public addOrder($definition, $order)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $definition | string |  |
| $order | string |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getLimit**

Описание: 
Returns a limit

Сигнатура: 

```php
public getLimit()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| null, int |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **setLimit**

Описание: 
Sets a limit for LIMIT n clause

Сигнатура: 

```php
public setLimit($limit)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $limit | int |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getOffset**

Описание: 
Returns an offset

Сигнатура: 

```php
public getOffset()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| null, int |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **setOffset**

Описание: 
Sets an offset for LIMIT n, m clause

Сигнатура: 

```php
public setOffset($offset)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $offset | int |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **union**

Описание: 
Puts additional query to union with current. Accepts one ore more Query  SqlExpression.

Сигнатура: 

```php
public union()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **unionAll**

Описание: 
Puts additional query to union (all) with current. Accepts one ore more Query  SqlExpression.

Сигнатура: 

```php
public unionAll()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **setUnionOrder**

Описание: 
General order for all the union queries. Has the same format as Query::setOrder(). @see Query::setOrder()

Сигнатура: 

```php
public setUnionOrder($order)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $order |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **addUnionOrder**

Описание: 
General order for all the union queries. Has the same format as Query::addOrder(). @see Query::addOrder()

Сигнатура: 

```php
public addUnionOrder($definition, $order)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $definition | string |  |
| $order | string |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **setUnionLimit**

Описание: 
General limit for all the union queries.

Сигнатура: 

```php
public setUnionLimit($limit)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $limit |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **setUnionOffset**

Описание: 
General offset for all the union queries.

Сигнатура: 

```php
public setUnionOffset($offset)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $offset |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **enableDataDoubling**

Описание: 
@see disableDataDoubling

Сигнатура: 

```php
public enableDataDoubling()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **disableDataDoubling**

Описание: 
Replaces all 1:N relations in filter to ID IN (subquery SELECT ID FROM <1:N relation>) Available for Entities with 1 primary field only

Сигнатура: 

```php
public disableDataDoubling()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **enablePrivateFields**

Описание: 
Allows private fields in query

Сигнатура: 

```php
public enablePrivateFields()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **disablePrivateFields**

Описание: 
Restricts private fields in query

Сигнатура: 

```php
public disablePrivateFields()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **isPrivateFieldsEnabled**

Сигнатура: 

```php
public isPrivateFieldsEnabled()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| bool |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **isFieldPrivate**

Сигнатура: 

```php
public static isFieldPrivate($field)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $field | Field, Main\ORM\Fields\IReadable |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| bool |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **registerRuntimeField**

Описание: 
Adds a runtime field (being created dynamically, opposite to being described statically in the entity map)

Сигнатура: 

```php
public registerRuntimeField($name, $fieldInfo)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $name | string, null |  |
| $fieldInfo | array, Field |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **setCustomBaseTableAlias**

Описание: 
Sets a custom alias for the table of the init entity

Сигнатура: 

```php
public setCustomBaseTableAlias($alias)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $alias | string |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **filter**

Описание: 
Returns new instance of Filter. Usage: Alternatively short calls Query::where can be used. @see Query::where()

Сигнатура: 

```php
public static filter()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Filter |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **expr**

Описание: 
Used to create ExpressionField in a short way. @see Filter::where()

Сигнатура: 

```php
public static expr()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Expression |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **exec**

Описание: 
Builds and executes the query and returns the result

Сигнатура: 

```php
public exec()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Result |  |

Исключения: 

| Класс |
| :--- |
| `Main\ObjectPropertyException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **fetch**

Описание: 
Short alias for $result->fetch()

Сигнатура: 

```php
public fetch($converter)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $converter | Main\Text\Converter, null |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array, false |  |

Исключения: 

| Класс |
| :--- |
| `Main\ObjectPropertyException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **fetchAll**

Описание: 
Short alias for $result->fetchAll()

Сигнатура: 

```php
public fetchAll($converter)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $converter | Main\Text\Converter, null |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

Исключения: 

| Класс |
| :--- |
| `Main\ObjectPropertyException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **fetchObject**

Описание: 
Short alias for $result->fetchObject()

Сигнатура: 

```php
public fetchObject()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| null | Actual type should be annotated by orm:annotate |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\ObjectPropertyException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **fetchCollection**

Описание: 
Short alias for $result->fetchCollection()

Сигнатура: 

```php
public fetchCollection()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| null | Actual type should be annotated by orm:annotate |

Исключения: 

| Класс |
| :--- |
| `Main\ObjectPropertyException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **addToSelectChain**

Сигнатура: 

```php
protected addToSelectChain($definition, $alias)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  |  |    $definition |
| $alias | null |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **setFilterChains**

Сигнатура: 

```php
public setFilterChains($filter, $section)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  |  |      $filter |
| $section | string |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **setFilterHandlerChains**

Сигнатура: 

```php
public setFilterHandlerChains($where, $section)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $where | Filter |  |
| $section | string |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **divideFilter**

Сигнатура: 

```php
protected divideFilter()
```

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **divideFilterHandler**

Сигнатура: 

```php
protected divideFilterHandler()
```

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **checkFilterAggregation**

Сигнатура: 

```php
protected checkFilterAggregation($filter)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $filter |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| bool |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **checkFilterHandlerAggregation**

Сигнатура: 

```php
protected checkFilterHandlerAggregation($filter)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $filter | Filter |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| bool |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **rewriteDataDoubling**

Сигнатура: 

```php
protected rewriteDataDoubling($filter, $section)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $filter | Filter |  |
|  |  |      $section |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **addToGroupChain**

Сигнатура: 

```php
protected addToGroupChain($definition)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $definition |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **addToOrderChain**

Сигнатура: 

```php
protected addToOrderChain($definition)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $definition |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **buildJoinMap**

Сигнатура: 

```php
protected buildJoinMap($chains)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $chains | null |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **buildJoin**

Сигнатура: 

```php
protected buildJoin()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **buildWhere**

Сигнатура: 

```php
protected buildWhere()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **buildGroup**

Сигнатура: 

```php
protected buildGroup()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **buildHaving**

Сигнатура: 

```php
protected buildHaving()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **buildOrder**

Сигнатура: 

```php
protected buildOrder()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **buildQuery**

Сигнатура: 

```php
protected buildQuery($forceObjectPrimary)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $forceObjectPrimary | bool | Add missing primaries to select |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| mixed, string |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getFilterCswFields**

Сигнатура: 

```php
protected getFilterCswFields($filter)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $filter |  |

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


#### Метод **prepareJoinReference**

Сигнатура: 

```php
protected prepareJoinReference($reference, $alias_this, $alias_ref, $baseDefinition, $refDefinition, $isBackReference)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $isBackReference |  |

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


#### Метод **prepareJoinFilterReference**

Сигнатура: 

```php
protected prepareJoinFilterReference($reference, $alias_this, $alias_ref, $baseDefinition, $refDefinition, $isBackReference, $firstCall)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $reference | Filter |  |
|  |  |      $firstCall |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Filter |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **checkChainsAggregation**

Сигнатура: 

```php
protected checkChainsAggregation($chain)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $chain |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| bool |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **collectExprChains**

Описание: 
The most magic method. Do not edit without strong need, and for sure run tests after.

Сигнатура: 

```php
protected collectExprChains($chain, $storages)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $chain | Chain |  |
| $storages | array |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Chain[] |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getUnionHandler**

Сигнатура: 

```php
protected getUnionHandler()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Union |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getRegisteredChain**

Сигнатура: 

```php
public getRegisteredChain($key, $force_create)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  |  |    $key |
| $force_create | bool |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Chain, bool |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **query**

Сигнатура: 

```php
protected query($query)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $query |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Main\DB\ArrayResult, Main\DB\Result |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\Db\SqlQueryException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **fetchDataModificationCallback**

Описание: 
Being called in Db\Result as a data fetch modifier

Сигнатура: 

```php
public fetchDataModificationCallback($data)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $data |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **isFetchModificationRequired**

Описание: 
Check if fetch data modification required, also caches modifier-callbacks

Сигнатура: 

```php
public isFetchModificationRequired()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| bool |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **replaceSelectAliases**

Сигнатура: 

```php
protected replaceSelectAliases($query)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $query |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **quoteTableSource**

Сигнатура: 

```php
public quoteTableSource($source)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | $source |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **hasBackReference**

Сигнатура: 

```php
public hasBackReference()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| bool |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getChains**

Сигнатура: 

```php
public getChains()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array, Chain[] |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getGroupChains**

Сигнатура: 

```php
public getGroupChains()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array, Chain[] |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getHiddenChains**

Сигнатура: 

```php
public getHiddenChains()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getHavingChains**

Сигнатура: 

```php
public getHavingChains()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array, Chain[] |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getFilterChains**

Сигнатура: 

```php
public getFilterChains()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array, Chain[] |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getOrderChains**

Сигнатура: 

```php
public getOrderChains()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array, Chain[] |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getSelectChains**

Сигнатура: 

```php
public getSelectChains()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array, Chain[] |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getWhereChains**

Сигнатура: 

```php
public getWhereChains()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array, Chain[] |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getRuntimeChains**

Сигнатура: 

```php
public getRuntimeChains()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| Chain[] |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getQuery**

Описание: 
Builds and returns SQL query string

Сигнатура: 

```php
public getQuery($forceObjectPrimary)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $forceObjectPrimary | bool |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getLastQuery**

Описание: 
Returns last executed query string

Сигнатура: 

```php
public static getLastQuery()
```

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **buildFilterSql**

Описание: 
Builds SQL filter conditions for WHERE. Useful for external calls: building SQL for mass UPDATEs or DELETEs

Сигнатура: 

```php
public static buildFilterSql($entity, $filter)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
|  | Entity |      $entity |
| $filter | array, Filter | the same format as for setFilterwhere |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentException` |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **getInitAlias**

Сигнатура: 

```php
public getInitAlias($withPostfix)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $withPostfix | bool |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

Исключения: 

| Класс |
| :--- |
| `Main\SystemException` |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)


#### Метод **cacheJoins**

Описание: 
Enables or disables caching of queries with joins.

Сигнатура: 

```php
public cacheJoins($mode)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $mode | bool |  |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| $this |  |

[к оглавлению](#оглавление)

![s](/asset/image/separator/30x30.png)




