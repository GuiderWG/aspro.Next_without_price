#Aspro.Next - без цен :fire:
------


## Общее
Добавить в инфоблок "Каталог" свойство - 
[1 Скрин](https://yadi.sk/i/CYctmXc8RJQvOA) => [2 Скрин](https://yadi.sk/i/tRVbSoIPzPcPTg) => [3 скрин](https://yadi.sk/i/7u9lIAdl1c-O7g)

------
------

## На главной в [хитах](https://yadi.sk/i/8pLOV7TNYdZHuw) 
#### В файле [Скринкод](https://yadi.sk/i/eYzBTXA09JfABw)
`/www/bitrix/templates/aspro_next/components/bitrix/catalog.section/catalog_block_front/lang/ru/template.php` - добавить переменную
``` php
"$MESS["WITHOUT_PRICE"] = "Цена по запросу"; 
```
#### В файле [Скринкод](https://yadi.sk/i/o_NZuvxSI1q0OA)
`/www/bitrix/templates/aspro_next/components/bitrix/catalog.section/catalog_block_front/result_modifier.php` - добавить условие
``` php 
if(isset($arItem["PROPERTIES"]["WITHOUT_PRICE"]))
                $arTmpProps["WITHOUT_PRICE"]=$arItem["PROPERTIES"]["WITHOUT_PRICE"];
```

#### В файле [Скринкод](https://yadi.sk/i/yjXWykGPlevjHA)
`/www/bitrix/templates/aspro_next/components/bitrix/catalog.section/catalog_block_front/template.php` - добавить условие

``` php
<? if (!empty($arItem["PROPERTIES"]["WITHOUT_PRICE"]["VALUE"])) { ?>
    <? $without_price_text = GetMessage('WITHOUT_PRICE'); ?>
    <span class="without-price"><?=$without_price_text?></span>
<? } else { ?>
    <? \Aspro\Functions\CAsproSku::showItemPrices($arParams, $arItem, $item_id, $min_price_id, array(), ($arParams["SHOW_DISCOUNT_PERCENT_NUMBER"] == "Y" ? "N" : "Y")); ?>
<? } ?>
```

------
------

## В каталоге в [разделах](https://yadi.sk/i/Cm8LDydBMiJMCw) 

### Сетка "плиткой" 
#### В файле [Скринкод](https://yadi.sk/i/9JBtbzQqQyF5PQ)
`/www/bitrix/templates/aspro_next/components/bitrix/catalog.section/catalog_block/lang/ru/template.php` - добавить переменную
``` php
"$MESS["WITHOUT_PRICE"] = "Цена по запросу"; 
```

#### В файле [Скринкод](https://yadi.sk/i/DubVsd-fa94hkQ)
`/www/bitrix/templates/aspro_next/components/bitrix/catalog.section/catalog_block/template.php` - добавить условие

``` php
<? if (!empty($arItem["PROPERTIES"]["WITHOUT_PRICE"]["VALUE"])) { ?>
    <? $without_price_text = GetMessage('WITHOUT_PRICE'); ?>
    <span class="without-price"><?=$without_price_text?></span>
<? } else { ?>
    <?\Aspro\Functions\CAsproSku::showItemPrices($arParams, $arItem, $item_id, $min_price_id, $arItemIDs, ($arParams["SHOW_DISCOUNT_PERCENT_NUMBER"] == "Y" ? "N" : "Y"));?>
<? } ?>
```

### Сетка "списком" 
#### В файле [Скринкод](https://yadi.sk/i/hNGa2tvTyZtj6Q)
`/www/bitrix/templates/aspro_next/components/bitrix/catalog.section/catalog_list/lang/ru/template.php` - добавить переменную
``` php
"$MESS["WITHOUT_PRICE"] = "Цена по запросу"; 
```

#### В файле [Скринкод](https://yadi.sk/i/DubVsd-fa94hkQ)
`/www/bitrix/templates/aspro_next/components/bitrix/catalog.section/catalog_list/template.php` - добавить условие

``` php
<? if (!empty($arItem["PROPERTIES"]["WITHOUT_PRICE"]["VALUE"])) { ?>
    <? $without_price_text = GetMessage('WITHOUT_PRICE'); ?>
    <span class="without-price"><?=$without_price_text?></span>
<? } else { ?>
    <?\Aspro\Functions\CAsproSku::showItemPrices($arParams, $arItem, $item_id, $min_price_id, $arItemIDs, ($arParams["SHOW_DISCOUNT_PERCENT_NUMBER"] == "Y" ? "N" : "Y"));?>
<? } ?>
```

### Сетка "таблицей" 
#### В файле [Скринкод](https://yadi.sk/i/5qadAyPmzWF35Q)
`/www/bitrix/templates/aspro_next/components/bitrix/catalog.section/catalog_table/lang/ru/template.php` - добавить переменную
``` php
"$MESS["WITHOUT_PRICE"] = "Цена по запросу"; 
```

#### В файле [Скринкод](https://yadi.sk/i/5mh-uflUChdPnA)
`/www/bitrix/templates/aspro_next/components/bitrix/catalog.section/catalog_table/template.php` - добавить условие

``` php
<? if (!empty($arItem["PROPERTIES"]["WITHOUT_PRICE"]["VALUE"])) { ?>
    <? $without_price_text = GetMessage('WITHOUT_PRICE'); ?>
    <span class="without-price"><?=$without_price_text?></span>
<? } else { ?>
    <?\Aspro\Functions\CAsproSku::showItemPrices($arParams, $arItem, $item_id, $min_price_id, array(), ($arParams["SHOW_DISCOUNT_PERCENT_NUMBER"] == "Y" ? "N" : "Y"));?>
<? } ?>
```

## В каталоге в [карточке](https://yadi.sk/i/6-LdXS6dpW_Wzw) 

#### В файле [Скринкод](https://yadi.sk/i/uToMKk4JNZde9w)
`/www/bitrix/templates/aspro_next/components/bitrix/catalog.element/custom/lang/ru/template.php` - добавить переменную
``` php
"$MESS["WITHOUT_PRICE"] = "Цена по запросу"; 
```

#### В файле [Скринкод](https://yadi.sk/i/QYGRgNl0c2r3Iw)
`/www/bitrix/templates/aspro_next/components/bitrix/catalog.element/custom/template.php` - добавить условие

``` php
<? if (!empty($arResult["PROPERTIES"]["WITHOUT_PRICE"]["VALUE"])) { ?>
    <? $without_price_text = GetMessage('WITHOUT_PRICE'); ?>
    <span class="without-price"><?=$without_price_text?></span>
<? } else { ?>
    <?\Aspro\Functions\CAsproSku::showItemPrices($arParams, $arResult, $item_id, $min_price_id, $arItemIDs, ($arParams["SHOW_DISCOUNT_PERCENT_NUMBER"] == "Y" ? "N" : "Y"));?>
<? } ?>
```