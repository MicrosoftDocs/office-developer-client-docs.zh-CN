---
title: 关于货币常量
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82253123
localization_priority: Normal
ms.assetid: d94c740f-29e1-1e7f-39f6-8aa215f3111d
description: 要将数字设为货币格式，可以使用 CY 函数并传递一个可选常量来指定要使用哪个国家（地区）的货币。货币常量可以指定为对应于一个国家（地区）的 ID 号，或者指定为对应于 ISO 4217 三字符缩写的字符串（将该字符串括在引号内）。
ms.openlocfilehash: 4492f4901779d94a32b881c973eab9e32a9c0514
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421793"
---
# <a name="about-currency-constants"></a>关于货币常量

要将数字设为货币格式，可以使用 CY 函数并传递一个可选常量来指定要使用哪个国家（地区）的货币。货币常量可以指定为对应于一个国家（地区）的 ID 号，或者指定为对应于 ISO 4217 三字符缩写的字符串（将该字符串括在引号内）。
  
如果要为非本地货币显示货币符号，而系统不识别指定货币的符号，将会显示美元符号 ($)。
  
## <a name="ids-and-abbreviations"></a>ID 和缩写

|**ID**|**Abbreviation**|**Currency**|
|:-----|:-----|:-----|
| 0  <br/> | http.sys  <br/> | 使用系统设置  <br/> |
| 1  <br/> | 美元  <br/> | 采用数字格式  <br/> |
| 2 - 9  <br/> | Reserved  <br/> |
| 10   <br/> | EUR  <br/> | 欧元  <br/> |
| 11   <br/> | 美元  <br/> | 美元  <br/> |
| 12   <br/> | ATS  <br/> | 奥地利先令  <br/> |
| 13   <br/> | AUD  <br/> | 澳大利亚元  <br/> |
| 14   <br/> | BEF  <br/> | 比利时法郎  <br/> |
| 15   <br/> | CAD  <br/> | 加拿大元  <br/> |
| 16   <br/> | CHF  <br/> | 瑞士法郎  <br/> |
| ×  <br/> | CNY  <br/> | 中国人民币元  <br/> |
| 18  <br/> | DEM  <br/> | 德国马克  <br/> |
| 合  <br/> | DKK  <br/> | 丹麦克朗  <br/> |
| 20  <br/> | ESP  <br/> | 西班牙比塞塔  <br/> |
| 不足  <br/> | FIM  <br/> | 芬兰马克  <br/> |
| 22  <br/> | FRF  <br/> | 法国法郎  <br/> |
| 上午  <br/> | GBP  <br/> | 英国英镑  <br/> |
| 24  <br/> | GRD  <br/> | 希腊德拉克马  <br/> |
| word  <br/> | HKD  <br/> | 香港特别行政区 (SAR) 元  <br/> |
| 26  <br/> | HUF  <br/> | 匈牙利福林  <br/> |
| 27  <br/> | IDR  <br/> | 印度尼西亚卢比  <br/> |
| 28  <br/> | IEP  <br/> | 爱尔兰镑  <br/> |
| 29  <br/> | ILS  <br/> | 以色列谢克尔  <br/> |
| 30  <br/> | ITL  <br/> | 意大利里拉  <br/> |
| 31  <br/> | 您  <br/> | 日元  <br/> |
| 32  <br/> | KRW  <br/> | 朝鲜元  <br/> |
| 33  <br/> | LUF  <br/> | 卢森堡法郎  <br/> |
| 34  <br/> | MXN  <br/> | 墨西哥比索  <br/> |
| 35  <br/> | MYR  <br/> | 马来西亚林吉特  <br/> |
| 36  <br/> | NLG  <br/> | 荷兰盾  <br/> |
| 37  <br/> | NOK  <br/> | 挪威克朗  <br/> |
| 38  <br/> | NZD  <br/> | 新西兰元  <br/> |
| 39  <br/> | PHP  <br/> | 菲律宾比索  <br/> |
| 40  <br/> | PLZ（被 PLN 取代。）  <br/> | 波兰兹罗提  <br/> |
| 41  <br/> | PTE  <br/> | 葡萄牙埃斯库多  <br/> |
| 42  <br/> | ROL  <br/> | 罗马尼亚列伊  <br/> |
| 43  <br/> | RUR（被 RUB 取代。）  <br/> | 俄罗斯卢布  <br/> |
| 44  <br/> | SEK  <br/> | 瑞典克朗  <br/> |
| 45  <br/> | SGD  <br/> | 新加坡元  <br/> |
| 46  <br/> | THB  <br/> | 泰国铢  <br/> |
| 47  <br/> | TWD  <br/> | 新台币  <br/> |
| 48  <br/> | XEU（被 EUR 取代。）  <br/> | 欧洲货币单位（1998 年以前）  <br/> |
| 49  <br/> | YUN（被 YUM 取代。）  <br/> | 南斯拉夫第纳尔  <br/> |
| 50  <br/> | ZAR  <br/> | 南非兰特  <br/> |
| 51 - 55  <br/> | Reserved  <br/> |
| 56  <br/> | ARS  <br/> | 阿根廷比索  <br/> |
| 57  <br/> | BMD  <br/> | 百慕大元  <br/> |
| 58  <br/> | BOB  <br/> | 玻利维亚玻利瓦  <br/> |
| 59  <br/> | BRR（被 BRL 取代。）  <br/> | 巴西克鲁塞罗  <br/> |
| 60  <br/> | BSD  <br/> | 巴哈马元  <br/> |
| 61  <br/> | CLP  <br/> | 智利比索  <br/> |
| 62  <br/> | COP  <br/> | 哥伦比亚比索  <br/> |
| 63  <br/> | CRC  <br/> | 哥斯达黎加科郎  <br/> |
| 64  <br/> | CZK  <br/> | 捷克克朗  <br/> |
| 65  <br/> | DOP  <br/> | 多米尼加比索  <br/> |
| 66  <br/> | ECS  <br/> | 厄瓜多尔苏克雷  <br/> |
| 67  <br/> | EGP  <br/> | 埃及镑  <br/> |
| 68  <br/> | HNL  <br/> | 洪都拉斯伦皮拉  <br/> |
| 69  <br/> | INR  <br/> | 印度卢比  <br/> |
| 70  <br/> | JMD  <br/> | 牙买加元  <br/> |
| 71  <br/> | JOD  <br/> | 约旦第纳尔  <br/> |
| 72  <br/> | KWD  <br/> | 科威特第纳尔  <br/> |
| 73  <br/> | MOP  <br/> | 澳门特别行政区元  <br/> |
| 74  <br/> | NIO  <br/> | 尼加拉瓜金科多巴  <br/> |
| 75  <br/> | .pab  <br/> | 巴拿马巴波亚  <br/> |
| 76  <br/> | 笔尖  <br/> | 秘鲁索尔  <br/> |
| 77  <br/> | PKR  <br/> | 巴基斯坦卢比  <br/> |
| 78  <br/> | PYG  <br/> | 巴拉圭瓜拉尼  <br/> |
| 79  <br/> | SAR  <br/> | 沙特阿拉伯里亚尔  <br/> |
| 80  <br/> | 等待  <br/> | 斯洛文尼亚托拉尔  <br/> |
| 81  <br/> | SKK  <br/> | 斯洛伐克克朗  <br/> |
| 82  <br/> | .svc  <br/> | 萨尔瓦多科郎  <br/> |
| 83  <br/> | TRY  <br/> | 新土耳其里拉  <br/> |
| 84  <br/> | TTD  <br/> | 特立尼达和多巴哥元  <br/> |
| 85  <br/> | UYU  <br/> | 乌拉圭比索  <br/> |
| 86  <br/> | VEB  <br/> | 委内瑞拉玻利瓦  <br/> |
| 87  <br/> | vnd.ms-excel  <br/> | 越南盾  <br/> |
| 88  <br/> | BRL  <br/> | 巴西雷亚尔  <br/> |
| 89  <br/> | PLN  <br/> | 波兰兹罗提  <br/> |
| 90  <br/> | RUB  <br/> | 俄罗斯卢布  <br/> |
| 91  <br/> | YUM  <br/> | 南斯拉夫第纳尔  <br/> |
| 92  <br/> | BYB（被 BYR 取代。）  <br/> | 白俄罗斯卢布  <br/> |
| 93  <br/> | UAH  <br/> | 乌克兰戈里夫纳  <br/> |
| 94  <br/> | AFA  <br/> | 阿富汗尼（在 Visio 2002 中已加入）  <br/> |
| 95  <br/> | 全部  <br/> | 列克（在 Visio 2002 中已加入）  <br/> |
| 96  <br/> | DZD  <br/> | 阿尔及利亚第纳尔（在 Visio 2002 中已加入）  <br/> |
| 97  <br/> | ADP  <br/> | 安道尔比塞塔（在 Visio 2002 中已加入）  <br/> |
| 98  <br/> | AOA  <br/> | 宽扎（在 Visio 2002 中已加入）  <br/> |
| 99  <br/> | XCD  <br/> | 东加勒比元（在 Visio 2002 中已加入）  <br/> |
| 100  <br/> | AMD  <br/> | 亚美尼亚打兰（在 Visio 2002 中已加入）  <br/> |
| 101  <br/> | AWG  <br/> | Aruban 盾（在 Visio 2002 中已加入）  <br/> |
| 102  <br/> | AZM  <br/> | 阿塞拜疆玛纳特（在 Visio 2002 中已加入）  <br/> |
| 103  <br/> | BHD  <br/> | 巴林第纳尔（在 Visio 2002 中已加入）  <br/> |
| 104  <br/> | BDT  <br/> | 塔卡（在 Visio 2002 中已加入）  <br/> |
| 105  <br/> | BBD  <br/> | 巴巴多斯元（在 Visio 2002 中已加入）  <br/> |
| 106  <br/> | BYR  <br/> | 白俄罗斯卢布（在 Visio 2002 中已加入）  <br/> |
| 107  <br/> | BZD  <br/> | 伯利兹元（在 Visio 2002 中已加入）  <br/> |
| 108  <br/> | XOF  <br/> | CFA 法郎 BCEAO（在 Visio 2002 中已加入）  <br/> |
| 109  <br/> | BTN  <br/> | 努尔特鲁姆（在 Visio 2002 中已加入）  <br/> |
| 110  <br/> | BAM  <br/> | 自由兑换马克（在 Visio 2002 中已加入）  <br/> |
| 111  <br/> | BWP  <br/> | 普拉（在 Visio 2002 中已加入）  <br/> |
| 112  <br/> | BND  <br/> | 文莱元（在 Visio 2002 中已加入）  <br/> |
| 113  <br/> | BGL（被 BGN 取代。）  <br/> | Lev  <br/> |
| 114  <br/> | BGN  <br/> | 保加利亚列弗（在 Visio 2002 中已加入）  <br/> |
| 115  <br/> | BIF  <br/> | 布隆迪法郎（在 Visio 2002 中已加入）  <br/> |
| 116  <br/> | KHR  <br/> | 瑞尔（在 Visio 2002 中已加入）  <br/> |
| 117  <br/> | XAF  <br/> | CFA 法郎 BEAC（在 Visio 2002 中已加入）  <br/> |
| 118  <br/> | CVE  <br/> | 佛得角埃斯库多（在 Visio 2002 中已加入）  <br/> |
| 119  <br/> | KYD  <br/> | 开曼群岛元（在 Visio 2002 中已加入）  <br/> |
| 120  <br/> | KMF  <br/> | 科摩罗法郎（在 Visio 2002 中已加入）  <br/> |
| 121  <br/> | CDF  <br/> | 刚果法郎（在 Visio 2002 中已加入）  <br/> |
| 122  <br/> | HRK  <br/> | 克罗地亚库纳（在 Visio 2002 中已加入）  <br/> |
| 123  <br/> | cup of  <br/> | 古巴比索（在 Visio 2002 中已加入）  <br/> |
| 124  <br/> | CYP  <br/> | 塞浦路斯镑（在 Visio 2002 中已加入）  <br/> |
| 125  <br/> | DJF  <br/> | 吉布提法郎（在 Visio 2002 中已加入）  <br/> |
| 126  <br/> | TPE  <br/> | 帝汶埃斯库多（在 Visio 2002 中已加入）  <br/> |
| 127  <br/> | ERN  <br/> | 纳克法（在 Visio 2002 中已加入）  <br/> |
| 128  <br/> | EEK  <br/> | 克鲁恩（在 Visio 2002 中已加入）  <br/> |
| 129  <br/> | ETB  <br/> | 埃塞俄比亚比尔（在 Visio 2002 中已加入）  <br/> |
| 130  <br/> | FKP  <br/> | 福克兰（马尔维纳斯 
）镑（在 Visio 2002 中已加入）  <br/> |
| 131  <br/> | FJD  <br/> | 斐济元（在 Visio 2002 中已加入）  <br/> |
| 132  <br/> | XPF  <br/> | CFP 法郎（在 Visio 2002 中已加入）  <br/> |
| 133  <br/> | GMD  <br/> | 冈比亚达拉西（在 Visio 2002 中已加入）  <br/> |
| 134  <br/> | GEL  <br/> | 拉里（在 Visio 2002 中已加入）  <br/> |
| 135  <br/> | GHC  <br/> | 塞地（在 Visio 2002 中已加入）  <br/> |
| 136  <br/> | GIP  <br/> | 直布罗陀镑（在 Visio 2002 中已加入）  <br/> |
| 137  <br/> | GTQ  <br/> | 格查尔（在 Visio 2002 中已加入）  <br/> |
| 138  <br/> | GNF  <br/> | 几内亚法郎（在 Visio 2002 中已加入）  <br/> |
| 139  <br/> | GWP  <br/> | 几内亚比绍共和国比索（在 Visio 2002 中已加入）  <br/> |
| 140  <br/> | GYD  <br/> | 圭亚那元（在 Visio 2002 中已加入）  <br/> |
| 141  <br/> | HTG  <br/> | 古德（在 Visio 2002 中已加入）  <br/> |
| 142  <br/> | ISK  <br/> | 冰岛克朗（在 Visio 2002 中已加入）  <br/> |
| 143  <br/> | IRR  <br/> | 伊朗里亚尔（在 Visio 2002 中已加入）  <br/> |
| 144  <br/> | IQD  <br/> | 伊拉克第纳尔（在 Visio 2002 中已加入）  <br/> |
| 145  <br/> | KZT  <br/> | 坚戈（在 Visio 2002 中已加入）  <br/> |
| 146  <br/> | KES  <br/> | 肯尼亚先令（在 Visio 2002 中已加入）  <br/> |
| 147  <br/> | KPW  <br/> | 朝鲜元（在 Visio 2002 中已加入）  <br/> |
| 148  <br/> | KGS  <br/> | 索姆（在 Visio 2002 中已加入）  <br/> |
| 149  <br/> | LAK  <br/> | 基普（在 Visio 2002 中已加入）  <br/> |
| 150  <br/> | LVL (历史)。 ）  <br/> | 拉脱维亚拉特（在 Visio 2002 中已加入）  <br/> |
| 151  <br/> | LBP  <br/> | 黎巴嫩镑（在 Visio 2002 中已加入）  <br/> |
| 152  <br/> | LSL  <br/> | 洛蒂（在 Visio 2002 中已加入）  <br/> |
| 153  <br/> | LRD  <br/> | 利比里亚元（在 Visio 2002 中已加入）  <br/> |
| 154  <br/> | LYD  <br/> | 利比亚第纳尔（在 Visio 2002 中已加入）  <br/> |
| 155  <br/> | LTL  <br/> | 立陶宛里特（在 Visio 2002 中已加入）  <br/> |
| 156  <br/> | MKD  <br/> | 代纳尔（在 Visio 2002 中已加入）  <br/> |
| 157  <br/> | MGF（被 MGA 取代。）  <br/> | 马达加斯加法郎（在 Visio 2002 中已加入）  <br/> |
| 158  <br/> | MWK  <br/> | 马拉维克瓦查（在 Visio 2002 中已加入）  <br/> |
| 159  <br/> | MVR  <br/> | 拉菲亚（在 Visio 2002 中已加入）  <br/> |
| 160  <br/> | MTL  <br/> | 马耳他里拉（在 Visio 2002 中已加入）  <br/> |
| 161  <br/> | MRO  <br/> | 乌吉亚（在 Visio 2002 中已加入）  <br/> |
| 162  <br/> | MUR  <br/> | 毛里求斯卢比（在 Visio 2002 中已加入）  <br/> |
| 163  <br/> | MDL  <br/> | 摩尔多瓦列伊（在 Visio 2002 中已加入）  <br/> |
| 164  <br/> | MNT  <br/> | 图格里克（在 Visio 2002 中已加入）  <br/> |
| 165  <br/> | 出色  <br/> | 摩洛哥迪拉姆（在 Visio 2002 中已加入）  <br/> |
| 166  <br/> | MZM  <br/> | 梅蒂卡尔（在 Visio 2002 中已加入）  <br/> |
| 167  <br/> | MMK  <br/> | 缅甸元（在 Visio 2002 中已加入）  <br/> |
| 168  <br/> | NAD  <br/> | 纳米比亚元（在 Visio 2002 中已加入）  <br/> |
| 169  <br/> | NPR  <br/> | 尼泊尔卢比（在 Visio 2002 中已加入）  <br/> |
| 170  <br/> | ANG  <br/> | 安替列群岛荷兰盾（在 Visio 2002 中已加入）  <br/> |
| 171  <br/> | NGN  <br/> | 奈拉（在 Visio 2002 中已加入）  <br/> |
| 172  <br/> | OMR  <br/> | 阿曼里亚尔（在 Visio 2002 中已加入）  <br/> |
| 173  <br/> | PGK  <br/> | 基那（在 Visio 2002 中已加入）  <br/> |
| 174  <br/> | QAR  <br/> | 卡塔尔里亚尔（在 Visio 2002 中已加入）  <br/> |
| 175  <br/> | RWF  <br/> | 卢旺达法郎（在 Visio 2002 中已加入）  <br/> |
| 176  <br/> | SHP  <br/> | 圣赫勒拿镑（在 Visio 2002 中已加入）  <br/> |
| 177  <br/> | WST  <br/> | 塔拉（在 Visio 2002 中已加入）  <br/> |
| 178  <br/> | STD  <br/> | 多布拉（在 Visio 2002 中已加入）  <br/> |
| 179  <br/> | .scr  <br/> | 塞舌尔卢比（在 Visio 2002 中已加入）  <br/> |
| 180  <br/> | SLL  <br/> | 利昂（在 Visio 2002 中已加入）  <br/> |
| 181  <br/> | SBD  <br/> | 索罗门群岛元（在 Visio 2002 中已加入）  <br/> |
| 182  <br/> | SOS  <br/> | 索马里先令（在 Visio 2002 中已加入）  <br/> |
| 183  <br/> | LKR  <br/> | 斯里兰卡卢比（在 Visio 2002 中已加入）  <br/> |
| 184  <br/> | SDD  <br/> | 苏丹第纳尔（在 Visio 2002 中已加入）  <br/> |
| 185  <br/> | SRG  <br/> | 苏里南盾（在 Visio 2002 中已加入）  <br/> |
| 186  <br/> | SZL  <br/> | 里兰吉尼（在 Visio 2002 中已加入）  <br/> |
| 187  <br/> | SYP  <br/> | 叙利亚镑（在 Visio 2002 中已加入）  <br/> |
| 188  <br/> | TJR（被 TJS 取代。）  <br/> | 塔吉克卢布  <br/> |
| 189  <br/> | TJS  <br/> | 塔吉克萨马尼（在 Visio 2002 中已加入）  <br/> |
| 190  <br/> | TZS  <br/> | 坦桑尼亚先令（在 Visio 2002 中已加入）  <br/> |
| 191  <br/> | 返回页首  <br/> | 潘加（在 Visio 2002 中已加入）  <br/> |
| 192  <br/> | TND  <br/> | 突尼斯第纳尔（在 Visio 2002 中已加入）  <br/> |
| 193  <br/> | TMM  <br/> | 马纳特（在 Visio 2002 中已加入）  <br/> |
| 194  <br/> | UGX  <br/> | 乌干达先令（在 Visio 2002 中已加入）  <br/> |
| 195  <br/> | AED  <br/> | 阿联酋迪拉姆（在 Visio 2002 中已加入）  <br/> |
| 196  <br/> | UZS  <br/> | 乌兹别克斯坦苏姆（在 Visio 2002 中已加入）  <br/> |
| 197  <br/> | VUV  <br/> | 瓦图（在 Visio 2002 中已加入）  <br/> |
| 198  <br/> | YER  <br/> | 也门里亚尔（在 Visio 2002 中已加入）  <br/> |
| 199  <br/> | ZMK  <br/> | 赞比亚可瓦查（在 Visio 2002 中已加入）  <br/> |
| 200  <br/> | ZWD  <br/> | 津巴布韦元（在 Visio 2002 中已加入）  <br/> |
|201  <br/> |VEF  <br/> |委内瑞拉玻利瓦（在 Visio 2010 中已加入）  <br/> |
|202  <br/> |MGA  <br/> |马达加斯加阿里亚里（在 Visio 2010 中已加入）  <br/> |
|203  <br/> |会面  <br/> |塞尔维亚第纳尔（在 Visio 2010 中已加入）  <br/> |
|204  <br/> |CSD（被 RSD 取代。）  <br/> |塞尔维亚第纳尔（在 Visio 2010 中已加入）  <br/> |
   

