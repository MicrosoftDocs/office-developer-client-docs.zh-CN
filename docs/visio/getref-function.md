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
description: 引用单元格和引用的单元格更改时不重新计算公式。
ms.openlocfilehash: 454314b1f156f560c237f22a45492978ca3c31ca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780339"
---
# <a name="getref-function"></a>GETREF 函数

引用单元格和引用的单元格更改时不重新计算公式。
  
## <a name="syntax"></a>语法

GETREF (* * *cellname* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellname_ <br/> |必需  <br/> |**字符串** <br/> |要获取的引用的单元格的名称。  <br/> |
   
## <a name="example"></a>示例

SETF(GETREF(PinX),5.1) 
  
将 PinX 单元格的公式设置为 5.1。 
  

