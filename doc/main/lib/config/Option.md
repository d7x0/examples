## Класс Option

Пространство имён: `Bitrix\Main\Config`



#### Оглавление:

* Методы:
    * Собственные методы [6]:

        * [Метод get](#метод-get)
        * [Метод getRealValue](#метод-getRealValue)
        * [Метод getDefaults](#метод-getDefaults)
        * [Метод getForModule](#метод-getForModule)
        * [Метод set](#метод-set)
        * [Метод delete](#метод-delete)

![s](/asset/image/separator/30x30.png)

# Методы
## Собственные методы


#### Метод **get**

Описание: 
Returns a value of an option.

Сигнатура: 

```php
public static get($moduleId, $name, $default, $siteId)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $moduleId | string | The module ID. |
| $name | string | The option name. |
| $default | string | The default value to return, if a value doesn't exist. |
| $siteId | bool, string | The site ID, if the option differs for sites. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| string |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentNullException` |
| `Main\ArgumentOutOfRangeException` |

[к оглавлению](#оглавление)

Примеры использования: 

Пример 1

```php
// Table: b_option_site
$ogex11 = Option::get(
    "main", "auth_components_template", "s1");      // $ogex11 = "flat"
$ogex12 = Option::get(
    "main", "auth_components_template", "ru");      // $ogex12 = "flat"
$ogex13 = Option::get(
    "main", "auth_components_template", "");        // $ogex13 = "flat"
// Table: b_option
$ogex14 = Option::get(
    "main", "~crypto_b_user_phone_auth", "");        // $ogex14 = "a:1:{s:10:"OTP_SECRET";b:1;}"

```
Пример 2

```php
try
{
    // Table: b_option_site
    $ogex21 = Option::get(
        "main", "", "");        // Bitrix\Main\ArgumentNullException
}
catch (\Exception $e)
{
    /* Bitrix\Main\ArgumentNullException Object
    (
        [parameter:protected] => name
        [message:protected] => Argument 'name' is null or empty
        [string:Exception:private] =>
        [code:protected] => 100
        [file:protected] => /home/bitrix/www/bitrix/modules/main/lib/config/option.php
        [line:protected] => 34
        [trace:Exception:private] => Array
            (
                [0] => Array
                    (
                        [file] => /home/bitrix/www/local/lib/l7rf1i82.d7.doc/test/php/main/lib/config/OptionExample.php
                        [line] => 35
                        [function] => get
                        [class] => Bitrix\Main\Config\Option
                        [type] => ::
                        [args] => Array
                            (
                                [0] => main
                                [1] =>
                                [2] =>
                            )
                    )
                [1] => Array
                    (
                        [file] => /home/bitrix/www/local/lib/l7rf1i82.d7.doc/test/exec.php
                        [line] => 55
                        [function] => get_example_2
                        [class] => Bitrix\Main\Config\OptionExample
                        [type] => ::
                        [args] => Array
                            (
                            )
                    )
            )
        [previous:Exception:private] =>
    ) */
}

```

![s](/asset/image/separator/30x30.png)


#### Метод **getRealValue**

Описание: 
Returns the real value of an option as it's written in a DB.

Сигнатура: 

```php
public static getRealValue($moduleId, $name, $siteId)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $moduleId | string | The module ID. |
| $name | string | The option name. |
| $siteId | bool, string | The site ID. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| null, string |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentNullException` |

[к оглавлению](#оглавление)

Примеры использования: 

Пример 1

```php
// Table: b_option_site ? expected b_option_site
$ogrex11 = Option::getRealValue(
    "l7rf1i82.d7.doc", "THREAD_COUNT", false);        // $ogrex11 = "8", ? expected "4"
// Table: b_option_site
$ogrex12 = Option::getRealValue(
    "l7rf1i82.d7.doc", "THREAD_COUNT", "s1");         // $ogrex12 = "8"

```

![s](/asset/image/separator/30x30.png)


#### Метод **getDefaults**

Описание: 
Returns an array with default values of a module options (from a default_option.php file).

Сигнатура: 

```php
public static getDefaults($moduleId)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $moduleId | string | The module ID. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentOutOfRangeException` |

[к оглавлению](#оглавление)

Примеры использования: 

Пример 1

```php
$ogdex11 = Option::getDefaults("l7rf1i82.d7.doc");        // $ogdex11 = []
// Table: No table, return array from "default_option.php" file from "wiki" module
$ogdex12 = Option::getDefaults("wiki");                   // $ogdex12 = [ .. ]
/* Array
(
    [allow_html] => Y
    [image_max_width] => 600
    [image_max_height] => 600
    [socnet_iblock_id] =>
    [socnet_iblock_type_id] =>
    [socnet_use_review] =>
    [socnet_message_per_page] =>
    [socnet_use_captcha] =>
    [socnet_forum_id] =>
) */

```

![s](/asset/image/separator/30x30.png)


#### Метод **getForModule**

Описание: 
Returns an array of set options array(name => value).

Сигнатура: 

```php
public static getForModule($moduleId, $siteId)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $moduleId | string | The module ID. |
| $siteId | bool, string | The site ID, if the option differs for sites. |

Возвращаемое значение: 

| Тип | Описание |
| :--- | :--- |
| array |  |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentNullException` |

[к оглавлению](#оглавление)

Примеры использования: 

Пример 1

```php
// Table: b_option
$ogfmex11 = Option::getForModule("wiki", false);        // $ogfmex11 = [ .. ]
/* Array
(
    [GROUP_DEFAULT_RIGHT] => R
) */
// Table:
$ogfmex12 = Option::getForModule("wiki", "s1");        // $ogfmex12 = [ .. ], excepted null
/* Array
(
    [GROUP_DEFAULT_RIGHT] => R
) */

```
Пример 2

```php
// Table: not b_option_site, return data for module from context for specific site
$ogfmex21 = Option::getForModule("sale", "s1");        // $ogfmex21 = [ .. ]
/* Array
(
    [~last_send_date_cashbox] => 20.04.2022 12:25:59
    [~last_send_date_paysystem] => 20.04.2022 12:25:59
    [1C_EXPORT_ALLOW_DELIVERY_ORDERS] => N
    [1C_EXPORT_FINAL_ORDERS] =>
    [1C_EXPORT_PAYED_ORDERS] => N
    [1C_FINAL_STATUS_ON_DELIVERY] => F
    [1C_REPLACE_CURRENCY] => руб.
    [1C_SALE_SITE_LIST] => s1
    [1C_SALE_USE_ZIP] => Y
    [ADDRESS_different_set] => N
    [affiliate_param_name] => partner
    [affiliate_plan_type] => N
    [basket_discount_converted] => Y
    [default_currency] => RUB
    [delete_after] => 30
    [delivery_handles_custom_path] => /bitrix/php_interface/include/sale_delivery/
    [discount_separately_calculation] => N
    [encode_fuser_id] => Y
    [exists_discounts_with_gift] => Y
    [expiration_processing_events] => Y
    [GRAPH_HEIGHT] => 600
    [GRAPH_WEIGHT] => 600
    [GROUP_DEFAULT_RIGHT] => D
    [handlers_dlv_add_rest_wrong_license] => Y
    [location] => 0000073738
    [location_zip] => 101000
    [lock_catalog] => Y
    [MAX_LOCK_TIME] => 30
    [measurement_path] => /bitrix/modules/sale/measurements.php
    [order_email] => sale@192.168.1.7
    [order_list_date] => 30
    [order_list_fields] => ID,USER,PAY_SYSTEM,PRICE,STATUS,PAYED,PS_STATUS,CANCELED,BASKET
    [p2p_status_list] => a:7:{i:0;s:1:"N";i:1;s:1:"P";i:2;s:1:"F";i:3;s:10:"F_CANCELED";i:4;s:10:"F_DELIVERY";i:5;s:5:"F_PAY";i:6;s:5:"F_OUT";}
    [path2user_ps_files] => /bitrix/php_interface/include/sale_payment/
    [product_reserve_clear_period] => 3
    [product_reserve_condition] => P
    [product_viewed_save] => N
    [recalc_product_list] => Y
    [recalc_product_list_period] => 4
    [sale_locationpro_enabled] => Y
    [sale_locationpro_import_performed] => Y
    [sale_locationpro_migrated] => Y
    [sale.location.index_valid] => N
    [saleservices_access] => a:3:{s:9:"client_id";s:26:"bx.625fd1b3cd2470.82184484";s:13:"client_secret";s:50:"MAlZDoCSHPsvEJAfyfFxGkM4To7m2u6FFvyT5iaJAZISWlILBk";s:4:"host";s:11:"192.168.1.7";}
    [SHOP_SITE_s1] => s1
    [show_order_product_xml_id] => N
    [show_order_sum] => N
    [show_paysystem_action_id] => N
    [subscribe_prod] => a:1:{s:2:"s1";a:1:{s:9:"del_after";s:3:"100";}}
    [use_sale_discount_only] => Y
    [viewed_capability] => N
    [viewed_count] => 10
    [viewed_time] => 5
    [WEIGHT_different_set] => N
    [weight_koef] => 1000
    [weight_unit] => кг
) */

```
Пример 3

```php
// Table: not b_option_site, return default data for module from context
$ogfmex31 = Option::getForModule("sale", false);        // $ogfmex31 = [ .. ]
/* Array
(
    see $ogfmex21 result
) */

```

![s](/asset/image/separator/30x30.png)


#### Метод **set**

Описание: 
Sets an option value and saves it into a DB. After saving the OnAfterSetOption event is triggered.

Сигнатура: 

```php
public static set($moduleId, $name, $value, $siteId)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $moduleId | string | The module ID. |
| $name | string | The option name. |
| $value | string | The option value. |
| $siteId | string | The site ID, if the option depends on a site. |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentOutOfRangeException` |

[к оглавлению](#оглавление)

Примеры использования: 

Пример 1

```php
// Table: b_option
$osex11 = Option::set(
    "l7rf1i82.d7.doc", "THREAD_COUNT", 4);          // $osex11 = "null"
// Table: b_option_site
$osex12 = Option::set(
    "l7rf1i82.d7.doc", "THREAD_COUNT", 8, "s1");    // $osex12 = "null"

```

![s](/asset/image/separator/30x30.png)


#### Метод **delete**

Описание: 
Deletes options from a DB. 		name - the name of the option; 		site_id - the site ID (can be empty).

Сигнатура: 

```php
public static delete($moduleId, $filter)
```
Аргументы: 

| Название | Тип | Описание |
| :--- | :--- | :--- |
| $moduleId | string | The module ID. |
| $filter | array | The array with filter keys: |

Исключения: 

| Класс |
| :--- |
| `Main\ArgumentNullException` |

[к оглавлению](#оглавление)

Примеры использования: 

Пример 1

```php
// Table: b_option, b_option_site
$odex11 = Option::delete(
    "l7rf1i82.d7.doc", [ "name" => "THREAD_COUNT"]);                           // $odex11 = null
// Table: b_option_site
$odex21 = Option::delete(
    "l7rf1i82.d7.doc", [ "name" => "THREAD_COUNT", "site_id" => "s1"]);        // $odex21 = null

```

![s](/asset/image/separator/30x30.png)




