---
title: User-defined Cells 行（“User-defined Cells”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm3060
localization_priority: Normal
ms.assetid: 6c48b9b3-5c62-7d5a-1c8f-fe96606f4dea
description: 包含解决方案中所有用户定义的单元格的值和说明性提示。对于每个用户定义的值/提示单元格对，形状都包含一个与之对应的 User-defined Cells 行。
ms.openlocfilehash: 45a9a033fe486a14e9881c3d79b79a129ecedc1f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781600"
---
# <a name="user-defined-cells-row-user-defined-cells-section"></a>User-defined Cells 行（“User-defined Cells”内容）

包含解决方案中所有用户定义的单元格的值和说明性提示。对于每个用户定义的值/提示单元格对，形状都包含一个与之对应的 User-defined Cells 行。
  
用户定义的单元格行名用户。 *名称*，并且包含以下单元格。 有关详细信息，请参阅特定单元格主题。 
  
|**Cell**|**说明**|
|:-----|:-----|
|[Value](value-cell-user-defined-cells-section.md) <br/> |为相应的用户定义的单元格指定值。  <br/> |
|[Prompt](prompt-cell-user-defined-cells-section.md) <br/> |为用户定义的单元格指定说明性提示或注释。  <br/> |
   
## <a name="remarks"></a>注解

用户定义的单元格可用于输入由其他单元格或加载项所引用的公式或常量。用户定义的单元格中的值是可移植的，也就是说，如果一个形状引用了某个形状中的用户定义的单元格，并且该形状被复制到另一个不含同一用户定义的单元格的形状中，则该单元格会被添加到另一个形状中。
  
 您可以添加任意多个用户。  *名称*行根据需要为这些行中，指定有意义的名称，并设置单元格的值。 要将行添加到现有的用户定义的单元格部分，右击某一行，然后单击快捷菜单上的**插入行**。 
  
可通过，这些行名称在 ShapeSheet 窗口中显示为红色文本来引用这些单元格。 为用户分配有意义的名称。 *名称*行中，单击该行，，然后键入名称，例如*偏移*，例如，创建行名称指定有。 然后，可以引用使用 User.Offset.Prompt Prompt 单元格。 
  
您输入的行名称在该内容中必须是唯一的。
  

