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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388068"
---
# <a name="managing-memory-in-mapi"></a>管理 MAPI 中的内存

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
了解如何以及何时以分配和释放内存是使用 MAPI 编程的重要组成部分。 MAPI 提供功能和宏的客户端或服务提供程序可用于管理内存中以一致方式。 三个函数，如下所示：
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
客户端和服务提供商时使用这些功能，该问题的"所有者"— 即，知道如何释放 — 去掉了特定块的内存。 调用服务提供程序方法的客户端需要传递足以容纳任何大小的返回值的缓冲区。 服务提供程序只可以分配适当的使用**MAPIAllocateBuffer**的内存量和，如有必要， **MAPIAllocateMore**和客户端可以更高版本释放其在将使用**MAPIFreeBuffer**，独立的服务提供程序。 
  
内存宏用于分配结构或结构特定大小的数组。 客户端和服务提供商应使用这些宏而不是手动分配内存。 例如，如果客户端需要执行处理上具有三个项的收件人列表的名称解析， **SizedADRLIST**宏可用于创建要与正确的数传递给**IAddrBook::ResolveName** **ADRLIST**结构**ADRENTRY**成员。 所有内存宏 MAPIDEFS 中定义。H 头文件。 这些宏是： 
  
|||
|:-----|:-----|
|[SizedADRLIST](sizedadrlist.md) <br/> |[SizedDtblPage](sizeddtblpage.md) <br/> |
|[SizedDtblButton](sizeddtblbutton.md) <br/> |[SizedENTRYID](sizedentryid.md) <br/> |
|[SizedDtblCheckBox](sizeddtblcheckbox.md) <br/> |[SizedSPropProblemArray](sizedspropproblemarray.md) <br/> |
|[SizedDtblComboBox](sizeddtblcombobox.md) <br/> |[SizedSPropTagArray](sizedsproptagarray.md) <br/> |
|[SizedDtblEdit](sizeddtbledit.md) <br/> |[SizedSRowSet](sizedsrowset.md) <br/> |
|[SizedDtblGroupBox](sizeddtblgroupbox.md) <br/> |[SizedSSortOrderSet](sizedssortorderset.md) <br/> |
|[SizedDtblLabel](sizeddtbllabel.md) <br/> | <br/> |
   
MAPI 还支持[IMalloc](https://msdn.microsoft.com/library/ms678425%28VS.85%29.aspx)的 COM 接口使用的内存管理。 服务提供商在初始化时通过 MAPI 授予**IMalloc**接口指针和还可以检索一星到[MAPIGetDefaultMalloc](mapigetdefaultmalloc.md)函数。 用于通过 MAPI 函数管理内存使用**IMalloc**方法的主要优点是，使用 COM 方法就可以重新分配现有缓冲区。 MAPI 内存函数不支持重新分配。 
  

