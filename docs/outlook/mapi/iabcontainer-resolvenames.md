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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279568"
---
# <a name="iabcontainerresolvenames"></a>IABContainer::ResolveNames

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为一个或多个收件人条目执行名称解析。
  
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
  
> 实时一个指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含一个属性标记数组, 这些标记描述提供程序返回的[ADRLIST](adrlist.md)结构中要包含的属性。 若要请求提供程序的默认属性集, 请在_lpPropTagArray_参数中传递 NULL。 
    
 _ulFlags_
  
> 实时用于控制返回的字符串中的文本类型的标志的位掩码。 可以设置以下标志:
    
EMS_AB_ADDRESS_LOOKUP
  
> 仅找到精确的代理地址匹配项;忽略部分匹配项。 仅 Exchange 通讯簿提供程序支持此标志。
    
MAPI_CACHE_ONLY
  
> 仅将脱机通讯簿用于执行名称解析。 例如, 可以使用此标志启用客户端应用程序, 以在缓存 exchange 模式下打开全局地址列表 (GAL), 并从缓存中访问该通讯簿中的条目, 而无需在客户端和服务器之间创建流量。 仅 Exchange 通讯簿提供程序支持此标志。 
    
MAPI_UNICODE 
  
> 返回的字符串属性采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 _lpAdrList_
  
> [in, out]在输入时, 指向包含要解析的收件人列表的**ADRLIST**结构的指针。 在输出时, 指向包含解析的名称的**ADRLIST**结构的指针。 
    
 _lpFlagList_
  
> [in, out]指向标志数组的指针, 每个与_lpAdrList_参数中的[ADRENTRY](adrentry.md)结构对应的标记, 该标记提供收件人的名称解析操作的状态。 _lpFlagList_参数中的标志与_lpAdrList_中的条目的顺序相同。 可以设置以下标志:
    
MAPI_AMBIGUOUS 
  
> 已解决相应的收件人, 但不是唯一的条目标识符。 其他容器不应尝试解析该收件人。 
    
MAPI_RESOLVED 
  
> 相应的收件人已解析为唯一条目标识符。 其他容器不应尝试解析该收件人。 
    
MAPI_UNRESOLVED 
  
> 尚未解析对应的条目。 其他容器应尝试解析该收件人。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 名称解析过程成功完成。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
MAPI_E_NO_SUPPORT 
  
> 通讯簿提供程序不支持通过使用此方法进行批量名称解析。
    
## <a name="remarks"></a>注解

**ResolveNames**方法尝试将未解析的收件人从_lpAdrList_参数中的条目数组与此通讯簿容器中的收件人进行匹配。 未解析的收件人通常仅具有**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性, 并且可能还有其他一些属性。 未解析的收件人不具有**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性, 并且_lpFlagList_参数中的相应标志设置为 MAPI_UNRESOLVED。 相反, 解析的收件人始终至少具有**PR_ENTRYID**属性和其他几个属性, 如**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))、 **PR_DISPLAY_NAME**和**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))。
  
名称解析通常在客户端调用[IAddrBook:: ResolveName](iaddrbook-resolvename.md)方法时启动。 Outlook MAPI 通过调用通讯簿搜索路径中包含的每个通讯簿容器的**ResolveNames**方法进行响应, 由**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性指定。 _lpAdrList_参数中的条目包含已解决的收件人, 因为它们位于 MAPI 已被调用**ResolveNames**的容器中, 因为这些条目显示在搜索路径的前面。 
  
每个容器都尝试通过将收件人的显示名称与它的一个条目的显示名称相匹配来解析未解析的条目。 找到唯一匹配时, **ResolveNames**会将_lpPropTagArray_参数中包含的**PR_ENTRYID**属性和其他属性添加到传出**ADRLIST**结构中的相应条目。 **ResolveNames**然后将_lpFlagList_参数中的条目设置为 MAPI_RESOLVED。 存储在**PR_ENTRYID**属性中的条目标识符可以是短期的, 也可以是长期的。 
  
在搜索路径中的所有容器都试图进行名称解析过程之后, MAPI 将打开一个对话框, 以提示用户解决其余冲突的帮助信息。 
  
客户端也可以在对[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法的调用中使用返回的**ADRLIST**结构。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

不需要使用**ResolveNames**方法支持名称解析。 相反, 或者, 也可以使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制来支持它。 如果决定依赖**PR_ANR**限制进行名称解析, 则可以返回 MAPI_E_NO_SUPPORT。 有关详细信息, 请参阅[实现名称解析](implementing-name-resolution.md)。
  
如果收件人与容器的任何收件人都不匹配, 则将_lpFlagList_参数中的收件人的标志条目设置为 MAPI_UNRESOLVED。 
  
当收件人匹配多个收件人时, 将其标志设置为 "MAPI_AMBIGUOUS", 并且不更改其**ADRENTRY**结构。 
  
对于邮件的收件人列表中包含的收件人, MAPI 需要特定的属性。 您可以将它们作为名称解析过程的一部分包含在**ADRENTRY**结构中, 或等待 MAPI 请求调用[IAddrBook::P reparerecips](iaddrbook-preparerecips.md)和[IMAPISupport:: ExpandRecips](imapisupport-expandrecips.md)方法。 您可以通过在所有解析的收件人的**ADRENTRY**结构中包括以下属性来消除这些额外的调用并提高性能。 
  
- **PR_ADDRTYPE**
    
- **PR_DISPLAY_NAME**
    
- **PR_EMAIL_ADDRESS**
    
- **PR_ENTRYID**
    
- **PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))
    
- **PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))
    
- **PR_TRANSMITABLE_DISPLAY_NAME**([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))
    
如果_lpPropTagArray_参数中的某些属性不可用 (通常是因为容器条目不支持属性, 并且它们不包含在**ADRLIST**结构的收件人的**ADRENTRY**成员中) 中。将每个不可用属性的属性类型设置为 PT_ERROR。 
  
请勿从解析的收件人的**ADRENTRY**结构中删除任何属性。 
  
如果您必须替换而不是修改**ADRENTRY**结构, 请先通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放原始**ADRENTRY**结构, 然后将替换的**ADRENTRY**结构[分配给MAPIAllocateBuffer](mapiallocatebuffer.md)。
  
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

