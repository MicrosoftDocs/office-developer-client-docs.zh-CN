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
description: 返回颜色的蓝色部分。 返回值是 0 到 255 之间（含 0 和 255）的整数。 对于无效输入，该函数将返回 0。
ms.openlocfilehash: adefbe0f8c2df0ead0f3e50cd5d4945501972865
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439035"
---
# <a name="blue-function"></a>BLUE 函数

返回颜色的蓝色部分。 返回值是 0 到 255 之间（含 0 和 255）的整数。 对于无效输入，该函数将返回 0。
  
## <a name="syntax"></a>语法

BLUE (** *expression* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**String** <br/> |文档颜色表中某颜色的索引值、解析为自定义颜色的表达式（如 RGB 或 HSL），或者是对某个包含颜色索引值或颜色结果的单元格的引用。  <br/> |
   
### <a name="return-value"></a>返回值

整数
  
## <a name="example-1"></a>示例 1

BLUE (Sheet.4!FillForegnd) 
  
返回 Sheet.4 的填充前景色的蓝色成分。
  
## <a name="example-2"></a>示例 2

蓝色 (13) 
  
如果文档使用默认的 Visio 调色板（其中青色是索引值为 13 的颜色），则返回 128。
  
## <a name="example-3"></a>示例 3

BLUE(RGB(10, 20, 30))
  
返回 30。
  

