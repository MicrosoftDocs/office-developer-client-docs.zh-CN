---
title: SQRT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251500
localization_priority: Normal
ms.assetid: 513302d3-3be8-882f-5258-95529098f95d
description: 返回数字的平方根。
ms.openlocfilehash: f9f31b9360248f002cac74dfb87ac3b292d34620
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349355"
---
# <a name="sqrt-function"></a>SQRT 函数

返回数字的平方根。 
  
## <a name="syntax"></a>语法

SQRT (* **数字** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Numeric** <br/> |要查找其平方根的数。  <br/> |
   
### <a name="return-value"></a>返回值

Numeric
  
## <a name="remarks"></a>注解

如果_number_为负值, SQRT 函数将返回错误值 #NUM!。 
  
## <a name="example"></a>示例

SQRT (2) 
  
返回 1.4142。 
  

