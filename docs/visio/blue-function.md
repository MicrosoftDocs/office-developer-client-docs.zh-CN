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
description: 返回一种颜色的蓝色成分。 返回值是整数，范围为 0 到 255。 此函数返回无效输入的 0。
ms.openlocfilehash: 6a86a0ee91054c89f2def95c0e3521508462bdaa
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779776"
---
# <a name="blue-function"></a>BLUE 函数

返回一种颜色的蓝色成分。 返回值是整数，范围为 0 到 255。 此函数返回无效输入的 0。
  
## <a name="syntax"></a>语法

蓝色 (* **表达式** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**字符串** <br/> |文档颜色表中某颜色的索引值、解析为自定义颜色的表达式（如 RGB 或 HSL），或者是对某个包含颜色索引值或颜色结果的单元格的引用。  <br/> |
   
### <a name="return-value"></a>返回值

Integer
  
## <a name="example-1"></a>示例 1

蓝色 (Sheet.4 ！FillForegnd)
  
返回 Sheet.4 的填充前景色的蓝色成分。
  
## <a name="example-2"></a>示例 2

BLUE(13)
  
如果文档使用默认的 Visio 调色板（其中青色是索引值为 13 的颜色），则返回 128。
  
## <a name="example-3"></a>示例 3

BLUE(RGB(10, 20, 30))
  
返回 30。
  

