---
title: GETREF 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251884
localization_priority: Normal
ms.assetid: 25c9f817-d22b-28c9-1339-dc9f27d0dd41
description: 引用单元格, 并且在引用的单元格发生更改时不重新计算公式。
ms.openlocfilehash: 38f3c8b4f34ed2b3d3711be5faed6b0d317e907a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424327"
---
# <a name="getref-function"></a>GETREF 函数

引用单元格, 并且在引用的单元格发生更改时不重新计算公式。
  
## <a name="syntax"></a>语法

GETREF (* * *cellname* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellname_ <br/> |必需  <br/> |**String** <br/> |要获取其引用的单元格的名称。  <br/> |
   
## <a name="example"></a>示例

SETF (GETREF (PinX), 5.1) 
  
将 PinX 单元格的公式设置为 5.1。 
  

