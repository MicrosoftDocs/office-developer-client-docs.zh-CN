---
title: SAT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251494
localization_priority: Normal
ms.assetid: 407817fb-9e4a-d2ca-6125-2440d2a417c6
description: 返回颜色饱和度组件的值。
ms.openlocfilehash: 54f3fa68c567c2a32e8cfd37c406387cd6973ce3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781214"
---
# <a name="sat-function"></a>SAT 函数

返回颜色饱和度组件的值。 
  
## <a name="syntax"></a>语法

SAT (* **表达式** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**而异** <br/> |文档颜色表中某颜色的索引值、解析为自定义颜色的表达式（如 RGB 或 HSL），或者是对某个包含颜色索引值或颜色结果的单元格的引用。  <br/> |
   
### <a name="return-value"></a>返回值

Numeric
  
## <a name="remarks"></a>注解

返回值是 0 至 240 之间的数字（包括 0 和 240）。对于无效输入，该函数将返回 0。
  
## <a name="example-1"></a>示例 1

SAT (Sheet.4 ！FillForegnd)
  
返回 Sheet.4 的填充前景色的饱和度。
  
## <a name="example-2"></a>示例 2

SAT(8)
  
如果文档使用默认的 Visio 调色板，其中深红色的索引值是 8，则返回 240。
  
## <a name="example-3"></a>示例 3

SAT(HSL(10, 20, 30))
  
返回 20。
  

