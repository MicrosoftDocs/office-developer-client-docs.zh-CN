---
title: ISTHEMED 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 91cde601-dca9-4737-afe1-bdf76638dfe3
description: 返回一个 Boolean 值，该值形状是否含有向其应用了主题。
ms.openlocfilehash: 4311780d8686b5792e999c204ec182d23efb723c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780515"
---
# <a name="isthemed-function"></a>ISTHEMED 函数

返回一个 Boolean 值，该值形状是否含有向其应用了主题。 
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2013
 
  
## <a name="syntax"></a>语法

 **ISTHEMED**()
  
## <a name="return-value"></a>返回值

Boolean
  
## <a name="remarks"></a>说明

> [!NOTE]
> Visio 2013 中的**ISTHEMED**函数替换为从早期版本的 Visio **CELLISTHEMED**函数。 
  
**ISTHEMED**函数，可以向形状分配相应部分的主题格式，但保留重写该主题的格式与手动应用格式的其他部分的能力。 如果您随后重新应用主题，任何手动格式将被覆盖并形状承担的所有主题的格式。 
  
 **ISTHEMED**计算结果为形状中的[ColorSchemeIndex](colorschemeindex-cell-theme-properties-section.md)单元格为大于 0 时为 TRUE。 如果此单元格等于 0，然后**ISTHEMED**计算结果为 FALSE。 主题的 DocumentSheet 和 PageSheet 不会影响在 ShapeSheet 中使用**ISTHEMED**函数的值。 仅当**ISTHEMED**函数中显示 PageSheet 执行的页面的主题专家。 
  
## <a name="example"></a>示例

||||
|:-----|:-----|:-----|
|单元格  <br/> |公式  <br/> |结果  <br/> |
|Char.Font  <br/> |IF(ISTHEMED()，THEMEVAL()，FONT("Calibri"))  <br/> |如果应用了主题应用于该形状，形状文本接受的字体格式设置的主题。 如果形状不是应用了主题，"宋体"字体格式形状文本。  <br/> |
|LineColor  <br/> |如果 (ISTHEMED，RGB （255，0，0）、 RGB （0、 255，0）)  <br/> |如果应用了主题应用于该形状，该形状的线条颜色为红色。 如果形状不是应用了主题的该形状的线条颜色为绿色。  <br/> |
   

