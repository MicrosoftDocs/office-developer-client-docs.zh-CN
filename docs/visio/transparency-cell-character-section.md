---
title: Transparency 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm50135
localization_priority: Normal
ms.assetid: ab835a1a-9e90-126e-279f-463882c48e93
description: 确定形状的某一范围文本颜色的透明度级别。
ms.openlocfilehash: 5914a061b1bba2173b338544b05abda8780ff164
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781541"
---
# <a name="transparency-cell-character-section"></a>Transparency 单元格（“Character”内容）

确定形状的某一范围文本颜色的透明度级别。
  
|**值**|**说明**|
|:-----|:-----|
|0-100  <br/> |表示透明度的百分比。默认值为 0%（完全不透明）。  <br/> |
   
## <a name="remarks"></a>注解

这些值被四舍五入为最接近的 0.5 个百分点。值 100% 是完全透明。虽然文本完全透明的形状在绘图页上看起来和没有文本的形状相同，但是它与该页上其他对象的交互方式与透明度为 0% 的形状相同。
  
您还可以通过使用**文本**对话框中的**字体**选项卡上的滑块控件设置此值 （在**主页**选项卡上，单击**字体**箭头）。 
  
如果“Characters”内容包含多行，则 Transparency 单元格包含应用于某形状文本的一个子范围的格式设置信息。否则，它就包含该形状的所有文本的格式设置信息。
  
若要获取对 Transparency 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Char.ColorTrans [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 Transparency 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionCharacter** <br/> |
|行索引：  <br/> |**visRowCharacter** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visCharacterColorTrans** <br/> |
   

