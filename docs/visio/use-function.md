---
title: USE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251510
localization_priority: Normal
ms.assetid: 410c4187-21f3-d959-750e-9dc6095fba9a
description: 适用的线型、 填充图案或线端调用到形状时处于 LinePattern、 FillPattern、 BeginArrow 或 EndArrow 单元格的名称。
ms.openlocfilehash: 0b6668e57a8f997a69fece51cbc5bd1b1574a576
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781601"
---
# <a name="use-function"></a>USE 函数

适用的线型、 填充图案或线端调用到形状时处于 LinePattern、 FillPattern、 BeginArrow 或 EndArrow 单元格的_名称_。 
  
## <a name="syntax"></a>语法

使用 ("* **名称** *") 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _name_ <br/> |必需  <br/> |**字符串** <br/> |是有效主控形状名称的任何字符串。  <br/> |
   
### <a name="return-value"></a>返回值

Number
  
## <a name="remarks"></a>注解

如果文档的文档模具上存在名为_name_的主控形状，如线型、 填充图案、 开始箭头或结束箭头应用模式。 
  
此函数始终返回 254。
  
## <a name="example"></a>示例

USE("Railroad Tracks") 
  
通过对包含该公式的形状应用名为 Railroad Tracks 的主控形状图案，设置该形状的格式。 
  

