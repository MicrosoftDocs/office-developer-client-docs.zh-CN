---
title: RED 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251487
localization_priority: Normal
ms.assetid: a95fd86d-ebc1-66b6-e7d9-9c8ea84d23ab
description: 返回一种颜色的红色成分。
ms.openlocfilehash: 801ebb64564df81f72c41cb720fe53f0f1b4c10d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19781015"
---
# <a name="red-function"></a>RED 函数

返回一种颜色的红色成分。 
  
## <a name="syntax"></a>语法

红色 (* **表达式** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**因情况而异** <br/> |文档颜色表中某颜色的索引值、解析为自定义颜色的表达式（如 RGB 或 HSL），或者是对某个包含颜色索引值或颜色结果的单元格的引用。  <br/> |
   
### <a name="return-value"></a>返回值

Number
  
## <a name="remarks"></a>说明

返回值是 0 到 255，包括的数字或解析为索引的单元格引用。 如果_表达式_无效，本函数将返回 0 （黑色）。 
  
## <a name="example-1"></a>示例 1

RED(22)
  
如果文档使用默认的 Microsoft Office Visio 调色板，其中深灰色是索引值为 22 的颜色，则返回 51。
  
## <a name="example-2"></a>示例 2

RED(Char.Color)
  
返回当前字体颜色的红色成分值。
  
## <a name="example-3"></a>示例 3

RED(RGB(10, 20, 30))
  
返回 10。
  

