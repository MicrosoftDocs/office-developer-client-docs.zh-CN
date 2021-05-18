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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fac4978bef94650f85ac3179acd3858602f933ec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405812"
---
# <a name="iabcontainerresolvenames"></a>IABContainer::ResolveNames

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对一个或多个收件人条目执行名称解析。
  
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
  
> [in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，该结构包含一组属性标记，用于描述提供程序返回 [的 ADRLIST](adrlist.md) 结构中包含的属性。 若要请求提供程序的默认属性集，请传递  _lpPropTagArray_ 参数中的 NULL。 
    
 _ulFlags_
  
> [in]控制返回的字符串中的文本类型的标志位掩码。 可以设置以下标志：
    
EMS_AB_ADDRESS_LOOKUP
  
> 将仅找到确切的代理地址匹配项;部分匹配将被忽略。 此标志仅受通讯簿Exchange支持。
    
MAPI_CACHE_ONLY
  
> 只有脱机通讯簿将用于执行名称解析。 例如，您可以使用此标志使客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。 此标志仅受通讯簿Exchange支持。 
    
MAPI_UNICODE 
  
> 返回的字符串属性采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 _lpAdrList_
  
> [in， out]输入时，指向包含要解析的收件人列表的 **ADRLIST** 结构的指针。 输出时，指向包含已解析名称 **的 ADRLIST** 结构的指针。 
    
 _lpFlagList_
  
> [in， out]指向标志数组的指针，每个标志对应于 _lpAdrList_ 参数中的 [ADRENTRY](adrentry.md)结构，该指针为收件人提供名称解析操作的状态。 _lpFlagList_ 参数中的标志与 _lpAdrList_ 中的条目的顺序相同。 可以设置以下标志：
    
MAPI_AMBIGUOUS 
  
> 已解析相应的收件人，但没有解析为唯一条目标识符。 其他容器不应尝试解析此收件人。 
    
MAPI_RESOLVED 
  
> 相应的收件人已解析为唯一条目标识符。 其他容器不应尝试解析此收件人。 
    
MAPI_UNRESOLVED 
  
> 尚未解析相应的条目。 其他容器应尝试解析此收件人。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 名称解析过程已成功。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
MAPI_E_NO_SUPPORT 
  
> 通讯簿提供程序不支持使用此方法进行批量名称解析。
    
## <a name="remarks"></a>备注

**ResolveNames** 方法尝试将 _lpAdrList_ 参数中的条目数组中的未解析收件人匹配到此通讯簿容器中的收件人。 未解析的收件人通常仅具有 PR_DISPLAY_NAME  ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性和一些其他属性。 未解析的收件人没有 PR_ENTRYID  ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，并且 _其 lpFlagList_ 参数中的相应标志设置为 MAPI_UNRESOLVED。 相反，解析的收件人始终至少具有 **PR_ENTRYID** 属性以及几个其他属性，如 **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md) **) 、PR_DISPLAY_NAME** 和 **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 。
  
名称解析通常在客户端调用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md) 方法时启动。 OutlookMAPI 通过调用通讯簿搜索路径中包含的每个通讯簿容器的 **ResolveNames** 方法进行响应，该路径由 **PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性指定。 _lpAdrList_ 参数中的条目包括已解析的收件人，因为它们在 MAPI 已调用 **ResolveNames** 的容器中，因为这些条目之前显示在搜索路径中。 
  
每个容器尝试解析未解析的条目，显示名称收件人的收件人地址与显示名称条目之一匹配。 当找到唯一匹配项时 **，ResolveNames** 会将 **PR_ENTRYID** 属性和  _lpPropTagArray_ 参数中包含的其他属性添加到传出 **ADRLIST** 结构中的相应条目。 **然后 ResolveNames** 将  _lpFlagList_ 参数中的条目MAPI_RESOLVED。 存储在 PR_ENTRYID **属性中的** 条目标识符可以是短期的或长期。 
  
在搜索路径中的所有容器尝试名称解析过程后，MAPI 将打开一个对话框（如果可能）以提示用户帮助解决任何剩余的冲突。 
  
客户端还可以在调用 [IMessage：：ModifyRecipients](imessage-modifyrecipients.md)方法时使用返回的 **ADRLIST** 结构。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

无需使用 **ResolveNames** 方法支持名称解析。 相反，或者另外，可以使用 PidTagAnr **PR_ANR (** [PidTagAnr](pidtaganr-canonical-property.md)) 支持它。 如果您决定依赖于名称解析 **PR_ANR** 限制，可以返回MAPI_E_NO_SUPPORT。 有关详细信息，请参阅 [实现名称解析](implementing-name-resolution.md)。
  
在  _lpFlagList_ 参数中设置收件人的标记条目MAPI_UNRESOLVED如果收件人与容器的任何收件人都不匹配，则设置该条目。 
  
当收件人与多个收件人匹配时，请设置其标志MAPI_AMBIGUOUS不要更改 **其 ADRENTRY** 结构。 
  
MAPI 要求邮件的收件人列表中包含的收件人的某些属性。 可以在名称解析过程中将它们包括在 **ADRENTRY** 结构中，或者等待 MAPI 通过调用 [IAddrBook：:P repareRecips](iaddrbook-preparerecips.md) 和 [IMAPISupport：：ExpandRecips](imapisupport-expandrecips.md) 方法来请求它们。 通过在所有解析的收件人的 **ADRENTRY** 结构中包括以下属性，可以消除这些额外的呼叫并提高性能： 
  
- **PR_ADDRTYPE**
    
- **PR_DISPLAY_NAME**
    
- **PR_EMAIL_ADDRESS**
    
- **PR_ENTRYID**
    
- **PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md)) 
    
- **PR_SEARCH_KEY (** [PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 
    
- **PR_TRANSMITABLE_DISPLAY_NAME (** [PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md)) 
    
如果 _lpPropTagArray_ 参数中的某些属性不可用（通常是因为容器条目不支持这些属性，并且这些属性不包含在 **ADRLIST** 结构中收件人的 **ADRENTRY** 成员中）将每个不可用属性的属性类型设置为 PT_ERROR。 
  
不要从解析的收件人的 **ADRENTRY** 结构中删除任何属性。 
  
如果必须替换而不是修改 **ADRENTRY** 结构，请首先通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放原始 **ADRENTRY** 结构，然后使用 [MAPIAllocateBuffer](mapiallocatebuffer.md)分配替换 **ADRENTRY** 结构。
  
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

