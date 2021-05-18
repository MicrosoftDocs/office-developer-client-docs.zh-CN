---
title: IAddrBookResolveName
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.ResolveName
api_type:
- COM
ms.assetid: a7823c16-efda-45c2-b931-3e1fbc823b0b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8a6a73153b857078cb37d94a634a6b0215a0a8c5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408129"
---
# <a name="iaddrbookresolvename"></a>IAddrBook::ResolveName

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
执行名称解析，将条目标识符分配给收件人列表中的收件人。
  
```cpp
HRESULT ResolveName(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPSTR lpszNewEntryTitle,
  LPADRLIST lpAdrList
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]对话框的父窗口的句柄，如果已指定，则显示该句柄以提示用户解决歧义问题。
    
 _ulFlags_
  
> [in]控制解决方案过程各个方面的标志的位掩码。 可以设置以下标志：
    
AB_UNICODEUI
  
> 指示  _lpszNewEntryTitle_ 是 UNICODE 字符串。 
    
MAPI_CACHE_ONLY
  
> 仅使用脱机通讯簿执行名称解析。 例如，您可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。 此标志仅受通讯簿Exchange支持。
    
MAPI_DIALOG 
  
> 显示一个对话框，提示用户输入其他名称解析信息。 如果未设置此标志，则不显示任何对话框。 
    
MAPI_UNICODE 
  
> 指示地址列表中返回的属性的类型应为 PT_UNICODE 而不是 PT_STRING8。 
    
 _lpszNewEntryTitle_
  
> [in]指向对话框中控件标题的文本的指针，提示用户输入收件人。 标题因收件人类型而异。 _lpszNewEntryTitle_ 参数可以是 NULL。 
    
 _lpAdrList_
  
> [in-out]指向包含要解析的收件人姓名列表的 [ADRLIST](adrlist.md) 结构的指针。 此 **ADRLIST** 结构可通过 [IAddrBook：：Address 方法](iaddrbook-address.md) 创建。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 名称解析过程成功。
    
MAPI_E_AMBIGUOUS_RECIP 
  
> _lpAdrList_ 参数中至少有一个收件人与通讯簿中的多个条目匹配。 通常，此值在设置 MAPI_DIALOG 标志时返回，禁止显示对话框。 
    
MAPI_E_NOT_FOUND 
  
> _lpAdrList_ 参数中至少有一个收件人无法解析。 通常，此值在设置 MAPI_DIALOG 标志时返回，禁止显示对话框。 
    
## <a name="remarks"></a>备注

客户端和服务提供商调用 **ResolveName** 方法以启动名称解析过程。 未解析的条目是尚没有条目标识符或PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 条目。 
  
 **ResolveName** 将针对在  _lpAdrList_ 参数中传递的地址列表中的每个未解析条目执行以下过程。 
  
1. 如果收件人的地址类型符合 SMTP 地址 ( _displayname_ @  _domain.top-level-domain_) 的格式 **，ResolveName** 会为其分配一次条目标识符。 
    
2. 对于 [PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md) PR_AB_SEARCH_PATH (的每个容器 **，ResolveName**) [IABContainer：：ResolveNames](iabcontainer-resolvenames.md)方法。  **ResolveNames** 尝试将每个未显示名称收件人的收件人与属于显示名称条目之一的收件人匹配。 
    
3. 如果容器不支持 **ResolveNames，ResolveName** 将通过使用 PR_ANR ([PidTagAnr](pidtaganr-canonical-property.md) ) 限制来限制容器的内容表。  此限制会导致容器执行"最佳猜测"类型的搜索以查找匹配的收件人。 所有容器 **都必须支持PR_ANR** 限制。 
    
4. 当容器返回与多个名称匹配的收件人时，如果设置了 MAPI_DIALOG 标志 **，ResolveName** 将显示一个对话框，允许用户选择正确的名称。 
    
5. 如果已调用 PR_AB_SEARCH_PATH **所有容器** ，并且未找到匹配项，则收件人将保持未解析。 
    
如果一个或多个收件人未解析 **，ResolveName** 将返回MAPI_E_NOT_FOUND。 如果一个或多个收件人具有无法通过对话框解析的不明确解析，或者由于未设置 MAPI_DIALOG 标志 **，ResolveName** 将返回 MAPI_E_AMBIGUOUS_RECIP。 当某些收件人不明确且某些收件人无法解析时 **，ResolveName** 可能会返回任一错误值。 
  
如果无法解析名称，客户端可以创建具有特殊格式的地址和条目标识符的一次使用地址。 有关一次输入标识符格式的信息，请参阅 [一次使用条目标识符](one-off-entry-identifiers.md)。 有关一次使用地址格式的信息，请参阅 [一次使用地址](one-off-addresses.md)。
  
MAPI 支持 **ADRLIST** 的 Unicode 字符字符串和 **ResolveName** 的新条目标题参数;如果设置 MAPI_UNICODE 标志，则以下属性作为 [ADRENTRY](adrentry.md) PT_UNICODE类型返回： 
  
- **PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) 
    
- **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
    
- **PR_EMAIL_ADDRESS (** [PidTagEmailAddress)](pidtagemailaddress-canonical-property.md)
    
- **PR_TRANSMITABLE_DISPLAY_NAME (** [PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md)) 
    
但是 **，PR_7BIT_DISPLAY_NAME (** [PidTag7BitDisplayName](pidtag7bitdisplayname-canonical-property.md)) 属性始终作为类型PT_STRING8。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIABFunctions.cpp  <br/> |AddOneOffAddress  <br/> |MFCMAPI 在将地址添加到邮件之前，使用 **ResolveName** 方法解析该地址。  <br/> |
|MAPIABFunctions.cpp  <br/> |AddRecipient  <br/> |MFCMAPI 使用 **ResolveName** 方法来查找通讯簿条目，显示名称。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[IABContainer::ResolveNames](iabcontainer-resolvenames.md)
  
[IAddrBook::Address](iaddrbook-address.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

