---
title: DEPENDSON 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251420
localization_priority: Normal
ms.assetid: 8fcfcfdd-69e2-b061-fdb6-d29389d14403
description: 创建一个单元格引用相关性。
ms.openlocfilehash: 07c0d79668230cbf2b1e8d51b50e67835c87e2f5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780081"
---
# <a name="dependson-function"></a>DEPENDSON 函数

创建一个单元格引用相关性。
  
## <a name="syntax"></a>语法

DEPENDSON (* * *cellref* * * [，* * *cellref2* * *，...]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellref_ <br/> |必需  <br/> |**字符串** <br/> |第一个单元格引用。  <br/> |
| _cellref2_ <br/> |可选  <br/> |**字符串** <br/> |第二个单元格引用。  <br/> |
   
## <a name="remarks"></a>注解

此函数总是返回 FALSE。在 Event 行或 Action 单元格中使用时不起任何作用。 
  
## <a name="example"></a>示例

OPENTEXTWIN() + DEPENDSON(PinX,PinY) 
  
只要形状的 PinX 或 PinY 单元格改变，就打开该形状的文本块。 
  

