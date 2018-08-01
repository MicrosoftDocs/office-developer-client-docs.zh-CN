---
title: GREEN 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251434
localization_priority: Normal
ms.assetid: eccec432-32d3-15c2-06b3-dd02b6313d4c
description: 返回一种颜色的绿色成分。
ms.openlocfilehash: 04bdadc0fa34dc4f51061d428b9366a433b669a5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780387"
---
# <a name="green-function"></a>GREEN 函数

返回一种颜色的绿色成分。
  
## <a name="syntax"></a>语法

绿色 (* **表达式** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**因情况而异** <br/> |文档颜色表，将解析为自定义颜色 （如 RGB 或 HSL） 或对包含颜色索引或颜色结果的单元格的引用的表达式中的颜色索引。  <br/> |
   
### <a name="return-value"></a>返回值

Integer
  
## <a name="remarks"></a>说明

返回值是 0 到 255，包括的数字或解析为索引的单元格引用。 如果*表达式*无效，则返回 0 （黑色）。 
  
## <a name="example-1"></a>示例 1

绿色 (Sheet.4 ！FillForegnd)
  
返回 Sheet.4 的填充前景色的绿色成分。
  
## <a name="example-2"></a>示例 2

GREEN(11)
  
如果文档使用默认的 Visio 调色板（其中深黄色是索引值为 11 的颜色），则返回 128。
  
## <a name="example-3"></a>示例 3

GREEN(RGB(10, 20, 30))
  
返回 20。
  

