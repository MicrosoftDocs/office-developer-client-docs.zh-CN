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
description: 存储在用户界面 (UI) 或自动化中通过某项操作设置一个值。
ms.openlocfilehash: c664717afcc2b81e55495fd1957a86ef1b021d0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781257"
---
# <a name="setatrefexpr-function"></a>SETATREFEXPR 函数

存储在用户界面 (UI) 或自动化中通过某项操作设置一个值。
  
## <a name="syntax"></a>语法

SETATREFEXPR ([* * *expr_opt* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expr_opt_ <br/> |可选  <br/> |**因情况而异** <br/> |表达式，用于替换为其分配到 SETATREF 函数中引用的单元格的表达式的值。 如果未指示，其初始值为 0 （零）。  <br/> |
   
## <a name="remarks"></a>注解

还可以通过其他单元格（该单元格引用包含 SETATREFEXPR 表达式的单元格）中的 SETATREF 函数设置 SETATREFEXPR 表达式的值。 
  
您不限于使用 SETATREFEXPR 函数作为 SETATREF 函数的参数。 
  
## <a name="example-1"></a>示例 1

下面的示例使用 SETATREFEXPR 函数来确保形状的宽度与其文本的宽度相同。
  
Width =MAX(TEXTWIDTH(TheText),SETATREFEXPR())
  
## <a name="example-2"></a>示例 2

下面的示例说明如何使用 SETATREFEXPR 函数使形状与自定义网格对齐。SETATREFEXPR 公式放置于 PinX 和 PinY 单元格中，使形状的旋转中心点与 User.GridX 和 User.GridY 中定义的网格对齐。 
  
User.GridX =2 in
  
User.GridY =2 in
  
PinX = INT (SETATREFEXPR （) /User.GridX +.5)\*User.GridX
  
PinY = INT (SETATREFEXPR （) /User.GridY +.5)\*User.GridY
  
## <a name="example-3"></a>示例 3

有关 SETATREFEXPR 函数与 SETATREF 函数结合使用的示例，请参阅 [SETATREF](setatref-function.md) 函数。 
  

