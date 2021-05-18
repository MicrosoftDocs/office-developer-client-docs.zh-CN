---
title: Smart Tags 行（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1026926
localization_priority: Normal
ms.assetid: 065c6977-c737-a4f4-effa-0fd2c98e8bbf
description: 包含与形状或页相关联的单个动作标记的信息。 对于每个动作标记，形状或页均包含一个与之对应的 Smart Tags 行。
ms.openlocfilehash: 1c1591fd2d2cacfbfb350a542e6601cb2f6fbfd6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404706"
---
# <a name="smart-tags-row-action-tags-section"></a>Smart Tags 行（“Action Tags”内容）

包含与形状或页相关联的单个动作标记的信息。 对于每个动作标记，形状或页均包含一个与之对应的 Smart Tags 行。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
Smart Tags 行被命名为 SmartTags. *name*  并包含以下单元格。 有关详细信息，请参阅特定的单元格主题。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[X](x-cell-action-tags-section.md) <br/> |形状的本地坐标中放置动作标记按钮的点的  *x*  坐标位置。  <br/> |
|[Y](y-cell-action-tags-section.md) <br/> |形状的本地坐标中放置动作标记按钮的点的  *y*  坐标位置。  <br/> |
|[TagName](tagname-cell-action-tags-section.md) <br/> |动作标记的逻辑名称。  <br/> |
|[X Justify](x-justify-cell-action-tags-section.md) <br/> |动作  *标记*  按钮相对于 X 单元格和 Y 单元格定义的点的 x 偏移量。  <br/> |
|[Y Justify](y-justify-cell-action-tags-section.md) <br/> |动作标记按钮相对于 X 和 Y 单元格定义的点的  *y*  偏移量。  <br/> |
|[DisplayMode](displaymode-cell-action-tags-section.md) <br/> |确定何时将显示动作标记。  <br/> |
|[ButtonFace](buttonface-cell-action-tags-section.md) <br/> |显示在动作标记按钮表面的图像的 ID。  <br/> |
|[说明](description-cell-action-tags-section.md) <br/> |动作标记的说明性字符串。  <br/> |
|[Disabled](disabled-cell-action-tags-section.md) <br/> |指示是否禁用动作标记。  <br/> |
   
## <a name="remarks"></a>备注

 可以根据需要添加任意多的 SmartTags.  *命名*  行（如需要）为行指定有意义的名称，并设置单元格值。 若要向现有的“Smart Tags”内容添加动作标记，请右键单击某一行，然后单击快捷菜单上的 **“插入行”**。 
  
可以通过上述单元格的行名称来引用这些单元格，这些行名称在 ShapeSheet 窗口中显示为红色文本。 为智能标记分配有意义的名称。 *name*  rows， click the row， and then type a name such as  *Size*  ， for example， to create the row name Smart Tags.Size. 然后，您可以使用 Smart Tags.Size.Description 引用 Description 单元格。 
  
您输入的行名称在该内容中必须是唯一的。
  

