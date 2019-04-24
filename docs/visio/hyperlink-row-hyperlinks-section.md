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
description: 包含与形状相关联的单个超链接的信息。 对于每个超链接，形状中都将包含一个与之对应的 Hyperlink 行。
ms.openlocfilehash: 36b9b62f248e4f5b9407156a79fa674dc2e8f14d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329902"
---
# <a name="hyperlink-row-hyperlinks-section"></a>Hyperlink 行（“Hyperlinks”内容）

包含与形状相关联的单个超链接的信息。 对于每个超链接，形状中都将包含一个与之对应的 Hyperlink 行。
  
Hyperlink 行被命名为 Hyperlink. *名称*并包含以下单元格。 有关详细信息，请参阅特定的单元格主题。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[说明](description-cell-hyperlinks-section.md) <br/> |超链接的说明性文本字符串。  <br/> |
|[Address](address-cell-hyperlinks-section.md) <br/> |要跳转到的 URL 地址、MS-DOS 文件名或 UNC 路径。  <br/> |
|[SubAddress](subaddress-cell-hyperlinks-section.md) <br/> |要链接到的目标文档内的位置。  <br/> |
|[ExtraInfo](extrainfo-cell-hyperlinks-section.md) <br/> |传递解析 URL 时要使用的信息的字符串。  <br/> |
|[Frame](frame-cell-hyperlinks-section.md) <br/> |Microsoft Office Visio 作为 ActiveX 容器中的活动文档打开时的目标框架名。默认值为空字符串。  <br/> |
|[关键字](sortkey-cell-hyperlinks-section.md) <br/> |确定超链接在快捷菜单上的显示顺序。  <br/> |
|[NewWindow](newwindow-cell-hyperlinks-section.md) <br/> |指定是否在新窗口中打开超链接。 如果为 TRUE, 则在新窗口中打开链接的页面、文档或网站。 默认值是 FALSE。  <br/> |
|[Default](default-cell-hyperlinks-section.md) <br/> |形状或页的默认超链接。  <br/> |
|[隐藏](invisible-cell-hyperlinks-section.md) <br/> |指示超链接是否出现在快捷菜单上。  <br/> |
   
## <a name="remarks"></a>注解

 可以根据需要添加任意多的 Hyperlink.  根据需要*命名*行, 为行分配有意义的名称, 并设置单元格的值。 若要向现有的“Hyperlinks”内容添加超链接，请右击某一行，然后单击快捷菜单上的 **“插入行”**。 
  
可以通过上述单元格的行名称来引用这些单元格，这些行名称在 ShapeSheet 窗口中显示为红色文本。 为超链接指定有意义的名称。 *名称*行, 请单击该行, 然后键入一个名称 (例如 "*营销*"), 以创建行名称超链接。营销。 然后, 您可以使用超链接 (Marketing) 引用 Description 单元格。 
  
您输入的行名称在该内容中必须是唯一的。
  

