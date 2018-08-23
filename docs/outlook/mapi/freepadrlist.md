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
ms.openlocfilehash: 39a184f00ccf54d4fa4477bbdf3086f3e44bddb0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576545"
---
# <a name="freepadrlist"></a>FreePadrlist

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
销毁[ADRLIST](adrlist.md)结构并释放关联的内存，包括分配给所有成员数组和结构的内存。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
void FreePadrlist(
  LPADRLIST padrlist
);
```

## <a name="parameters"></a>参数

 _padrlist_
  
> [in]指向要销毁**ADRLIST**结构。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="notes-to-callers"></a>给调用方的说明

作为其实现**FreePadrlist**的一部分，MAPI 调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放完整结构之前释放**ADRLIST**结构中的每个条目。 因此所有此类条目必须遵循了[ADRLIST](adrlist.md)结构的分配规则，使用个人[MAPIAllocateBuffer](mapiallocatebuffer.md)调用的每个成员数组和结构。 
  
有关为**ADRLIST**和**SRowSet**结构分配内存的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIABFunctions.cpp  <br/> |AddOneOffAddress  <br/> |MFCMAPI 使用**FreePadrlist**方法释放生成一次性地址添加到一条消息 ADRLIST 结构。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

