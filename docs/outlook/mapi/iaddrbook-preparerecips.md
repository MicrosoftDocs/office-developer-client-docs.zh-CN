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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339219"
---
# <a name="iaddrbookpreparerecips"></a>IAddrBook::PrepareRecips

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
准备收件人列表, 以供邮件系统以后使用。 
  
```cpp
HRESULT PrepareRecips(
  ULONG ulFlags,
  LPSPropTagArray lpSPropTagArray,
  LPADRLIST lpRecipList
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时用于控制条目打开方式的标志的位掩码。 可以设置以下标志:
    
MAPI_CACHE_ONLY
  
> 仅使用脱机通讯簿执行名称解析。 例如, 可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL), 并从缓存中访问该通讯簿中的条目, 而无需在客户端和服务器之间创建流量。 仅 Exchange 通讯簿提供程序支持此标志。
    
 _lpSPropTagArray_
  
> 实时一个指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含一个指明属性 (如果有) 需要更新的属性标记数组。 _lpSPropTagArray_参数可以为 NULL。 
    
 _lpRecipList_
  
> 实时指向包含收件人列表的[ADRLIST](adrlist.md)结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功准备收件人列表。
    
## <a name="remarks"></a>注解

客户端和服务提供程序调用**PrepareRecips**方法以执行以下操作: 
  
- 确保_lpRecipList_参数中的所有收件人都具有长期条目标识符。 
    
- 确保_lpRecipList_参数中的每个收件人都具有_lpSPropTagArray_参数中列出的属性, 并且这些属性将出现在收件人列表的开头。 
    
MAPI 将每个收件人的短期条目标识符转换为长期条目标识符。 如有必要, 将从相应的通讯簿提供程序中检索收件人的长期条目标识符, 并请求任何其他属性。
  
在单个收件人条目中, 首先对请求的属性进行排序, 然后对该条目的已有的所有属性进行排序。 如果_lpSPropTagArray_参数中的一个或多个请求的属性不是由相应的通讯簿提供程序处理的, 则它们的属性类型将设置为 PT_ERROR。 其属性值将设置为 MAPI_E_NOT_FOUND 或其他值, 以提供更具体的属性原因的原因。 必须使用[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIAllocateMore](mapiallocatemore.md)函数分别分配_lpRecipList_参数中包含的每个[SPropValue](spropvalue.md)结构, 以便可以单独释放该结构。 
  
有关 PT_ERROR 的信息, 请参阅[属性类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMessage::ModifyRecipients](imessage-modifyrecipients.md)
  
[PidTagEntryId 规范属性](pidtagentryid-canonical-property.md)
  
[SPropValue](spropvalue.md)
  
[SRowSet](srowset.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

