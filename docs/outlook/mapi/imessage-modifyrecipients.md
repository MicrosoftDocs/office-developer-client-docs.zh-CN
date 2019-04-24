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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349257"
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
  
> 实时控制收件人更改的标志的位掩码。 如果为_ulFlags_参数传递零, **ModifyRecipients**将使用_lpMods_参数指向的收件人列表替换所有现有的收件人。 可以为_ulFlags_设置以下标志:
    
MODRECIP_ADD 
  
> 应将_lpMods_参数指向的收件人添加到收件人列表中。 
    
MODRECIP_MODIFY 
  
> 由_lpMods_参数指向的收件人应替换现有的收件人。 所有现有属性都将替换为相应的[ADRENTRY](adrentry.md)结构中的属性。 
    
MODRECIP_REMOVE 
  
> 应从收件人列表中删除现有收件人。作为索引, 应将**PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md)) 属性包含在_lpMods_参数中每个收件人条目的属性值数组中。 
    
 _lpMods_
  
> 实时指向[ADRLIST](adrlist.md)结构的指针, 该结构包含要在邮件中添加、删除或修改的收件人列表。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功修改收件人列表。
    
## <a name="remarks"></a>注解

**IMessage:: ModifyRecipients**方法更改邮件的收件人列表。 它来自此列表, 并保留在[ADRLIST](adrlist.md)结构中, 收件人表已建立。 
  
**ADRLIST**结构包含每个收件人的一个[ADRENTRY](adrentry.md)结构, 每个**ADRENTRY**结构包含一个描述收件人属性的属性值数组。 
  
可以解析或解析**ADRLIST**结构中的收件人。 不同之处在于所包含的属性的数量和类型。 未解析的收件人仅包含**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性, 而解析的收件人包含这两个属性加上**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 和**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))。 如果**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 可用, 也可以包含该功能。
  
邮件提交时, 必须在收件人列表中仅包含解析的收件人。 未解析的收件人会导致创建 nondelivery 报告并将其发送给邮件的原始发件人。 有关客户端角度的名称解析过程的详细信息, 请参阅[解析名称](resolving-a-recipient-name.md)。 有关通讯簿提供程序的角度的详细信息, 请参阅[实现名称解析](implementing-name-resolution.md)。
  
除了已解析和未解析的收件人之外, 收件人可以为 NULL。 将收件人的**ADRENTRY**结构的**cValues**成员设置为零, 并将**rgPropVals**成员设置为 NULL。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以通过调用[IAddrBook:: Address](imapisupport-address.md)来显示通用对话框, 并提示用户选择条目, 从而创建收件人列表。 _lppAdrList_参数指向**address**的地址列表可以作为_lpMods_参数传递给**ModifyRecipients** 。 
  
当您在[ADRLIST](adrlist.md)结构中指定收件人的属性时, 请包含收件人的所有属性, 而不仅仅是新的或更改的属性。 修改收件人时, 将删除**ADRLIST**结构中不包含的任何属性。 若要检索邮件的所有收件人的当前属性集, 请调用[GetRecipientTable](imessage-getrecipienttable.md)并检索所有行。 由于**SRowSet**在结构中与**ADRLIST**的结构相同, 因此可以交替使用它们。
  
 **ModifyRecipients**将当前收件人列表中的所有条目替换为_lpMods_在_ulFlags_参数中未设置任何标记时指向的信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当您设置 MODRECIP_MODIFY 标志时, **ModifyRecipients**会将每个收件人行替换为在_lpMods_中传递的[ADRLIST](adrlist.md)结构中的关联行。 请务必指定收件人应具有的所有属性, 而无需考虑是否已将其更改为阻止无意中删除它们。
  
下面是在**ADRLIST**结构中设置收件人的属性的一些规则: 
  
- 请勿使用 PT_NULL 作为属性类型。 当遇到此值时, **ModifyRecipients**将返回错误。 
    
- 请勿使用 PT_ERROR 作为属性类型。 **ModifyRecipients**将忽略此值。 
    
- 当您在_ulFlags_中设置 MODRECIP_REMOVE 或 MODRECIP_MODIFY 标志时, 包括所有收件人的**PR_ROWID**属性。 
    
- 当您在_ulFlags_中设置 MODRECIP_ADD 标志或在_ulFlags_中传递0时, 请勿包含任何收件人的**PR_ROWID**属性。
    
如果您包含收件人的**PR_ADDRTYPE**属性或**PR_EMAIL_ADDRESS**属性, 并且其中一个或两个属性与**PR_ENTRYID**标识的收件人的地址类型和地址不一致, 则结果未定义。 也就是说, 有三种可能性, 具体取决于服务提供商:
  
- 邮件将传递到**PR_ADDRTYPE**和**PR_EMAIL_ADDRESS**属性所描述的地址。 
    
- 邮件将传递给由**PR_ENTRYID**标识的收件人。
    
- 由于地址信息不明确, 邮件将被声明为无法送达。
    
使用在[管理 ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)中概述的分配规则为收件人列表分配内存。 **ModifyRecipients**不释放**ADRLIST**结构及其任何 substructures。 必须使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数对**ADRLIST**结构和每个 SPropValue 结构进行单独分配, 以便可以单独释放每个[](spropvalue.md)结构。 如果该方法需要额外的空间用于任何**SPropValue**结构, 则可以将**SPropValue**结构替换为稍后可使用[MAPIFreeBuffer](mapifreebuffer.md)释放的新结构。 原始**SPropValue**结构也应使用**MAPIFreeBuffer**来释放。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIABFunctions  <br/> |AddRecipient  <br/> |MFCMAPI 使用**IMessage:: ModifyRecipients**方法将新的收件人添加到邮件中。  <br/> |
   
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

