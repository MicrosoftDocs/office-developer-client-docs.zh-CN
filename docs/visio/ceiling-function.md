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
description: 将数字从 0（零）后舍入到 multiple 的下一个实例。 如果未指定 multiple，会将数字从 0 后舍入到下一个整数。
ms.openlocfilehash: 449f17d1b68c116cccb2635723a3f6277d0ac2a9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337224"
---
# <a name="ceiling-function"></a>CEILING 函数

将数字从 0 (零) 舍入到下一个_多个_实例。 如果未指定_多个_, 则该数字将从0舍入到下一个整数。 
  
## <a name="syntax"></a>语法

天花板 (* * *number* * *、* **多** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Number** <br/> |要舍入的数字。  <br/> |
| _多位_ <br/> |必需  <br/> |**Number** <br/> |要舍入到的倍数。  <br/> |
   
## <a name="remarks"></a>注解

 _数字_和_多个_必须具有相同的符号或 #NUM! 错误。 如果_number_或_倍数_无法转换为值, #VALUE! 错误。 如果有一个_数_或_多个_值为 0, 则结果为0。 
  
## <a name="example-1"></a>示例 1

天花板 (3.7)
  
返回 4
  
## <a name="example-2"></a>示例 2

天花板 (-3.7)
  
返回 -4
  
## <a name="example-3"></a>示例 3

天花板 (3.7, 0.25)
  
返回 3.75
  

