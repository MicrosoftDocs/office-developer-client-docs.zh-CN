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
ms.openlocfilehash: 01e2da8ef1e97e8a911df605ab6cf1e9f8a853eb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420687"
---
# <a name="user-defined-cells-row-user-defined-cells-section"></a>User-defined Cells 行（“User-defined Cells”内容）

包含解决方案中所有用户定义的单元格的值和说明性提示。对于每个用户定义的值/提示单元格对，形状都包含一个与之对应的 User-defined Cells 行。
  
User-defined Cells 行被命名为 User. *名称*并包含以下单元格。 有关详细信息，请参阅特定的单元格主题。 
  
|**单元格**|**说明**|
|:-----|:-----|
|[值](value-cell-user-defined-cells-section.md) <br/> |为相应的用户定义的单元格指定值。  <br/> |
|[Prompt](prompt-cell-user-defined-cells-section.md) <br/> |为用户定义的单元格指定说明性提示或注释。  <br/> |
   
## <a name="remarks"></a>说明

用户定义的单元格可用于输入由其他单元格或加载项所引用的公式或常量。用户定义的单元格中的值是可移植的，也就是说，如果一个形状引用了某个形状中的用户定义的单元格，并且该形状被复制到另一个不含同一用户定义的单元格的形状中，则该单元格会被添加到另一个形状中。
  
 可以根据需要添加任意多的 User.  根据需要*命名*行, 为行分配有意义的名称, 并设置单元格的值。 若要向现有的“User-defined Cells”内容添加行，请右击某一行，然后单击快捷菜单上的 **“插入行”**。 
  
可以通过上述单元格的行名称来引用这些单元格，这些行名称在 ShapeSheet 窗口中显示为红色文本。 为用户分配有意义的名称。 *名称*行, 请单击该行, 然后键入一个名称 (例如*offset* ), 以创建行名称 User. offset。 然后, 可以使用 User. prompt 引用 prompt 单元格。 
  
您输入的行名称在该内容中必须是唯一的。
  

