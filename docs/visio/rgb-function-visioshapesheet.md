---
title: RGB Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251489
localization_priority: Normal
ms.assetid: f6b9f65c-6752-16cb-7eb1-44e1ce56e80b
description: 返回一个值，表示在文档的调色板中的索引。 指定一种颜色由其红色、 绿色和蓝色的组件，其中每个是 0 到 255，包括中, 号或计算出此类数值的表达式。
ms.openlocfilehash: 7fa129d3ed28441f619660ed0db035cde85979bf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781102"
---
# <a name="rgb-function-visioshapesheet"></a>RGB Function (VisioShapeSheet)

返回一个值，表示在文档的调色板中的索引。 指定一种颜色由其红色、 绿色和蓝色的组件，其中每个是 0 到 255，包括中, 号或计算出此类数值的表达式。 
  
## <a name="syntax"></a>语法

RGB (* **红色** *，* **绿色** *，* **蓝色** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _红色_ <br/> |必需  <br/> |**编号** <br/> |红色成分。  <br/> |
| _绿色_ <br/> |必需  <br/> |**编号** <br/> |绿色成分。  <br/> |
| _蓝色_ <br/> |必需  <br/> |**Number** <br/> |蓝色成分。  <br/> |
   
### <a name="return-value"></a>返回值

Number
  
## <a name="remarks"></a>注解

如果由该函数返回的颜色在当前文档的调色板中尚不存在，则它将添加到调色板中。
  
下表列出了一些标准颜色，以及它们的红、绿和蓝值。
  
|**颜色**|**红色值**|**绿色值**|**蓝值**|
|:-----|:-----|:-----|:-----|
|黑色  <br/> |0  <br/> |0  <br/> |0  <br/> |
|蓝色  <br/> |0  <br/> |0  <br/> |255  <br/> |
|绿色  <br/> |0  <br/> |255  <br/> |0  <br/> |
|蓝绿色  <br/> |0  <br/> |255  <br/> |255  <br/> |
|红色  <br/> |255  <br/> |0  <br/> |0  <br/> |
|洋红色  <br/> |255  <br/> |0  <br/> |255  <br/> |
|黄色  <br/> |255  <br/> |255  <br/> |0  <br/> |
|白色  <br/> |255  <br/> |255  <br/> |255  <br/> |
   
## <a name="example-1"></a>示例 1

RGB(0,0,255)
  
返回蓝色的索引值。
  
## <a name="example-2"></a>示例 2

RGB （红 (Sheet.1 ！FillForegnd)，120、 0)
  
返回一种颜色的索引值，它的红成分匹配 Sheet.1 的填充前景色。
  

