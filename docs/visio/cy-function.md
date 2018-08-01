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
description: 返回一个货币值。
ms.openlocfilehash: ea7696e7628939466730b9c054a706a7a9fa264e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780005"
---
# <a name="cy-function"></a>CY 函数

返回一个货币值。
  
## <a name="syntax"></a>语法

CY (* **值** *，* * *cyID* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _value_ <br/> |可选  <br/> |**数字或字符串** <br/> |数字或字符串，其中包含货币特定的格式。 如果未指定，将货币值根据系统的区域和语言设置中的货币样式格式。  <br/> |
| _cyID_ <br/> |可选  <br/> |**编号** <br/> |数字货币 ID 或三个字符引号的字符串组成的 ISO 4217 缩写。  <br/> |
   
## <a name="remarks"></a>说明

若要指定不同的货币，必须包括有效的_cyID_。 有关列表，请参阅[关于货币常量](about-currency-constants.md)。
  
如果_值_为与指定的货币类型，不兼容或无效的参数，如"而不是数字"如果已指定，#VALUE ！ 将返回错误。 如果_值_大于 922,337,203,685,477.5807 或小于-922337203685，477.5808，则 #VALUE ！ 将返回错误。 
  
更加精确地非常大的货币值的带小数的单位，如 3.6 万亿，请使用字符串参数的_值_。
  
指定无效的_cyID_将返回错误。 
  
## <a name="example-1"></a>示例 1

如果用户的“区域和语言设置”指定了美国美元：
  
CY(999998.993)
  
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
  

