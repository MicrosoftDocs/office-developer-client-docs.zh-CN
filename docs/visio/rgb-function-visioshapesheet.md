---
title: RGB 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251489
localization_priority: Normal
ms.assetid: f6b9f65c-6752-16cb-7eb1-44e1ce56e80b
description: 返回一个值, 该值代表文档调色板中的索引。 它通过它的红色、绿色和蓝色分量指定颜色, 其中每个是范围为0到 255 (含) 的数字, 或者是计算结果为此类数字的表达式。
ms.openlocfilehash: 34f9c2f2043afe6144feba561e545dc7be35a5a2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326738"
---
# <a name="rgb-function-visioshapesheet"></a>RGB 函数 (VisioShapeSheet)

返回一个值, 该值代表文档调色板中的索引。 它通过它的红色、绿色和蓝色分量指定颜色, 其中每个是范围为0到 255 (含) 的数字, 或者是计算结果为此类数字的表达式。 
  
## <a name="syntax"></a>语法

RGB (* * *red* * *、* **绿色** *、* **蓝** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _表示_ <br/> |必需  <br/> |**Number** <br/> |红色成分。  <br/> |
| _表示_ <br/> |必需  <br/> |**Number** <br/> |绿色成分。  <br/> |
| _变为_ <br/> |必需  <br/> |**Nmber** <br/> |蓝色成分。  <br/> |
   
### <a name="return-value"></a>返回值

帐号
  
## <a name="remarks"></a>注解

如果由该函数返回的颜色在当前文档的调色板中尚不存在，则它将添加到调色板中。
  
下表列出了一些标准颜色，以及它们的红、绿和蓝值。
  
|**Color**|**红值**|**绿值**|**蓝值**|
|:-----|:-----|:-----|:-----|
|黑色  <br/> |0  <br/> |0  <br/> |0  <br/> |
|蓝色  <br/> |0  <br/> |0  <br/> |255  <br/> |
|绿色  <br/> |0  <br/> |255  <br/> |0  <br/> |
|蓝绿  <br/> |0  <br/> |255  <br/> |255  <br/> |
|红色  <br/> |255  <br/> |0  <br/> |0  <br/> |
|洋红  <br/> |255  <br/> |0  <br/> |255  <br/> |
|黄色  <br/> |255  <br/> |255  <br/> |0  <br/> |
|白色  <br/> |255  <br/> |255  <br/> |255  <br/> |
   
## <a name="example-1"></a>示例 1

RGB (0, 0255)
  
返回蓝色的索引值。
  
## <a name="example-2"></a>示例 2

RGB (RED (Sheet. 1!FillForegnd)、120、0)
  
返回一种颜色的索引值，它的红成分匹配 Sheet.1 的填充前景色。
  

