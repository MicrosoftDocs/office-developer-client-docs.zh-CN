---
title: HUE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251440
localization_priority: Normal
ms.assetid: 0f5c6097-eef5-5f58-e2ef-2c348e42dc9a
description: 返回颜色色调组件的值。
ms.openlocfilehash: 39fdd160f5cd792e95930a3e7c7cea3c37ed16c1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439490"
---
# <a name="hue-function"></a>HUE 函数

返回颜色色调组件的值。
  
## <a name="syntax"></a>语法

色相 (* **表达式** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**String** <br/> |一个计算结果为某种颜色的表达式。  <br/> |
   
### <a name="return-value"></a>返回值

数字
  
## <a name="remarks"></a>说明

返回值是 0 至 239 之间的数字（包括 0 和 239）。输入内容为文档颜色表中某颜色的索引值、解析为自定义颜色的表达式（如 RGB 或 HSL），或者是对某个包含颜色索引值或颜色结果的单元格的引用。对于无效输入，该函数将返回 0。 
  
## <a name="example-1"></a>示例 1

色相 (Sheet. 4!FillForegnd
  
返回 Sheet.4 的填充前景色的色调。
  
## <a name="example-2"></a>示例 2

色相 (7)
  
如果文档使用默认的 Microsoft Visio 调色板，其中青色是索引值为 7 的颜色，则返回 120。
  
## <a name="example-3"></a>示例 3

HUE(HSL(10, 20, 30) )
  
返回 10。
  

