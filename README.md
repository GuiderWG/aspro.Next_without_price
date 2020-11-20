#Aspro.Next - без цен :fire:
------


## Общее
Добавить в инфоблок "Каталог" свойство - 
[1 Скрин](https://yadi.sk/i/CYctmXc8RJQvOA) => [2 Скрин](https://yadi.sk/i/tRVbSoIPzPcPTg) => [3 скрин](https://yadi.sk/i/7u9lIAdl1c-O7g)

------
------

## На главной в [хитах](https://yadi.sk/i/8pLOV7TNYdZHuw) 
#### В файле [Скринкод](https://yadi.sk/i/eYzBTXA09JfABw)
`/home/c26353/dev.universalopt.ru/www/bitrix/templates/aspro_next/components/bitrix/catalog.section/catalog_block_front/lang/ru/template.php` - добавить переменную
``` php
"$MESS["WITHOUT_PRICE"] = "Цена по запросу"; 
```
#### В файле [Скринкод](https://yadi.sk/i/o_NZuvxSI1q0OA)
`/home/c26353/dev.universalopt.ru/www/bitrix/templates/aspro_next/components/bitrix/catalog.section/catalog_block_front/result_modifier.php` - добавить условие
``` php 
if(isset($arItem["PROPERTIES"]["WITHOUT_PRICE"]))
                $arTmpProps["WITHOUT_PRICE"]=$arItem["PROPERTIES"]["WITHOUT_PRICE"];
```

#### В файле [Скринкод](https://yadi.sk/i/yjXWykGPlevjHA)
`/home/c26353/dev.universalopt.ru/www/bitrix/templates/aspro_next/components/bitrix/catalog.section/catalog_block_front/template.php` - добавить условие

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