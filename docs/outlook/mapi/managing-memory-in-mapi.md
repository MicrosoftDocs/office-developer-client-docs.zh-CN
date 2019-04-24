---
title: 管理 MAPI 中的内存
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9eee6925-ab91-413e-8907-c747ab4a4bb5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 66489c09be641d8fe9ae5f3ffff46a6d5004f473
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32298094"
---
# <a name="managing-memory-in-mapi"></a>管理 MAPI 中的内存

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
了解如何以及何时分配和释放内存是使用 MAPI 编程的重要部分。 MAPI 提供了功能和宏, 客户端或服务提供商可以使用它们以一致的方式管理内存。 这三个函数如下所示:
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
当客户端和服务提供商使用这些功能时, 有权 "拥有" 的问题 (即知道如何释放) 将消除特定的内存块。 调用服务提供程序方法的客户端无需传递足够大的缓冲区以容纳任意大小的返回值。 服务提供程序可以简单地使用**MAPIAllocateBuffer**分配适当的内存量, 并在必要时**MAPIAllocateMore**, 并且客户端可以在以后使用**MAPIFreeBuffer**, 而不依赖于服务provider. 
  
内存宏用于分配特定大小的结构或结构数组。 客户端和服务提供商应使用这些宏, 而不是手动分配内存。 例如, 如果客户端需要在具有三个条目的收件人列表中执行名称解析处理, 则可以使用**SizedADRLIST**宏创建**ADRLIST**结构, 以将结构传递给**IAddrBook:: ResolveName**的正确数量的**ADRENTRY**成员。 所有内存宏都在 mapidefs.h 中进行了定义。H 头文件。 这些宏为: 
  
|||
|:-----|:-----|
|[SizedADRLIST](sizedadrlist.md) <br/> |[SizedDtblPage](sizeddtblpage.md) <br/> |
|[SizedDtblButton](sizeddtblbutton.md) <br/> |[SizedENTRYID](sizedentryid.md) <br/> |
|[SizedDtblCheckBox](sizeddtblcheckbox.md) <br/> |[SizedSPropProblemArray](sizedspropproblemarray.md) <br/> |
|[SizedDtblComboBox](sizeddtblcombobox.md) <br/> |[SizedSPropTagArray](sizedsproptagarray.md) <br/> |
|[SizedDtblEdit](sizeddtbledit.md) <br/> |[SizedSRowSet](sizedsrowset.md) <br/> |
|[SizedDtblGroupBox](sizeddtblgroupbox.md) <br/> |[SizedSSortOrderSet](sizedssortorderset.md) <br/> |
|[SizedDtblLabel](sizeddtbllabel.md) <br/> | <br/> |
   
MAPI 还支持使用 COM 接口[IMalloc](https://msdn.microsoft.com/library/ms678425%28VS.85%29.aspx)进行内存管理。 服务提供程序在初始化时为 MAPI 提供**IMalloc**接口指针, 还可以通过[MAPIGetDefaultMalloc](mapigetdefaultmalloc.md)函数检索一个接口指针。 使用**IMalloc**方法来通过 MAPI 函数管理内存的主要优势在于, 使用 COM 方法可以重新分配现有缓冲区。 MAPI 内存函数不支持重新分配。 
  

