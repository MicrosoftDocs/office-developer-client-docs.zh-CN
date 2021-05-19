---
title: CY 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253223
localization_priority: Normal
ms.assetid: abb27f90-21b4-08cd-6995-9520fbcebd78
description: 返回货币值。
ms.openlocfilehash: 65c88d69669e2fa7f708402d9d50dfe035456edb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433554"
---
# <a name="cy-function"></a>CY 函数

返回货币值。
  
## <a name="syntax"></a>语法

CY (** *value* **， ** *cyID* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _value_ <br/> |可选  <br/> |**数字或字符串** <br/> |包含货币特定格式的一个数字或字符串。 如果未指定，则根据系统的"地区"和"语言"设置中的货币样式设置货币值的格式。  <br/> |
| _cyID_ <br/> |可选  <br/> |**Number** <br/> |ISO 4217 缩写的数字货币 ID 或三个字符引用的字符串。  <br/> |
   
## <a name="remarks"></a>备注

若要指定不同的货币，必须包含有效的  _cyID_。 若要获取列表，请参阅[关于货币常量](about-currency-constants.md)。
  
如果  _值_ 与指定的货币类型不兼容，或者指定了无效的参数（如"非数字"），则#VALUE！ 错误。 如果  _值_ 大于 922，337，203，685，477.5807 或小于 -922，337，203，685，477.5808，#VALUE！ 错误。 
  
对于包含单位分数的非常大的货币值（如 3.6 万亿）的精度更高，请使用字符串参数作为  _值_。
  
指定无效的  _cyID_ 将返回错误。 
  
## <a name="example-1"></a>示例 1

如果用户的“区域和语言设置”指定了美国美元：
  
CY (999998.993) 
  
返回 $999,998.99
  
## <a name="example-2"></a>示例 2

CY(12345678.993, "USD")
  
返回 $12,345,678.99
  
## <a name="example-3"></a>示例 3

CY(12345678.993, "DEM")
  
返回 12,345,678.99 DEM
  
## <a name="example-4"></a>示例 4

CY(12345678.7832, "XXX")
  
返回 12,345,678.78
  

