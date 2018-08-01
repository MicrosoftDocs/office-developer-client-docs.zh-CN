---
title: IABContainerResolveNames
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABContainer.ResolveNames
api_type:
- COM
ms.assetid: 27474af2-29a2-4cfb-b94f-72eb91562dac
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ed87a2a6e3232cec492da6be032cf54cd66c3772
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775210"
---
# <a name="iabcontainerresolvenames"></a>IABContainer::ResolveNames

  
  
**适用于**： Outlook 
  
执行一个或多个收件人的条目的名称解析。
  
```cpp
HRESULT ResolveNames(
  LPSPropTagArray lpPropTagArray,
  ULONG ulFlags,
  LPADRLIST lpAdrList,
  LPFlagList lpFlagList
);
```

## <a name="parameters"></a>参数

 _lpPropTagArray_
  
> [in]一个指向[SPropTagArray](sproptagarray.md)结构，其中包含数组属性标记描述要包括在[ADRLIST](adrlist.md)结构提供程序返回的属性。 若要请求提供程序的默认属性集，请_lpPropTagArray_参数中传递 NULL。 
    
 _ulFlags_
  
> [in]位掩码的标志的控制返回的字符串中的文本的类型。 可以设置以下标志：
    
EMS_AB_ADDRESS_LOOKUP
  
> 将找到仅确切代理地址匹配;部分匹配项将被忽略。 此标志仅受 Exchange 通讯簿提供程序支持。
    
MAPI_CACHE_ONLY
  
> 仅在脱机通讯簿将用于执行名称解析。 例如，您可以使用此标志若要将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。 此标志仅受 Exchange 通讯簿提供程序支持。 
    
MAPI_UNICODE 
  
> 返回的字符串属性采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 _lpAdrList_
  
> [传入、 传出]在输入，指向**ADRLIST**结构，其中包含要解析的收件人列表的指针。 在输出，指向包含解析的名称**ADRLIST**结构的指针。 
    
 _lpFlagList_
  
> [传入、 传出]为数组标志的指针，对应于[ADRENTRY](adrentry.md)结构_lpAdrList_参数中每个标志提供收件人的名称解析操作的状态。 _LpFlagList_参数中的标志处于_lpAdrList_中的项的顺序相同。 可以设置以下标志：
    
MAPI_AMBIGUOUS 
  
> 相应的接收人已得到解决，但不适用于唯一项标识符。 其他容器不应尝试解析该收件人。 
    
MAPI_RESOLVED 
  
> 已为唯一条目标识符解决了相应的收件人。 其他容器不应尝试解析该收件人。 
    
MAPI_UNRESOLVED 
  
> 尚未解决的相应项。 其他容器应尝试解析该收件人。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 名称解析过程成功。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
MAPI_E_NO_SUPPORT 
  
> 通讯簿提供程序不支持批量名称解析使用此方法。
    
## <a name="remarks"></a>说明

**ResolveNames**方法尝试匹配未解析的收件人，数组中的条目_lpAdrList_参数中向此通讯簿容器中的收件人。 无法解析的收件人通常具有仅**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性和可能的一些其他属性。 无法解析的收件人没有**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，而且其_lpFlagList_参数中的相应标志设置为 MAPI_UNRESOLVED。 相反，解析的收件人总是至少具有**PR_ENTRYID**属性以及**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))、 **PR_DISPLAY_NAME**，等**PR_ADDRTYPE** ([的其他几个属性PidTagAddressType](pidtagaddresstype-canonical-property.md))。
  
通常，当在客户端调用[IAddrBook::ResolveName](iaddrbook-resolvename.md)方法时，将启动名称解析。 Outlook MAPI 响应通过调用**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性指定的通讯簿搜索路径中包含每个通讯簿容器的**ResolveNames**方法。 _LpAdrList_参数中的项包括因为它们在容器为其 MAPI 已调用**ResolveNames**，因为在搜索路径的前面部分中显示的项已成功解析的收件人。 
  
每个容器尝试解析的未解决的条目匹配收件人的显示名称，其条目之一的显示名称。 当找到唯一的匹配项时， **ResolveNames**添加**PR_ENTRYID**属性和传出**ADRLIST**结构中的相应条目的_lpPropTagArray_参数中包含其他属性。 然后， **ResolveNames** MAPI_RESOLVED 的_lpFlagList_参数中设置该条目。 短期或长期，可以是存储在**PR_ENTRYID**属性中的项标识符。 
  
毕竟中搜索的容器的路径具有尝试名称解析过程、 MAPI 打开一个对话框，如果可能，以提示用户输入帮助解决任何剩余的冲突。 
  
客户端还可以对[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法调用中使用返回的**ADRLIST**结构。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

您无需使用**ResolveNames**方法支持名称解析。 相反，或此外，您可以与**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制来支持它。 如果您决定依赖于**PR_ANR**限制的名称解析，您可以返回 MAPI_E_NO_SUPPORT。 有关详细信息，请参阅[实现名称解析](implementing-name-resolution.md)。
  
如果收件人不匹配的任何容器的收件人，请在 MAPI_UNRESOLVED _lpFlagList_参数设置收件人的标志条目。 
  
收件人匹配时多个收件人，将其标志设置为 MAPI_AMBIGUOUS，而不更改其**ADRENTRY**结构。 
  
MAPI 要求对收件人的邮件的收件人列表中包含的某些属性。 您可以将它们作为名称解析过程的一部分包含**ADRENTRY**结构中或等待 MAPI 请求它们通过[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)和[IMAPISupport::ExpandRecips](imapisupport-expandrecips.md)方法的调用。 您可以消除这些额外的呼叫和提高性能，通过将所有已解析的收件人的**ADRENTRY**结构包括以下属性： 
  
- **PR_ADDRTYPE**
    
- **PR_DISPLAY_NAME**
    
- **PR_EMAIL_ADDRESS**
    
- **PR_ENTRYID**
    
- **PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))
    
- **PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))
    
- **PR_TRANSMITABLE_DISPLAY_NAME**([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))
    
如果_lpPropTagArray_参数中的属性的一些不可 — 通常因为容器条目不支持的属性，并且它们不包括在**ADRLIST**结构中的收件人的**ADRENTRY**成员 —设置为 PT_ERROR 不可用的每个属性的属性类型。 
  
不要从解析的收件人的**ADRENTRY**结构中删除任何属性。 
  
如果必须替换，而不是修改**ADRENTRY**结构，释放首先通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数，原始**ADRENTRY**结构，然后将分配替换[**ADRENTRY**结构MAPIAllocateBuffer](mapiallocatebuffer.md)。
  
## <a name="see-also"></a>另请参阅



[ADRENTRY](adrentry.md)
  
[ADRLIST](adrlist.md)
  
[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)
  
[IAddrBook::ResolveName](iaddrbook-resolvename.md)
  
[IMAPISupport::ExpandRecips](imapisupport-expandrecips.md)
  
[IMessage::ModifyRecipients](imessage-modifyrecipients.md)
  
[PidTagAnr 规范属性](pidtaganr-canonical-property.md)
  
[SPropertyRestriction](spropertyrestriction.md)
  
[IABContainer : IMAPIContainer](iabcontainerimapicontainer.md)

