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
ms.openlocfilehash: aa72085c4e50fcef1f2d3da81e5409af3d55d89b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775245"
---
# <a name="iaddrbookresolvename"></a>IAddrBook::ResolveName

  
  
**适用于**： Outlook 
  
执行名称解析，分配给收件人列表中的收件人的项标识符。
  
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
  
> [in]显示一个对话框的父窗口的句柄如果指定，以提示用户解决歧义。
    
 _ulFlags_
  
> [in]控制决策过程的各个方面的标志的位掩码。 可以设置以下标志：
    
AB_UNICODEUI
  
> 指示该_lpszNewEntryTitle_是 UNICODE 字符串。 
    
MAPI_CACHE_ONLY
  
> 使用仅脱机通讯簿执行名称解析。 例如，您可以使用此标志以允许将客户端应用程序在缓存的 exchange 模式下打开全局地址列表 (GAL)，而不创建客户端和服务器之间的流量从缓存中访问该通讯簿中的条目。 此标志仅受 Exchange 通讯簿提供程序支持。
    
MAPI_DIALOG 
  
> 显示一个对话框，提示用户输入其他名称解析信息。 如果未设置此标志，则不显示任何对话框。 
    
MAPI_UNICODE 
  
> 指示应类型而不是 PT_STRING8 PT_UNICODE 的地址列表中返回的属性。 
    
 _lpszNewEntryTitle_
  
> [in]一个指向提示用户输入收件人的对话框中的控件的标题文本。 标题根据收件人的类型而有所不同。 _LpszNewEntryTitle_参数可以是 NULL。 
    
 _lpAdrList_
  
> [out]一个指向[ADRLIST](adrlist.md)结构，其中包含要解析的收件人姓名的列表。 可以通过[IAddrBook::Address](iaddrbook-address.md)方法创建该**ADRLIST**结构。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 名称解析过程成功。
    
MAPI_E_AMBIGUOUS_RECIP 
  
> 至少一个收件人的_lpAdrList_参数中匹配在通讯簿中的多个条目。 通常，当设置 MAPI_DIALOG 标志，禁止显示的对话框中，则返回此值。 
    
MAPI_E_NOT_FOUND 
  
> 无法解析_lpAdrList_参数中的至少一个收件人。 通常，当设置 MAPI_DIALOG 标志，禁止显示的对话框中，则返回此值。 
    
## <a name="remarks"></a>说明

客户端和服务提供商调用**ResolveName**方法以启动名称解析过程。 未解析的项是尚不具有条目标识符或**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的一个条目。
  
 **ResolveName**经历_lpAdrList_参数中传递的地址列表中每个未解析项的以下过程。 
  
1. 如果收件人的地址类型符合 SMTP 地址的格式 ( _displayname_@ _domain.top 级别域_)， **ResolveName**将其分配一个一次性条目标识符。 
    
2. 对于每个容器中的**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性， **ResolveName**调用[IABContainer::ResolveNames](iabcontainer-resolvenames.md)方法。 **ResolveNames**尝试匹配属于其项之一的显示名称与每个未解析的收件人的显示名称。 
    
3. 如果容器不支持**ResolveNames**， **ResolveName**将限制使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制的容器的内容表。 此限制将会导致容器来执行"最佳猜测"搜索来查找匹配的收件人类型。 所有容器都必须都支持**PR_ANR**属性限制。 
    
4. 当容器返回与多个名称相匹配的收件人时， **ResolveName**将显示一个对话框，如果设置 MAPI_DIALOG 标志是，它允许用户选择正确的名称。 
    
5. 如果调用了所有**PR_AB_SEARCH_PATH**属性中的容器，并且已找到不匹配，仍无法解析收件人。 
    
如果一个或多个收件人无法解析， **ResolveName**返回 MAPI_E_NOT_FOUND。 如果一个或多个收件人具有与对话框中，无法解析的不明确解决方案或由于未设置 MAPI_DIALOG 标志， **ResolveName**返回 MAPI_E_AMBIGUOUS_RECIP。 当某些收件人不明确而无法解析一些时， **ResolveName**可以返回其中任何一个错误值。 
  
如果无法解析名称，客户端可以创建具有特殊格式的地址以及条目标识符一次性地址。 一次性条目标识符的格式的详细信息，请参阅[一次性条目标识符](one-off-entry-identifiers.md)。 一次性地址的格式的详细信息，请参阅[一次性地址](one-off-addresses.md)。
  
MAPI **ADRLIST**和**ResolveName**; 的新条目标题参数中支持 Unicode 字符串如果设置 MAPI_UNICODE 标志，作为类型 PT_UNICODE [ADRENTRY](adrentry.md)结构中会返回以下属性： 
  
- **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
- **PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))
    
- **PR_TRANSMITABLE_DISPLAY_NAME**([PidTagTransmittableDisplayName](pidtagtransmittabledisplayname-canonical-property.md))
    
但是， **PR_7BIT_DISPLAY_NAME** ([PidTag7BitDisplayName](pidtag7bitdisplayname-canonical-property.md)) 属性始终返回键入 PT_STRING8。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIABFunctions.cpp  <br/> |AddOneOffAddress  <br/> |MFCMAPI 使用**ResolveName**方法来解析一次性地址之前将其添加到一条消息。  <br/> |
|MAPIABFunctions.cpp  <br/> |AddRecipient  <br/> |MFCMAPI 使用**ResolveName**方法查找按显示名称的通讯簿条目。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[IABContainer::ResolveNames](iabcontainer-resolvenames.md)
  
[IAddrBook::Address](iaddrbook-address.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

