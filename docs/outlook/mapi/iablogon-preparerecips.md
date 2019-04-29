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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 0a9b88d762ca88cebd6d9acecf06db53a0b778f6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423858"
---
# <a name="iablogonpreparerecips"></a>IABLogon::PrepareRecips

**适用于**：Outlook 2013 | Outlook 2016 
  
准备收件人列表, 以供邮件系统以后使用。
  
```cpp
HRESULT PrepareRecips(
  ULONG ulFlags,
  LPSPropTagArray lpPropTagArray,
  LPADRLIST lpRecipList
);
```

## <a name="parameters"></a>参数

_ulFlags_
  
> 实时用于控制返回的字符串中的文本类型的标志的位掩码。 可以设置以下标志:
    
  - MAPI_CACHE_ONLY: 仅使用脱机通讯簿执行名称解析。 例如, 可以使用此标志允许客户端应用程序在缓存 exchange 模式中打开全局地址列表 (GAL), 并从缓存中访问该通讯簿中的条目, 而无需在客户端和服务器之间创建流量。 仅 Exchange 通讯簿提供程序支持此标志。
    
_lpPropTagArray_
  
> 实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含指示需要更新的属性的属性标记的数组 (如果有)。 _lpPropTagArray_参数可以为 NULL。 
    
_lpRecipList_
  
> 实时指向包含收件人列表的[ADRLIST](adrlist.md)结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功准备收件人列表。
    
MAPI_E_NOT_FOUND 
  
> _lpRecipList_参数中的一个或多个收件人不存在。 
    
## <a name="return-value"></a>返回值

客户端调用 MAPI [IAddrBook::P reparerecips](iaddrbook-preparerecips.md)方法来修改或重新排列一个或多个收件人的一组属性。 收件人可能会有, 也可能不是传出邮件的收件人列表的一部分。 MAPI 将此呼叫传送到通讯簿提供程序的**IABLogon::P reparerecips**方法。 
  
**IABLogon::P reparerecips**执行四个主要任务: 
  
- 确保_lpRecipList_参数指向的地址列表中的所有收件人都具有长期条目标识符。 
    
- 确保所有收件人具有在由_lpPropTagArray_参数指向的属性值数组中指定的属性。 
    
- 确保属性值数组中的属性显示在调用之前存在的任何其他属性之前。
    
- 确保**ADRLIST**结构中每个收件人的[ADRENTRY](adrentry.md)结构中的属性顺序与属性值数组中的顺序相同。 
    
_lpRecipList_参数中的**ADRENTRY**结构包含每个收件人的一个**ADRENTRY**结构。 每个**ADRENTRY**结构包含[SPropValue](spropvalue.md)结构的数组, 用于描述收件人的属性。 当**IABLogon::P reparerecips**返回时, 每个收件人的**SPropValue**结构数组包括_lpPropTagArray_中的属性以及收件人的其他属性。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

实现**IABLogon::P reparerecips**包括按特定顺序放置属性、检索属性值, 以及将短期条目标识符转换为长期条目标识符。 在_lpPropTagArray_参数中请求的属性必须位于与_lpRecipList_参数中的每个收件人的**ADRENTRY**结构相关联的属性值数组的开头。 如果这些属性的值不存在, 请使用其条目标识符打开关联的邮件用户或通讯组列表, 并检索缺少的属性值。 
  
分别分配_lpRecipList_中传递的每个**SPropValue**结构, 以便可以单独释放这些结构。 如果必须为任何**SPropValue**结构分配额外的空间, 例如, 若要存储 string 属性的数据, 请使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数为完整属性值数组分配额外的空间。 使用[MAPIFreeBuffer](mapifreebuffer.md)函数释放原始属性值数组, 然后使用[MAPIAllocateMore](mapiallocatemore.md)函数分配所需的其他任何内存。 
  
若要实现**IABLogon::P reparerecips**, 请使用以下过程:
  
1. 检查_lpPropTagArray_参数中的条目。 如果属性值数组为空, 则无需执行任何操作。 返回一个成功值。 
    
2. 处理_lpRecipList_参数中的每个收件人。 列表中的每个收件人都有一个**ADRENTRY**结构成员。 忽略下列类型的收件人: 
    
   - 在其**ADRENTRY**结构的**rgPropVals**成员中没有条目标识符的收件人 (即未解析的收件人)。 
    
   - 其条目标识符不属于您的提供程序的收件人。 这些收件人将被传递到另一个通讯簿提供程序。
    
3. 打开收件人, 并检索已为收件人设置的属性。
    
4. 将_lpRecipList_中指定的属性值数组与**GetProps**返回的属性数组合并。 如果两个属性数组中都出现相同的属性, 请使用_lpRecipList_中的值。
    
5. 如果_lpRecipList_属性值数组的大小足以容纳所有必需的属性, 只需将其替换为合并后的数组即可。 如果_lpRecipList_属性值数组不够大, 请将其替换为新分配的数组。 确保新的数组在其每个**cValues**成员中都有更新的值。 
    
6. 如果您不识别_lpPropTagArray_参数中的一个或多个属性, 请将收件人的**ADRENTRY**结构中的属性类型设置为 PT_ERROR, 并将属性值设置为 MAPI_E_NOT_FOUND 或其他值, 以提供更属性不可用的特定原因。 有关 PT_ERROR 的信息, 请参阅[属性类型](property-types.md)。
    
> [!NOTE]
> 永远不要重新分配传递到 IABLogon 中的**ADRLIST**结构 **::P reparerecips**或更改其条目数。 
  
## <a name="see-also"></a>另请参阅

- [ADRLIST](adrlist.md)
- [IMAPIProp::GetProps](imapiprop-getprops.md)
- [PidTagEntryId 规范属性](pidtagentryid-canonical-property.md)
- [SPropValue](spropvalue.md)
- [IABLogon : IUnknown](iablogoniunknown.md)

