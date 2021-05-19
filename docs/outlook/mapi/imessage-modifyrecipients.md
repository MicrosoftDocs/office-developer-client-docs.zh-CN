---
title: IMessageModifyRecipients
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.ModifyRecipients
api_type:
- COM
ms.assetid: 2625f29d-325f-417d-bcec-49d580f9cd7e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 07e1c2104068a6eb242e8ba81f91655edaa92cd8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426238"
---
# <a name="imessagemodifyrecipients"></a>IMessage::ModifyRecipients

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
添加、删除或修改邮件收件人。
  
```cpp
HRESULT ModifyRecipients(
  ULONG ulFlags,
  LPADRLIST lpMods
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制收件人更改的标志的位掩码。 如果为  _ulFlags_ 参数传递零 **，ModifyRecipients** 将用  _lpMods_ 参数指向的收件人列表替换所有现有收件人。 可以为  _ulFlags_ 设置以下标志：
    
MODRECIP_ADD 
  
> _lpMods_ 参数指向的收件人应添加到收件人列表中。 
    
MODRECIP_MODIFY 
  
> _lpMods_ 参数指向的收件人应替换现有收件人。 所有现有属性都替换为相应的 [ADRENTRY 结构中](adrentry.md) 的属性。 
    
MODRECIP_REMOVE 
  
> 应该将 _lpMods_ 参数中每个收件人条目的属性值数组中包含的 **PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md)) 属性用作索引，从收件人列表中删除现有收件人。 
    
 _lpMods_
  
> [in]指向包含邮件中要添加、删除或修改的收件人列表的 [ADRLIST](adrlist.md) 结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功修改收件人列表。
    
## <a name="remarks"></a>备注

**IMessage：：ModifyRecipients** 方法更改邮件的收件人列表。 收件人表是在 [ADRLIST](adrlist.md) 结构中基于此列表构建的。 
  
**ADRLIST** 结构包含每个收件人的一个 [ADRENTRY](adrentry.md)结构，而每个 **ADRENTRY** 结构包含描述收件人属性的属性值数组。 
  
**ADRLIST** 结构的收件人可以解析或解析。 区别在于所包含属性的数量和类型。 未解析的收件人仅包含 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和 **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性，而解析的收件人包含这两个属性以及 **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 和 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 。 如果 **PR_EMAIL_ADDRESS (** PidTagEmailAddress) 可用，则还可以包含该 [PidTagEmailAddress。](pidtagemailaddress-canonical-property.md)
  
在提交邮件时，邮件必须仅包括收件人列表中已解析的收件人。 未解析的收件人会导致创建未送达报告，并发送给邮件的原始发件人。 有关从客户端角度解析名称过程的信息，请参阅 [解析名称](resolving-a-recipient-name.md)。 有关通讯簿提供程序方面的信息，请参阅 [实现名称解析](implementing-name-resolution.md)。
  
除了解析和未解析的收件人之外，收件人还可以为 NULL。 收件人 **的 ADRENTRY** 结构的 **cValues** 成员设置为零 **，rgPropVals** 成员设置为 NULL。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以通过调用 [IAddrBook：：Address](imapisupport-address.md) 来显示公用对话框并提示用户选择条目来创建收件人列表。 _lppAdrList_ 参数指向 **Address** 的地址列表可以作为 _lpMods_ 参数传递给 **ModifyRecipients。** 
  
在 [ADRLIST](adrlist.md) 结构中指定收件人的属性时，请包含收件人的所有属性，而不仅是新的或已更改的属性。 修改收件人时，将删除 **ADRLIST** 结构中未包括的任何属性。 若要检索邮件的所有收件人的当前属性集，请调用 [GetRecipientTable](imessage-getrecipienttable.md) 并检索所有行。 由于 **SRowSet** 的结构与 **ADRLIST** 相同，因此可以互换使用。
  
 当 _ulFlags_ 参数中没有设置任何标志时 **，ModifyRecipients** 会用 _lpMods_ 指向的信息替换当前收件人列表中的所有条目。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当您设置 MODRECIP_MODIFY 标志时 **，ModifyRecipients** 会用传入 _lpMods_ 的 [ADRLIST](adrlist.md)结构中的关联行替换每个收件人行。 请注意指定收件人应具有的所有属性，无论这些属性是否已更改以防止意外删除。
  
以下是在 **ADRLIST** 结构中设置收件人属性的一些规则： 
  
- 请勿将PT_NULL用作属性类型。 **ModifyRecipients** 在遇到此值时返回错误。 
    
- 请勿将PT_ERROR用作属性类型。 **ModifyRecipients** 将忽略此值。 
    
- 在 _ulFlags_ **PR_ROWID** 设置 MODRECIP_REMOVE 或 MODRECIP_MODIFY 标记时，包括所有收件人的 MODRECIP_REMOVE 属性。 
    
- 在 ulFlags **中** 设置 MODRECIP_ADD 标志或在  _ulFlags_ 中传递零时，请勿包含任何收件人的  _PR_ROWID 属性_。
    
如果包含收件人的 **PR_ADDRTYPE** 属性或 **PR_EMAIL_ADDRESS** 属性，并且其中一个或两个属性与 PR_ENTRYID 标识的收件人的地址类型和地址不一致，则结果 **未** 定义。 也就是说，有三种可能性，具体取决于服务提供商：
  
- 邮件将传递到由属性和属性PR_ADDRTYPE PR_EMAIL_ADDRESS地址。  
    
- 邮件将传递给由收件人标识的 **PR_ENTRYID。**
    
- 由于地址信息不明确，邮件将被声明为无法送达。
    
使用管理 [ADRLIST 和 SRowSet](managing-memory-for-adrlist-and-srowset-structures.md) 结构的内存中概述的分配规则为收件人列表分配内存。 **ModifyRecipients** 不会释放 **ADRLIST** 结构及其任何子结构。 必须使用 [MAPIAllocateBuffer](mapiallocatebuffer.md)函数单独分配 **ADRLIST** 结构和每个 [SPropValue](spropvalue.md)结构，这样可以单独释放每个结构。 如果该方法需要任何 **SPropValue** 结构的附加空间，它可以将 **SPropValue** 结构替换为一个新结构，稍后可以使用 [MAPIFreeBuffer](mapifreebuffer.md)释放该结构。 还应该使用 **MAPIFreeBuffer** 释放原始 **SPropValue** 结构。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIABFunctions.cpp  <br/> |AddRecipient  <br/> |MFCMAPI 使用 **IMessage：：ModifyRecipients** 方法向邮件添加新收件人。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ADRENTRY](adrentry.md)
  
[ADRLIST](adrlist.md)
  
[IAddrBook::Address](iaddrbook-address.md)
  
[IMAPISupport::Address](imapisupport-address.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropValue](spropvalue.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

