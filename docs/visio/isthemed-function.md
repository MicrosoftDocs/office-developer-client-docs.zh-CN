---
title: ISTHEMED 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 91cde601-dca9-4737-afe1-bdf76638dfe3
description: 返回一个布尔值, 该值指示是否对形状应用了主题。
ms.openlocfilehash: 49f53eaaacbdc86a633703d6ef847e38097f5122
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418118"
---
# <a name="isthemed-function"></a>ISTHEMED 函数

返回一个布尔值, 该值指示是否对形状应用了主题。 
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013
 
  
## <a name="syntax"></a>语法

 **ISTHEMED**()
  
## <a name="return-value"></a>返回值

布尔值
  
## <a name="remarks"></a>备注

> [!NOTE]
> visio 2013 中的**ISTHEMED**函数将替换以前版本的 visio 中的**CELLISTHEMED**函数。 
  
**ISTHEMED**函数允许您将主题格式的相应部分分配给形状, 但仍可以使用手动应用的格式替代主题格式设置的其他部分。 如果您随后重新应用主题, 则任何手动的格式都将被覆盖, 并且形状将采用主题的所有格式。 
  
 如果形状中的[ColorSchemeIndex](colorschemeindex-cell-theme-properties-section.md)单元格大于 0, 则**ISTHEMED**的计算结果为 TRUE。 如果此单元格等于 0, 则**ISTHEMED**的计算结果为 FALSE。 DocumentSheet 和 PageSheet 的主题不会影响 ShapeSheet 中使用的**ISTHEMED**函数的值。 仅当**ISTHEMED**函数在 PageSheet 中显示时, 才会执行页面的主题事务。 
  
## <a name="example"></a>示例

||||
|:-----|:-----|:-----|
|Cell  <br/> |公式  <br/> |结果  <br/> |
|字符。字体  <br/> |IF (ISTHEMED ()、THEMEVAL () 和 FONT ("Calibri"))  <br/> |如果形状应用了主题, 则形状文本接受主题中的字体格式。 如果形状没有主题, 则形状文本的格式为 "Calibri" 字体。  <br/> |
|LineColor  <br/> |IF (ISTHEMED, rgb (255, 0, 0), RGB (0, 255, 0))  <br/> |如果形状应用了主题, 则该形状的线条颜色为红色。 如果形状没有主题, 则形状的线条颜色为绿色。  <br/> |
   

