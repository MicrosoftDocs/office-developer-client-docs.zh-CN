---
title: SETATREFEXPR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1027317
localization_priority: Normal
ms.assetid: c1bd7819-b53b-bff1-69c1-6d78e8fb278b
description: 存储通过用户界面 (UI) 或自动化中的操作设置的值。
ms.openlocfilehash: 5ca7b59d0ced9c3da346c416826ac89e6b4001da
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439049"
---
# <a name="setatrefexpr-function"></a>SETATREFEXPR 函数

存储通过用户界面 (UI) 或自动化中的操作设置的值。
  
## <a name="syntax"></a>语法

SETATREFEXPR ([* * *expr_opt* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expr_opt_ <br/> |可选  <br/> |**相同** <br/> |由赋给 SETATREF 函数中引用单元格的值或表达式所替换的表达式。 如果未指明, 其初始值为 0 (零)。  <br/> |
   
## <a name="remarks"></a>说明

还可以通过其他单元格（该单元格引用包含 SETATREFEXPR 表达式的单元格）中的 SETATREF 函数设置 SETATREFEXPR 表达式的值。 
  
您并不局限于将 SETATREFEXPR 函数用作 SETATREF 函数的参数。 
  
## <a name="example-1"></a>示例 1

下面的示例使用 SETATREFEXPR 函数来确保形状的宽度与其文本的宽度相同。
  
Width =MAX(TEXTWIDTH(TheText),SETATREFEXPR())
  
## <a name="example-2"></a>示例 2

下面的示例说明如何使用 SETATREFEXPR 函数使形状与自定义网格对齐。SETATREFEXPR 公式放置于 PinX 和 PinY 单元格中，使形状的旋转中心点与 User.GridX 和 User.GridY 中定义的网格对齐。 
  
User.GridX =2 in
  
User.GridY =2 in
  
PinX = INT (SETATREFEXPR ()/User.GridX + .5)\*用户 GridX
  
PinY = INT (SETATREFEXPR ()/User.GridY + .5)\*User. GridY
  
## <a name="example-3"></a>示例 3

有关 SETATREFEXPR 函数与 SETATREF 函数结合使用的示例，请参阅 [SETATREF](setatref-function.md) 函数。 
  

