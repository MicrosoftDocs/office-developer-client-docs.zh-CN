---
title: FreeProws
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FreeProws
api_type:
- HeaderDef
ms.assetid: 0f8f9fc4-4940-4c0a-92cc-2a6409b9a13f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0686cee9bf6fa47332f75f99e1d2a2d35cb7e7fb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578022"
---
# <a name="freeprows"></a>FreeProws

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
销毁[SRowSet](srowset.md)结构并释放关联的内存，包括分配给所有成员数组和结构的内存。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
void FreeProws(
  LPSRowSet prows
);
```

## <a name="parameters"></a>参数

 _prows_
  
> [in]指向要销毁**SRowSet**结构。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="notes-to-callers"></a>给调用方的说明

作为其实现**FreeProws**的一部分，MAPI 调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放完整结构之前释放**SRowSet**结构中的每个条目。 因此所有此类条目必须遵循了[SRowSet](srowset.md)结构的分配规则，使用个人[MAPIAllocateBuffer](mapiallocatebuffer.md)调用的每个成员数组和结构。 
  
有关为**ADRLIST**和**SRowSet**结构分配内存的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |DwThreadFuncLoadTable  <br/> |MFCMAPI 使用**FreeProws**方法来释放包含正在处理 table 的行 SRowSet 结构。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

