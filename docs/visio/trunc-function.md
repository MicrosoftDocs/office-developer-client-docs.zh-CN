---
title: TRUNC 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251508
localization_priority: Normal
ms.assetid: 62f074ef-5bf8-df1e-d826-fc1027a36501
description: 返回截断为指定位数的数字。
ms.openlocfilehash: 5b2138ff3091f70313344d5b38d8225d572d8e70
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426497"
---
# <a name="trunc-function"></a>TRUNC 函数

返回截断为指定位数的数字。
  
## <a name="syntax"></a>语法

TRUNC (** *number* **， ** *numberofdigits* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Numeric** <br/> |要截断的数字。  <br/> |
| _numberofdigits_ <br/> |必需  <br/> |**Numeric** <br/> |要截断号码的  _位数_。  <br/> |
   
### <a name="return-value"></a>返回值

数字。
  
## <a name="remarks"></a>备注

如果 _numberofdigits_ 大于 0，_则 number_ 将被截断到小数点右边的 _numberofdigits。_ 如果  _numberofdigits_ 为 0，  _则 number_ 将被截短为整数。 如果 _numberofdigits_ 小于 0，_则 number_ 将被截断为小数点左侧的 _numberofdigits。_ 
  
## <a name="example-1"></a>示例 1

TRUNC (123.654，2) 
  
返回 123.65。
  
## <a name="example-2"></a>示例 2

TRUNC (123.654，0) 
  
返回 123。
  
## <a name="example-3"></a>示例 3

TRUNC (123.654，-1) 
  
返回 120。
  

