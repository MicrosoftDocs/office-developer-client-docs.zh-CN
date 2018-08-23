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
ms.openlocfilehash: 0735008575db5e1cab62dbde4b699b15e04cedb0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567284"
---
# <a name="imessagemodifyrecipients"></a>IMessage::ModifyRecipients

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
添加、 删除或修改邮件的收件人。
  
```cpp
HRESULT ModifyRecipients(
  ULONG ulFlags,
  LPADRLIST lpMods
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，控件的收件人的更改。 如果为_ulFlags_参数传递零，则**ModifyRecipients**用_lpMods_参数指向的收件人列表替换所有现有收件人。 可以为_ulFlags_设置以下标志：
    
MODRECIP_ADD 
  
> _LpMods_参数指向的收件人应添加到的收件人列表中。 
    
MODRECIP_MODIFY 
  
> _LpMods_参数指向的收件人应替换现有的收件人。 以免那些相应[ADRENTRY](adrentry.md)结构中替换所有现有属性。 
    
MODRECIP_REMOVE 
  
> 应从作为索引使用**PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md)) 属性包含属性值数组_lpMods_参数中的每个收件人项中的收件人列表中删除现有收件人。 
    
 _lpMods_
  
> [in]指向[ADRLIST](adrlist.md)结构，其中包含要添加、 删除或修改邮件中的收件人列表的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功修改的收件人列表。
    
## <a name="remarks"></a>注解

**IMessage::ModifyRecipients**方法可更改邮件的收件人列表。 它是从该列表中，在[ADRLIST](adrlist.md)结构中，保留收件人表构建。 
  
**ADRLIST**结构包含一个[ADRENTRY](adrentry.md)结构，每个收件人，并且每个**ADRENTRY**结构包含描述收件人属性的属性值的数组。 
  
可以解析或无法解析**ADRLIST**结构中的收件人。 区别在于数量和类型所包含的属性。 无法解析的收件人包含**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性解析的收件人包含这些两个属性以及**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 和**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))。 如果可用**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))，它还可以包含这些属性。
  
邮件提交时，它必须在其收件人列表中包含已解析的收件人。 未解析的收件人导致未送达报告创建和发送到邮件的原始发件人。 有关从客户端角度名称解析过程的详细信息，请参阅[解析名称](resolving-a-recipient-name.md)。 从通讯簿提供程序的角度来看的详细信息，请参阅[实现名称解析](implementing-name-resolution.md)。
  
除了解析和未解析的收件人，收件人可以为 NULL。 收件人的**ADRENTRY**结构的**cValues**成员设置为零，并且**rgPropVals**成员设置为 NULL。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以通过调用[IAddrBook::Address](imapisupport-address.md)以显示公共对话框，并提示用户选择条目创建收件人列表。 为**地址** _lppAdrList_参数指向的地址列表可以作为_lpMods_参数传递给**ModifyRecipients** 。 
  
[ADRLIST](adrlist.md)结构中的收件人的指定属性时，包括所有收件人的属性、 不仅新的或更改起来。 修改收件人时，会删除**ADRLIST**结构中不包含任何属性。 若要检索所有邮件的收件人，当前的属性集，请调用[GetRecipientTable](imessage-getrecipienttable.md) ，并检索的所有行。 **ADRLIST**结构与**SRowSet** ，因为您可以交替使用它们。
  
 **ModifyRecipients**将替换所有当前的收件人列表中的项所指的_lpMods_时无标志设置_ulFlags_参数中的信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当设置 MODRECIP_MODIFY 标志时， **ModifyRecipients**会将每个收件人的整行替换_lpMods_中传递的[ADRLIST](adrlist.md)结构中的关联行。 请注意指定所有收件人都应有而不考虑它们是否已更改可防止意外删除的属性。
  
下面是一些**ADRLIST**结构中设置属性的收件人的规则： 
  
- 不要使用 PT_NULL 作为属性类型。 在遇到此值时， **ModifyRecipients**将返回错误。 
    
- 不要使用 PT_ERROR 作为属性类型。 **ModifyRecipients**将忽略此值。 
    
- _UlFlags_中设置的 MODRECIP_REMOVE 或 MODRECIP_MODIFY 标志时，应包含所有收件人**PR_ROWID**属性。 
    
- 不包括**PR_ROWID**属性的任何收件人时_ulFlags_或时传递零_ulFlags_中的设置 MODRECIP_ADD 标志。
    
如果收件人和一个包括**PR_ADDRTYPE**属性或**PR_EMAIL_ADDRESS**属性或两个这些属性不一致的地址类型和由**PR_ENTRYID**，标识的收件人地址结果不确定。 即，有三种可能性，具体取决于服务提供商：
  
- 邮件将传递到**PR_ADDRTYPE**和**PR_EMAIL_ADDRESS**属性并由它们所述的地址。 
    
- 邮件将传递给收件人由**PR_ENTRYID**标识。
    
- 邮件将声明的地址信息歧义由于未送达。
    
使用[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)中概述的分配规则的收件人列表为分配内存。 **ModifyRecipients**不释放**ADRLIST**结构也任何子结构。 **ADRLIST**结构和每个[SPropValue](spropvalue.md)结构必须单独分配使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以便可以单独释放每。 如果方法的任何**SPropValue**结构需要额外的空间，它可以与一个更高版本可以通过使用[MAPIFreeBuffer](mapifreebuffer.md)释放的新替换**SPropValue**结构。 此外应使用**MAPIFreeBuffer**释放原始**SPropValue**结构。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIABFunctions.cpp  <br/> |AddRecipient  <br/> |MFCMAPI 使用**IMessage::ModifyRecipients**方法将一个新收件人添加到一条消息。  <br/> |
   
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

