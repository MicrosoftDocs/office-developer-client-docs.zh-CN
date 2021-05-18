---
title: FreePadrlist
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FreePadrlist
api_type:
- COM
ms.assetid: ca8fbac6-b6f1-46ab-90a1-fc16f0d5824c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 95c2e52760bd7d65351b4dd2091b68a43cd2f97c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408640"
---
# <a name="freepadrlist"></a>FreePadrlist

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
销毁 [ADRLIST](adrlist.md) 结构并释放关联的内存，包括分配给所有成员数组和结构的内存。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
void FreePadrlist(
  LPADRLIST padrlist
);
```

## <a name="parameters"></a>参数

 _padrlist_
  
> [in]指向要 **销毁的 ADRLIST** 结构的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="notes-to-callers"></a>给调用方的说明

作为 **FreePadrlist** 实现一部分 [，MAPI 调用 MAPIFreeBuffer](mapifreebuffer.md) 函数以释放 **ADRLIST** 结构的每一项，然后再释放整个结构。 因此，所有此类条目都必须遵循 [ADRLIST](adrlist.md) 结构的分配规则，并针对每个成员数组和结构使用单个 [MAPIAllocateBuffer](mapiallocatebuffer.md) 调用。 
  
有关为 **ADRLIST** 和 **SRowSet** 结构分配内存的信息，请参阅 [管理 ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIABFunctions.cpp  <br/> |AddOneOffAddress  <br/> |MFCMAPI 使用 **FreePadrlist** 方法释放 ADRLIST 结构，该结构构建为向邮件添加一次地址。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

