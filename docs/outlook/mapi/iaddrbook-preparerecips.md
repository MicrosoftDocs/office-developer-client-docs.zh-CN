---
title: IAddrBookPrepareRecips
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.PrepareRecips
api_type:
- COM
ms.assetid: d423f7b5-23b8-44dd-bca3-6590182dc42d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: db1c23f33e604d6aafdd8a046566c7390c281ad8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414275"
---
# <a name="iaddrbookpreparerecips"></a>IAddrBook::PrepareRecips

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
准备收件人列表供邮件系统稍后使用。 
  
```cpp
HRESULT PrepareRecips(
  ULONG ulFlags,
  LPSPropTagArray lpSPropTagArray,
  LPADRLIST lpRecipList
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制条目打开方式的标志的位掩码。 可以设置以下标志：
    
MAPI_CACHE_ONLY
  
> 仅使用脱机通讯簿执行名称解析。 例如，您可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。 此标志仅受通讯簿Exchange支持。
    
 _lpSPropTagArray_
  
> [in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，其中包含指示需要更新的属性（如果有）的属性标记数组。 _lpSPropTagArray_ 参数可以是 NULL。 
    
 _lpRecipList_
  
> [in]指向包含收件人 [列表的 ADRLIST](adrlist.md) 结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功准备收件人列表。
    
## <a name="remarks"></a>备注

客户端和服务提供商调用 **PrepareRecips** 方法来执行以下操作： 
  
- 确保  _lpRecipList_ 参数中所有收件人都有长期条目标识符。 
    
- 确保  _lpRecipList_ 参数中的每个收件人都有  _lpSPropTagArray_ 参数中列出的属性，并且这些属性显示在收件人列表的开始部分。 
    
MAPI 将每个收件人的短期条目标识符转换为长期条目标识符。 如有必要，从相应的通讯簿提供程序检索收件人的长期条目标识符，并请求任何其他属性。
  
在单个收件人条目中，首先对请求的属性排序，然后对条目已有的任何属性排序。 如果  _lpSPropTagArray_ 参数中的一个或多个请求属性不是由相应的通讯簿提供程序处理的，则其属性类型将设置为 PT_ERROR。 它们的属性值将设置为 MAPI_E_NOT_FOUND 或设置为其他值，以给出这些属性不可用的更具体的原因。 _lpRecipList_ 参数中包含的每个 [SPropValue](spropvalue.md)结构都必须使用 [MAPIAllocateBuffer](mapiallocatebuffer.md)和 [MAPIAllocateMore](mapiallocatemore.md)函数单独分配，以便可以单独释放它。 
  
有关属性类型PT_ERROR，请参阅 [属性类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMessage::ModifyRecipients](imessage-modifyrecipients.md)
  
[PidTagEntryId 规范属性](pidtagentryid-canonical-property.md)
  
[SPropValue](spropvalue.md)
  
[SRowSet](srowset.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

