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
  
销毁[ADRLIST](adrlist.md)结构并释放关联内存, 包括为所有成员数组和结构分配的内存。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
void FreePadrlist(
  LPADRLIST padrlist
);
```

## <a name="parameters"></a>参数

 _padrlist_
  
> 实时指向要销毁的**ADRLIST**结构的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="notes-to-callers"></a>给调用方的说明

在**FreePadrlist**的实现过程中, MAPI 将调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 以释放**ADRLIST**结构中的每个条目, 然后再释放完整的结构。 因此, 所有这样的条目都必须遵循[ADRLIST](adrlist.md)结构的分配规则, 为每个成员数组和结构使用单独的[MAPIAllocateBuffer](mapiallocatebuffer.md)调用。 
  
有关为**ADRLIST**和**SRowSet**结构分配内存的详细信息, 请参阅[管理 ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIABFunctions  <br/> |AddOneOffAddress  <br/> |MFCMAPI 使用**FreePadrlist**方法来释放为向邮件添加一次性地址而生成的 ADRLIST 结构。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

