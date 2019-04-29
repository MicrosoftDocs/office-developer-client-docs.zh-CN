---
title: LUM 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251460
localization_priority: Normal
ms.assetid: 38e6bba7-1bf2-3d31-0912-707002454f5d
description: 返回颜色发光度组件的值。
ms.openlocfilehash: 17fa43f8e2cd7422428f92724e351436233c2d62
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419336"
---
# <a name="lum-function"></a>LUM 函数

返回颜色发光度组件的值。
  
## <a name="syntax"></a>语法

亮度 (* **表达式** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**数值** <br/> |文档颜色表中的颜色索引值，或对包含颜色索引值的某单元格的引用。  <br/> |
   
### <a name="return-value"></a>返回值

数字
  
## <a name="remarks"></a>说明

返回值是 0 至 240 之间的数字（包括 0 和 240）。对于无效输入，该函数将返回 0。 
  
## <a name="example-1"></a>示例 1

亮度 (Sheet. 4!FillForegnd
  
返回 Sheet.4 的填充前景色的发光度。
  
## <a name="example-2"></a>示例 2

亮度 (6)
  
如果文档使用默认的 Visio 调色板，其中洋红是索引值为 6 的颜色，则返回 120。
  
## <a name="example-3"></a>示例 3

LUM(HSL(10, 20, 30))
  
返回 30。
  

