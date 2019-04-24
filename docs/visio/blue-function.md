---
title: BLUE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251402
localization_priority: Normal
ms.assetid: da9fb933-4e2c-3e2a-1879-6e70db0cd830
description: 返回颜色的蓝色成分。 返回值是介于0到 255 (含) 之间的整数。 对于无效输入，该函数将返回 0。
ms.openlocfilehash: adefbe0f8c2df0ead0f3e50cd5d4945501972865
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297352"
---
# <a name="blue-function"></a>BLUE 函数

返回颜色的蓝色成分。 返回值是介于0到 255 (含) 之间的整数。 对于无效输入，该函数将返回 0。
  
## <a name="syntax"></a>语法

蓝色 (* **表达式** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**String** <br/> |文档颜色表中某颜色的索引值、解析为自定义颜色的表达式（如 RGB 或 HSL），或者是对某个包含颜色索引值或颜色结果的单元格的引用。  <br/> |
   
### <a name="return-value"></a>返回值

整数
  
## <a name="example-1"></a>示例 1

蓝色 (Sheet 4!FillForegnd
  
返回 Sheet.4 的填充前景色的蓝色成分。
  
## <a name="example-2"></a>示例 2

蓝色 (13)
  
如果文档使用默认的 Visio 调色板（其中青色是索引值为 13 的颜色），则返回 128。
  
## <a name="example-3"></a>示例 3

BLUE(RGB(10, 20, 30))
  
返回 30。
  

