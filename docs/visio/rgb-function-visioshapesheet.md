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
description: 返回一个值，该值代表文档的调色板中的索引。 它通过红色、绿色和蓝色分量指定颜色，其中每个颜色都是 0 到 255 之间的一个数字（包含这两者）或计算结果为此类数字的表达式。
ms.openlocfilehash: 34f9c2f2043afe6144feba561e545dc7be35a5a2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426301"
---
# <a name="rgb-function-visioshapesheet"></a>RGB 函数 (VisioShapeSheet)

返回一个值，该值代表文档的调色板中的索引。 它通过红色、绿色和蓝色分量指定颜色，其中每个颜色都是 0 到 255 之间的一个数字（包含这两者）或计算结果为此类数字的表达式。 
  
## <a name="syntax"></a>语法

RGB (** *red* **， ** *green* **， ** *blue* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _red_ <br/> |必需  <br/> |**Number** <br/> |红色成分。  <br/> |
| _绿色_ <br/> |必需  <br/> |**Number** <br/> |绿色成分。  <br/> |
| _blue_ <br/> |必需  <br/> |**nmber** <br/> |蓝色成分。  <br/> |
   
### <a name="return-value"></a>返回值

帐号
  
## <a name="remarks"></a>备注

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

RGB (0，0，255) 
  
返回蓝色的索引值。
  
## <a name="example-2"></a>示例 2

RGB (RED (Sheet.1！FillForegnd) ，120，0) 
  
返回一种颜色的索引值，它的红成分匹配 Sheet.1 的填充前景色。
  

