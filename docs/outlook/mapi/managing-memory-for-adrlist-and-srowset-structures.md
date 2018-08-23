---
title: 管理 ADRLIST 和 SRowSet 结构的内存
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d009f6b6-d151-4d52-b7cc-a15127142354
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ef20cf8460aa7d3d160208109e42b2de66658d54
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589726"
---
# <a name="managing-memory-for-adrlist-and-srowset-structures"></a>管理内存 ADRLIST 和 SRowSet 结构"

**适用于**： Outlook 2013 |Outlook 2016 
  
为尽可能使用单个**MAPIAllocateBuffer**呼叫缓冲区分配所有内存要求不适用于时使用的地址列表中或**ADRLIST**，和行集或**SRowSet**，结构。 
  
以下两个结构是分配和释放内存的标准规则例外。 它们包含多个层次结构的旨在使单个成员都能添加或删除。 因此，每个属性必须单独分配。 

其中大多数结构释放调用一次**MAPIFreeBuffer**，每个**ADRLIST**或**SRowSet**结构中的各个条目，必须释放自己调用**MAPIFreeBuffer**或单个调用**FreeProws**或**FreePadrlist**。 有关详细信息，请参阅[MAPIFreeBuffer](mapifreebuffer.md)、 [ADRLIST](adrlist.md)和[SRowSet](srowset.md)。 

**FreeProws**和**FreePadrlist**是由 MAPI 提供的用于简化这些数据结构释放的功能。 有关详细信息，请参阅[FreeProws](freeprows.md)和[FreePadrlist](freepadrlist.md)。 **FreePadrlist**释放**ADRLIST**结构内存以及所有关联的结构成员; 内存**FreeProws**执行相同的**SRowSet**结构。 
  
下图显示了指示所需的单独的内存分配**ADRLIST**数据结构的布局。 灰色框中显示可以分配和释放调用一次使用的内存。 
  
**ADRLIST 内存分配**
  
![ADRLIST 内存分配](media/amapi_52.gif "ADRLIST 内存分配")
  
## <a name="see-also"></a>另请参阅

- [管理 MAPI 中的内存](managing-memory-in-mapi.md)

