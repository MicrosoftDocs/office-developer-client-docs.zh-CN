---
title: CEILING 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251405
localization_priority: Normal
ms.assetid: 1a8d6d48-7ae3-5483-28d2-5b1706088a53
description: 将数字从 0（零）后舍入到 multiple 的下一个实例。如果未指定 multiple，会将数字从 0 后舍入到下一个整数。
ms.openlocfilehash: fa982b44ea4a73e7da614c49a52cd50efd612f20
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779824"
---
# <a name="ceiling-function"></a>CEILING 函数

舍入数字向远离 0 （零） 到_多个_的下一个实例。 如果未指定_multiple_ ，则数字舍入数字向远离 0 到下一个整数。 
  
## <a name="syntax"></a>语法

CEILING (* **数量** *，* **多个** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**编号** <br/> |要舍入的数值。  <br/> |
| _多个_ <br/> |必需  <br/> |**编号** <br/> |要舍入到的倍数。  <br/> |
   
## <a name="remarks"></a>注解

 _号码_和_多个_必须具有相同的迹象或 #NUM ！ 将返回错误。 如果_号码_或_多个_不能转换为一个值，#VALUE ！ 将返回错误。 如果_号码_或_多个_为 0，则结果为 0。 
  
## <a name="example-1"></a>示例 1

CEILING(3.7)
  
返回 4
  
## <a name="example-2"></a>示例 2

CEILING(-3.7)
  
返回 -4
  
## <a name="example-3"></a>示例 3

CEILING （3.7、 0.25）
  
返回 3.75
  

