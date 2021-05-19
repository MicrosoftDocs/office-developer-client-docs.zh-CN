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
  
准备收件人列表供邮件系统稍后使用。
  
```cpp
HRESULT PrepareRecips(
  ULONG ulFlags,
  LPSPropTagArray lpPropTagArray,
  LPADRLIST lpRecipList
);
```

## <a name="parameters"></a>参数

_ulFlags_
  
> [in]控制返回的字符串中的文本类型的标志位掩码。 可以设置以下标志：
    
  - MAPI_CACHE_ONLY：使用脱机通讯簿执行名称解析。 例如，您可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。 此标志仅受通讯簿Exchange支持。
    
_lpPropTagArray_
  
> [in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，其中包含指示需要更新的属性（如果有）的属性标记数组。 _lpPropTagArray_ 参数可以是 NULL。 
    
_lpRecipList_
  
> [in]指向包含收件人 [列表的 ADRLIST](adrlist.md) 结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功准备收件人列表。
    
MAPI_E_NOT_FOUND 
  
> _lpRecipList_ 参数中的一个或多个收件人不存在。 
    
## <a name="return-value"></a>返回值

客户端调用 MAPI [IAddrBook：:P repareRecips](iaddrbook-preparerecips.md) 方法来修改或重新排列一个或多个收件人的一组属性。 收件人可能是传出邮件的收件人列表的一部分，也可能不是该收件人列表的一部分。 MAPI 将此调用转接到通讯簿提供商的 **IABLogon：:P repareRecips** 方法。 
  
**IABLogon：:P repareRecips** 执行四个主要任务： 
  
- 确保  _lpRecipList_ 参数指向的地址列表中的所有收件人都有一个长期条目标识符。 
    
- 确保所有收件人都有由  _lpPropTagArray_ 参数指向的属性值数组中指定的属性。 
    
- 确保属性值数组中的属性显示在调用之前已存在的其他任何属性之前。
    
- 确保 **ADRLIST** 结构中每个收件人 [的 ADRENTRY](adrentry.md)结构中属性的顺序与属性值数组中的顺序相同。 
    
_lpRecipList_ 参数中的 **ADRENTRY** 结构包含每个收件人的一个 **ADRENTRY** 结构。 每个 **ADRENTRY** 结构都包含一个 [SPropValue](spropvalue.md) 结构数组，用于描述收件人的属性。 **当 IABLogon：:P repareRecips** 返回时，每个收件人的 **SPropValue** 结构数组包括 _lpPropTagArray_ 中的属性，后跟收件人的其他属性。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

实现 **IABLogon：:P repareRecips** 涉及按特定顺序放置属性、检索属性值以及将短期条目标识符转换为长期条目标识符。 _lpPropTagArray_ 参数中请求的属性必须位于与 _lpRecipList_ 参数中每个收件人 **的 ADRENTRY** 结构关联的属性值数组的起始点。 如果这些属性不存在，则使用关联的邮件用户或通讯组列表的条目标识符打开它，并检索缺少的属性值。 
  
单独分配传入 _lpRecipList_ 的每个 **SPropValue** 结构，以便可以单独释放结构。 例如，如果必须为任何 **SPropValue** 结构分配额外空间以存储字符串属性的数据，请使用 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数为完整属性值数组分配额外空间。 使用 [MAPIFreeBuffer](mapifreebuffer.md) 函数释放原始属性值数组，然后使用 [MAPIAllocateMore](mapiallocatemore.md) 函数分配所需的任何其他内存。 
  
若要实现 **IABLogon：:P repareRecips，** 请使用以下过程：
  
1. 检查  _lpPropTagArray_ 参数中的条目。 如果属性值数组为空，则无需执行任何操作。 返回成功值。 
    
2. 处理  _lpRecipList 参数中的每个_ 收件人。 列表中每个收件人都有一个 **ADRENTRY** 结构成员。 忽略以下类型的收件人： 
    
   - **ADRENTRY** 结构的 **rgPropVals** 成员中没有条目标识符 (，即未解析的收件人) 。 
    
   - 具有不属于您的提供程序的条目标识符的收件人。 这些收件人将被传递到另一个通讯簿提供程序。
    
3. 打开收件人并检索为收件人设置的属性。
    
4. 将  _lpRecipList_ 中指定的属性值数组与从 **GetProps** 返回的属性数组合并。 如果同一属性出现在两个属性数组中，请使用  _lpRecipList 中的值_。
    
5. 如果  _lpRecipList_ 属性值数组足够大，足以容纳所有必需的属性，只需将其替换为合并的数组。 如果  _lpRecipList_ 属性值数组不够大，请将其替换为新分配的数组。 确保新数组的每个 **cValues** 成员中都有更新的值。 
    
6. 如果您无法识别  _lpPropTagArray_ 参数中的一个或多个属性，将收件人 **的 ADRENTRY** 结构中的属性类型设置为 PT_ERROR，将属性值设置为 MAPI_E_NOT_FOUND 或设置为其他值，以更具体地解释属性不可用的原因。 有关属性类型PT_ERROR，请参阅 [属性类型](property-types.md)。
    
> [!NOTE]
> 切勿重新分配传递到 **IABLogon：:P repareRecips 的** **ADRLIST** 结构或更改其条目数。 
  
## <a name="see-also"></a>另请参阅

- [ADRLIST](adrlist.md)
- [IMAPIProp::GetProps](imapiprop-getprops.md)
- [PidTagEntryId 规范属性](pidtagentryid-canonical-property.md)
- [SPropValue](spropvalue.md)
- [IABLogon : IUnknown](iablogoniunknown.md)

