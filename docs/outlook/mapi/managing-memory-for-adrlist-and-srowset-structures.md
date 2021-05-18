---
title: 管理 ADRLIST 和 SRowSet 结构的内存
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d009f6b6-d151-4d52-b7cc-a15127142354
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a5636cad7cad23bb5114bdbd34aff48c3639773b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407863"
---
# <a name="managing-memory-for-adrlist-and-srowset-structures"></a>管理 ADRLIST 和 SRowSet 结构的内存"

**适用于**：Outlook 2013 | Outlook 2016 
  
使用地址列表 **、ADRLIST、** 行集或 **SRowSet** 结构时，使用 **单个 MAPIAllocateBuffer** 调用尽可能为缓冲区分配所有内存的要求不适用。 
  
这两种结构是分配和释放内存的标准规则的例外。 它们包含多个级别的结构，旨在允许添加或删除单个成员。 因此，每个属性都必须是单独的分配。 

大多数结构通过一次 **MAPIFreeBuffer** 调用释放，ADRLIST 或 **SRowSet** 结构中的每个条目都必须通过其自己的 **MAPIFreeBuffer** 调用或对 **FreeProws** 或 **FreePadrlist** 的单个调用释放。  有关详细信息，请参阅 [MAPIFreeBuffer、](mapifreebuffer.md) [ADRLIST](adrlist.md)和 [SRowSet](srowset.md)。 

**FreeProws** 和 **FreePadrlist** 是由 MAPI 提供以简化释放这些数据结构的函数。 有关详细信息，请参阅 [FreeProws](freeprows.md) 和 [FreePadrlist](freepadrlist.md)。 **FreePadrlist** 释放 **ADRLIST** 结构的内存以及结构成员的所有关联内存; **FreeProws** 对 **SRowSet** 结构具有相同的作用。 
  
下图显示了 **ADRLIST** 数据结构的布局，指示所需的单独内存分配。 灰色框显示可通过一次调用分配和释放的内存。 
  
**ADRLIST 内存分配**
  
![ADRLIST 内存分配](media/amapi_52.gif "ADRLIST 内存分配")
  
## <a name="see-also"></a>另请参阅

- [在 MAPI 中管理内存](managing-memory-in-mapi.md)

