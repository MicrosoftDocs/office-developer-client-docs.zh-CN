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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fe3e098b2b70e77bd0c536002a4724810261bff3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19775274"
---
# <a name="iaddrbookpreparerecips"></a>IAddrBook::PrepareRecips

  
  
**适用于**： Outlook 
  
通过在邮件系统，以供以后使用准备收件人列表。 
  
```cpp
HRESULT PrepareRecips(
  ULONG ulFlags,
  LPSPropTagArray lpSPropTagArray,
  LPADRLIST lpRecipList
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，控制如何打开该条目。 可以设置以下标记：
    
MAPI_CACHE_ONLY
  
> 使用仅脱机通讯簿执行名称解析。 例如，可以使用此标志以允许在缓存的 exchange 模式下打开全局地址列表 (GAL) 和从缓存中访问该通讯簿中的条目，而不创建客户端和服务器之间的流量的客户端应用程序。 此标志仅受 Exchange 通讯簿提供程序支持。
    
 _lpSPropTagArray_
  
> [in]指向包含属性标记指示属性，如果有一个数组[SPropTagArray](sproptagarray.md)结构的指针，需要更新。 _LpSPropTagArray_参数可以是 NULL。 
    
 _lpRecipList_
  
> [in]指向[ADRLIST](adrlist.md)结构，其中包含的收件人列表的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功准备好的收件人列表。
    
## <a name="remarks"></a>说明

客户端和服务提供商调用**PrepareRecips**方法以执行下列操作： 
  
- 确保_lpRecipList_参数中的所有收件人都具有长期条目标识符。 
    
- 确保_lpRecipList_参数中的每个收件人有_lpSPropTagArray_参数中列出的属性，并且这些属性显示收件人列表的开头。 
    
MAPI 将每个收件人的短期条目标识符转换为长期条目标识符。 如有必要，收件人的长期条目标识符检索从相应地址簿提供程序和系统要求的任何其他属性。
  
在单个收件人条目，请求的属性被排序首先，跟已存在的项的任何属性。 如果一个或多个_lpSPropTagArray_参数中所请求属性不会处理相应地址簿提供程序，其属性类型将设置为 PT_ERROR。 其属性值会设置为 MAPI_E_NOT_FOUND 或另一个值，该值提供更具体原因为什么属性不可用。 _LpRecipList_参数中包含每个[SPropValue](spropvalue.md)结构必须单独分配使用的[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIAllocateMore](mapiallocatemore.md)函数，以便可以单独被释放。 
  
有关 PT_ERROR 的信息，请参阅[属性类型](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMessage::ModifyRecipients](imessage-modifyrecipients.md)
  
[PidTagEntryId 规范属性](pidtagentryid-canonical-property.md)
  
[SPropValue](spropvalue.md)
  
[SRowSet](srowset.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

