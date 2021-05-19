---
title: ISTHEMED 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 91cde601-dca9-4737-afe1-bdf76638dfe3
description: 返回一个 Boolean 值，该值指示形状是否应用了主题。
ms.openlocfilehash: 49f53eaaacbdc86a633703d6ef847e38097f5122
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418118"
---
# <a name="isthemed-function"></a>ISTHEMED 函数

返回一个 Boolean 值，该值指示形状是否应用了主题。 
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013
 
  
## <a name="syntax"></a>语法

 **ISTHEMED** () 
  
## <a name="return-value"></a>返回值

布尔值
  
## <a name="remarks"></a>备注

> [!NOTE]
> 2013 中的 **ISTHEMED** Visio替换以前版本的 **CELLISTHEMED** 函数Visio。 
  
**ISTHEMED** 函数允许您为形状分配主题格式的适当部分，但保留使用手动应用的格式覆盖主题格式的其他部分的功能。 如果随后重新应用该主题，则任何手动格式都将被覆盖，并且形状将采用所有主题的格式。 
  
 如果形状中的 [ColorSchemeIndex](colorschemeindex-cell-theme-properties-section.md)单元格大于 0，**则 ISTHEMED** 计算结果为 TRUE。 如果此单元格等于 0，则 **ISTHEMED** 计算结果为 FALSE。 DocumentSheet 和 PageSheet 的主题不会影响 ShapeSheet 中使用的 **ISTHEMED** 函数的值。 只有在 PageSheet 中显示 **ISTHEMED** 函数时，页面的主题才重要。 
  
## <a name="example"></a>示例

||||
|:-----|:-----|:-----|
|Cell  <br/> |公式  <br/> |结果  <br/> |
|Char.Font  <br/> |如果 (ISTHEMED () 、THEMEVAL () 、FONT ("Calibri") )   <br/> |如果形状应用了主题，则形状文本将接受主题中的字体格式。 如果形状未设置其颜色，则形状文本的格式为"Calibri"字体。  <br/> |
|LineColor  <br/> |如果 (ISTHEMED、RGB (255、0、0) 、RGB (0、255、0) )   <br/> |如果形状应用了一种颜色，则形状的线条颜色为红色。 如果形状未设置其颜色，则形状的线条颜色为绿色。  <br/> |
   

