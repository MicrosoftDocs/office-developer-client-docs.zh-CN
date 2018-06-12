---
title: IABLogonPrepareRecips
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.PrepareRecips
api_type:
- COM
ms.assetid: 3c1845ea-e291-4855-9afd-51d2c64d7e85
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 82a7ecc8fbad0baf67b49c80c5a62cb8df94dfd1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775222"
---
# <a name="iablogonpreparerecips"></a>IABLogon::PrepareRecips

**适用于**： Outlook 
  
通过在邮件系统，以供以后使用准备收件人列表。
  
```cpp
HRESULT PrepareRecips(
  ULONG ulFlags,
  LPSPropTagArray lpPropTagArray,
  LPADRLIST lpRecipList
);
```

## <a name="parameters"></a>参数

_ulFlags_
  
> [in]位掩码的标志的控制返回的字符串中的文本的类型。 可以设置以下标记：
    
  - MAPI_CACHE_ONLY： 使用仅脱机通讯簿执行名称解析。 例如，您可以使用此标志以允许将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。 此标志仅受 Exchange 通讯簿提供程序支持。
    
_lpPropTagArray_
  
> [in]一个指向[SPropTagArray](sproptagarray.md)结构，其中包含指示需要更新，如果有属性的属性标记的数组。 _LpPropTagArray_参数可以是 NULL。 
    
_lpRecipList_
  
> [in]指向包含收件人列表的[ADRLIST](adrlist.md)结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功准备好的收件人列表。
    
MAPI_E_NOT_FOUND 
  
> 不存在一个或多个_lpRecipList_参数中的收件人。 
    
## <a name="return-value"></a>返回值

客户端调用 MAPI [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)方法来修改或重新排列的一个或多个收件人的一组属性。 收件人可能也可能不是传出邮件的收件人列表的一部分。 MAPI 传输对通讯簿提供程序的**IABLogon::PrepareRecips**方法的调用。 
  
**IABLogon::PrepareRecips**执行四个主要任务： 
  
- 确保地址列表中的所有收件人都指向_lpRecipList_参数具有长期的项标识符。 
    
- 确保所有收件人都有_lpPropTagArray_参数指向的属性值数组中指定的属性。 
    
- 确保在呼叫之前存在的任何其他属性之前出现属性值数组中的属性。
    
- 确保**ADRLIST**结构中的每个收件人的[ADRENTRY](adrentry.md)结构中属性的顺序相同属性值数组。 
    
**ADRENTRY**结构_lpRecipList_参数中的包含一个**ADRENTRY**结构，每个收件人。 每个**ADRENTRY**结构包含数组[SPropValue](spropvalue.md)结构来描述收件人的属性。 **IABLogon::PrepareRecips**返回时，每个收件人的**SPropValue**结构数组包含从_lpPropTagArray_收件人后跟其他属性的属性。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

实现**IABLogon::PrepareRecips**涉及将属性放在特定的顺序，检索属性值，并将其转换到长期条目标识符短期条目标识符。 属性值数组_lpRecipList_参数中的每个收件人的**ADRENTRY**结构相关联的开头必须请求_lpPropTagArray_参数中的属性。 如果不存在这些属性的值，使用其条目标识符打开相关联的邮件用户或通讯组列表，并检索缺少的属性值。 
  
分配每个**SPropValue**结构中传递_lpRecipList_单独，以便可以单独释放结构。 如果您必须为任何**SPropValue**结构来分配额外的空间，例如，来存储对于字符串属性，数据[MAPIAllocateBuffer](mapiallocatebuffer.md)函数用于为完整的属性值数组分配额外的空间。 使用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放原始属性值数组，然后使用[MAPIAllocateMore](mapiallocatemore.md)函数分配任何其他所需的内存。 
  
若要实现**IABLogon::PrepareRecips**，使用以下过程：
  
1. 检查_lpPropTagArray_参数中的项。 如果属性值数组为空，则执行任何操作。 返回一个成功值。 
    
2. 处理_lpRecipList_参数中的每个收件人。 没有为每个收件人列表中的一个**ADRENTRY**结构成员。 忽略以下类型的收件人： 
    
   - 没有其**ADRENTRY**结构 （即未解析的收件人） 的**rgPropVals**成员中的项标识符的收件人。 
    
   - 使用不属于您的提供商的项标识符的收件人。 这些收件人将传递给另一个通讯簿提供程序。
    
3. 打开收件人，并检索收件人已设置的属性。
    
4. 合并_lpRecipList_在阵列中从**GetProps**返回的属性中指定的属性值数组。 如果同一属性发生两个属性数组中，使用_lpRecipList_的值。
    
5. 如果足以容纳所有必要的属性_lpRecipList_属性值数组，只需替换它合并的数组。 如果_lpRecipList_属性值数组不足够大，将其与新分配的数组。 确保新数组中每个其**cValues**成员具有更新的值。 
    
6. 如果您不认识一个或多个_lpPropTagArray_参数中的属性，PT_ERROR 和到 MAPI_E_NOT_FOUND 或另一个值，该值提供更多的属性值的收件人的**ADRENTRY**结构中设置的属性类型该属性不可用的特定原因。 有关 PT_ERROR 的信息，请参阅[属性类型](property-types.md)。
    
> [!NOTE]
> 从不重新分配到**IABLogon::PrepareRecips**传递的**ADRLIST**结构或更改其项数。 
  
## <a name="see-also"></a>另请参阅

- [ADRLIST](adrlist.md)
- [IMAPIProp::GetProps](imapiprop-getprops.md)
- [PidTagEntryId 规范属性](pidtagentryid-canonical-property.md)
- [SPropValue](spropvalue.md)
- [IABLogon: IUnknown](iablogoniunknown.md)

