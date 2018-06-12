---
title: Hyperlink 行（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm3065
localization_priority: Normal
ms.assetid: e3c7ae27-2e54-a174-4fb3-d16093faf759
description: 包含与形状相关联的单个超链接的信息。对于每个超链接，形状中都将包含一个与之对应的 Hyperlink 行。
ms.openlocfilehash: 99295838f5d1860e3c34cf4e37866eb477fe81ad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780419"
---
# <a name="hyperlink-row-hyperlinks-section"></a>Hyperlink 行（“Hyperlinks”内容）

包含与形状相关联的单个超链接的信息。对于每个超链接，形状中都将包含一个与之对应的 Hyperlink 行。
  
超链接行被命名超链接。 *名称*，并且包含以下单元格。 有关详细信息，请参阅特定单元格主题。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[说明](description-cell-hyperlinks-section.md) <br/> |超链接的说明性文本字符串。  <br/> |
|[Address](address-cell-hyperlinks-section.md) <br/> |要跳转到的 URL 地址、MS-DOS 文件名或 UNC 路径。  <br/> |
|[SubAddress](subaddress-cell-hyperlinks-section.md) <br/> |要链接到的目标文档内的位置。  <br/> |
|[ExtraInfo](extrainfo-cell-hyperlinks-section.md) <br/> |传递解析 URL 时要使用的信息的字符串。  <br/> |
|[框架](frame-cell-hyperlinks-section.md) <br/> |Microsoft Office Visio 作为 ActiveX 容器中的活动文档打开时的目标框架名。默认值为空字符串。  <br/> |
|[SortKey](sortkey-cell-hyperlinks-section.md) <br/> |确定超链接在快捷菜单上的显示顺序。  <br/> |
|[NewWindow](newwindow-cell-hyperlinks-section.md) <br/> |指定是否在新窗口中打开超链接。如果为 TRUE，则在新窗口中打开链接的页、文档或网站。默认值是 FALSE。  <br/> |
|[Default](default-cell-hyperlinks-section.md) <br/> |形状或页的默认超链接。  <br/> |
|[不可见](invisible-cell-hyperlinks-section.md) <br/> |指示超链接是否出现在快捷菜单上。  <br/> |
   
## <a name="remarks"></a>注解

 您可以添加任意多个超链接。  *名称*行根据需要为这些行中，指定有意义的名称，并设置单元格的值。 将超链接添加到现有的 Hyperlinks 内容中，右击某一行，然后单击快捷菜单上的**插入行**。 
  
可通过，这些行名称在 ShapeSheet 窗口中显示为红色文本来引用这些单元格。 分配给超链接的有意义的名称。 *名称*行中，单击行，，然后键入名称，例如*市场营销*，例如，创建行名称指定有。 然后，可以引用使用 Hyperlink.Marketing.Description Description 单元格。 
  
您输入的行名称在该内容中必须是唯一的。
  

