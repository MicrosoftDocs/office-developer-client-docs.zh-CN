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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287005"
---
# <a name="iaddrbookresolvename"></a>IAddrBook::ResolveName

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
执行名称解析, 将条目标识符分配给收件人列表中的收件人。
  
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
  
> 实时显示的对话框的父窗口的句柄 (如果指定), 以提示用户解决多义性问题。
    
 _ulFlags_
  
> 实时用于控制解决过程各个方面的标志的位掩码。 可以设置以下标志:
    
AB_UNICODEUI
  
> 指示_lpszNewEntryTitle_是一个 UNICODE 字符串。 
    
MAPI_CACHE_ONLY
  
> 仅使用脱机通讯簿执行名称解析。 例如, 可以使用此标志允许客户端应用程序在缓存 exchange 模式中打开全局地址列表 (GAL), 并从缓存中访问该通讯簿中的条目, 而无需在客户端和服务器之间创建流量。 仅 Exchange 通讯簿提供程序支持此标志。
    
MAPI_DIALOG 
  
> 显示一个对话框, 提示用户输入其他名称解析信息。 如果未设置此标志, 则不会显示任何对话框。 
    
MAPI_UNICODE 
  
> 指示在地址列表中返回的属性的类型应为 PT_UNICODE 而不是 PT_STRING8。 
    
 _lpszNewEntryTitle_
  
> 实时一个指针, 指向用于提示用户输入收件人的对话框中控件标题的文本。 标题根据收件人类型的不同而不同。 _lpszNewEntryTitle_参数可以为 NULL。 
    
 _lpAdrList_
  
> [输出]指向[ADRLIST](adrlist.md)结构的指针, 该结构包含要解析的收件人姓名的列表。 此**ADRLIST**结构可通过[IAddrBook:: Address](iaddrbook-address.md)方法创建。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 名称解析过程已成功。
    
MAPI_E_AMBIGUOUS_RECIP 
  
> _lpAdrList_参数中至少有一个收件人与通讯簿中的一个或多个条目匹配。 通常情况下, 在设置 MAPI_DIALOG 标志时, 将会返回此值, 禁止显示对话框。 
    
MAPI_E_NOT_FOUND 
  
> _lpAdrList_参数中至少有一个收件人无法解析。 通常情况下, 在设置 MAPI_DIALOG 标志时, 将会返回此值, 禁止显示对话框。 
    
## <a name="remarks"></a>注解

客户端和服务提供程序调用**ResolveName**方法以启动名称解析过程。 未解析的条目是尚不具有条目标识符或**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的条目。
  
 对于在_lpAdrList_参数中传递的地址列表中的每个未解析条目, **ResolveName**将完成以下过程。 
  
1. 如果收件人的地址类型遵循 SMTP 地址 ( _displayname_@ _domain_) 的格式, 则**ResolveName**将为其分配一次性条目标识符。 
    
2. 对于**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性中的每个容器, **ResolveName**调用[IABContainer:: ResolveNames](iabcontainer-resolvenames.md)方法。 **ResolveNames**尝试将每个未解析收件人的显示名称与其某个条目所属的显示名称进行匹配。 
    
3. 如果容器不支持**ResolveNames**, 则**ResolveName**使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制来限制容器的内容表。 此限制会导致容器执行 "最佳推测" 类型的搜索以查找匹配的收件人。 所有容器都必须支持**PR_ANR**属性限制。 
    
4. 当容器返回与多个名称匹配的收件人时, 如果设置了 MAPI_DIALOG 标志, **ResolveName**将显示一个对话框, 允许用户选择正确的名称。 
    
5. 如果已调用**PR_AB_SEARCH_PATH**属性中的所有容器, 但未找到匹配项, 则不会保持收件人的解析。 
    
如果一个或多个收件人未解析, **ResolveName**将返回 MAPI_E_NOT_FOUND。 如果一个或多个收件人具有不明确的分辨率, 无法通过对话框进行解析, 或者因为未设置 MAPI_DIALOG 标志, 则**ResolveName**将返回 MAPI_E_AMBIGUOUS_RECIP。 当某些收件人不明确且无法解析时, **ResolveName**可能会返回任一错误值。 
  
如果无法解析某个名称, 客户端可以创建一个具有特殊格式地址和条目标识符的一次性地址。 有关一次性条目标识符的格式的详细信息, 请参阅[一次性条目标识符](one-off-entry-identifiers.md)。 有关一次性地址的格式的详细信息, 请参阅[一次性地址](one-off-addresses.md)。
  
MAPI 支持**ADRLIST**的 Unicode 字符字符串和**ResolveName**的新条目标题参数;如果设置了 MAPI_UNICODE 标志, 以下属性将作为[ADRENTRY](adrentry.md)结构中的类型 PT_UNICODE 返回: 
  
- **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
- **PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))
    
- **PR_TRANSMITABLE_DISPLAY_NAME**([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))
    
但是, **PR_7BIT_DISPLAY_NAME** ([PidTag7BitDisplayName](pidtag7bitdisplayname-canonical-property.md)) 属性始终返回为类型 PT_STRING8。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIABFunctions  <br/> |AddOneOffAddress  <br/> |MFCMAPI 使用**ResolveName**方法在将一个一次性地址添加到邮件之前对其进行解析。  <br/> |
|MAPIABFunctions  <br/> |AddRecipient  <br/> |MFCMAPI 使用**ResolveName**方法按显示名称查找通讯簿条目。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[IABContainer::ResolveNames](iabcontainer-resolvenames.md)
  
[IAddrBook::Address](iaddrbook-address.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

