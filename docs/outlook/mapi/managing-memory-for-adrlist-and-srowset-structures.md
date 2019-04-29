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
# <a name="managing-memory-for-adrlist-and-srowset-structures"></a>管理 ADRLIST 和 SRowSet 结构的内存

**适用于**：Outlook 2013 | Outlook 2016 
  
如果使用单个**MAPIAllocateBuffer**调用时, 需要为缓冲区分配所有内存, 如果使用地址列表、 **ADRLIST**、行集或**SRowSet**, 则不适用。 
  
这两个结构是用于分配和释放内存的标准规则的例外。 它们包含多个级别的结构, 旨在允许添加或删除单个成员。 因此, 每个属性都必须是单独的分配。 

在使用一次调用**MAPIFreeBuffer**释放大部分结构后, **ADRLIST**或**SRowSet**结构中的每个单独条目都必须使用自己的**MAPIFreeBuffer**调用或对**FreeProws** **的单个调用进行释放, 或者FreePadrlist**。 有关详细信息, 请参阅[MAPIFreeBuffer](mapifreebuffer.md)、 [ADRLIST](adrlist.md)和[SRowSet](srowset.md)。 

**FreeProws**和**FreePadrlist**是 MAPI 提供的用于简化这些数据结构的释放的函数。 有关详细信息, 请参阅[FreeProws](freeprows.md)和[FreePadrlist](freepadrlist.md)。 **FreePadrlist**释放**ADRLIST**结构的内存以及结构成员的所有关联内存;**FreeProws**对**SRowSet**结构进行相同的工作。 
  
下图显示了**ADRLIST**数据结构的布局, 指示需要单独的内存分配。 灰色框显示可通过一次调用分配和释放的内存。 
  
**ADRLIST 内存分配**
  
![ADRLIST 内存分配](media/amapi_52.gif "ADRLIST 内存分配")
  
## <a name="see-also"></a>另请参阅

- [管理 MAPI 中的内存](managing-memory-in-mapi.md)

