---
title: GETVAL 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251885
localization_priority: Normal
ms.assetid: 1da42991-5791-ebab-84cc-286cfe984a61
description: 获取单元格的值和单元格的值更改时不重新计算公式。
ms.openlocfilehash: b4c8ea14b7184101a360c9f5ee4af03fd178aa6d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780341"
---
# <a name="getval-function"></a>GETVAL 函数

获取单元格的值和单元格的值更改时不重新计算公式。
  
## <a name="syntax"></a>语法

GETVAL (* * *cellname* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellname_ <br/> |必需  <br/> |**字符串** <br/> |要获取其值的单元格的名称。  <br/> |
   
## <a name="example"></a>示例

GETVAL(PinX) + GETVAL(PinY) + Width 
  
返回 PinX、PinY 和 Width 单元格的值的总和。 
  

