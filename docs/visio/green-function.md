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
description: 返回颜色的绿色成分。
ms.openlocfilehash: 0412e4519c2964b05d7663805d7773e8dc5deaab
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438104"
---
# <a name="green-function"></a>GREEN 函数

返回颜色的绿色成分。
  
## <a name="syntax"></a>语法

绿色 (* **表达式** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**相同** <br/> |文档颜色表中颜色的索引、解析为自定义颜色的表达式 (如 RGB 或 HSL), 或者是对包含颜色索引或颜色结果的单元格的引用。  <br/> |
   
### <a name="return-value"></a>返回值

整数
  
## <a name="remarks"></a>说明

返回值是 0 至 255（包括 0 和 255）之间的数字，或解析为索引值的单元格引用。 如果*表达式*无效, 则返回 0 (黑色)。 
  
## <a name="example-1"></a>示例 1

绿色 (Sheet 4!FillForegnd
  
返回 Sheet.4 的填充前景色的绿色成分。
  
## <a name="example-2"></a>示例 2

绿色 (11)
  
如果文档使用默认的 Visio 调色板（其中深黄色是索引值为 11 的颜色），则返回 128。
  
## <a name="example-3"></a>示例 3

GREEN(RGB(10, 20, 30))
  
返回 20。
  

