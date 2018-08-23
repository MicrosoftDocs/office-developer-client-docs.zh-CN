---
title: IMAPISupportAddress
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.Address
api_type:
- COM
ms.assetid: 8c22547e-ddf5-47f7-aed3-76e3854688df
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 524bbfe5f40a66585fb4ed4463b057ca6a0c881a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586800"
---
# <a name="imapisupportaddress"></a>IMAPISupport::Address

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
显示通用的地址对话框。 
  
```cpp
HRESULT Address(
  ULONG_PTR FAR * lpulUIParam,
  LPADRPARM lpAdrParms,
  LPADRLIST FAR * lppAdrList
);
```

## <a name="parameters"></a>参数

 _lpulUIParam_
  
> [传入、 传出]指向对话框中的父窗口的句柄的指针。 在输入时，必须始终传递窗口句柄。 输出，如果 DIALOG_SDI 标志设置在[ADRPARM](adrparm.md)结构中所指的_lpAdrParms_参数，则返回无模式对话框的窗口句柄。 
    
 _lpAdrParms_
  
> [传入、 传出]指向控制的演示文稿和行为的地址对话框的**ADRPARM**结构的指针。 
    
 _lppAdrList_
  
> [传入、 传出]指向地址列表的指针的指针。 在输入时，此列表可是当前列表的邮件中的收件人或 NULL，如果不存在任何此类列表。 输出， _lppAdrList_指向经过更新的邮件的收件人列表。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功地显示地址对话框。
    
## <a name="remarks"></a>注解

对于通讯簿提供程序支持对象实现**IMAPISupport::Address**方法。 通讯簿提供程序调用要创建或更新的邮件的收件人列表的**地址**。 
  
包括在[ADRLIST](adrlist.md)结构_lppAdrList_参数指向[ADRENTRY](adrentry.md)结构中介绍了每个收件人。 **ADRENTRY**结构包含收件人属性值数组，其中之一是收件人的类型或**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性。 此**ADRLIST**结构可以传递给客户端使用作为[IMessage::ModifyRecipients](imessage-modifyrecipients.md)将调用_lpMods_参数。
  
**ADRLIST**结构中的每个收件人可以可以解析，指示其属性值之一是其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，或无法解析，指示**PR_ENTRYID**属性缺少。 
  
除了**PR_ENTRYID**，已解析的收件人包括以下属性：
  
- **PR_RECIPIENT_TYPE**
    
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
- **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
- **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))
    
未解析的收件人通常包括只有**PR_DISPLAY_NAME**和**PR_RECIPIENT_TYPE**。 
  
## <a name="notes-to-callers"></a>给调用方的说明

传入呼叫者的**ADRLIST**结构可能从结构的 MAPI 返回不同的大小。 当您为**ADRLIST**结构分配内存时，将单独为每个[SPropValue](spropvalue.md)结构分配内存。 
  
使用 MAPI 内存分配功能在传递给[ABProviderInit](abproviderinit.md)函数指针分配内存。 **ADRLIST**和中**ADRLIST** **ADRENTRY**结构中的每个属性值结构分配[MAPIAllocateBuffer](mapiallocatebuffer.md)函数使用的内存。 
  
如果**地址**必须返回较大的**ADRLIST**结构，或者如果您已为_lppAdrList_传递 NULL，**地址**释放原始结构，并分配一个新。 **地址**还分配**ADRLIST**结构中的其他属性值结构并释放根据旧的。 有关如何将内存管理**ADRLIST**结构的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。
  
 **地址**立即返回 DIALOG_SDI 标志设置在_lpAdrParms_参数的**ADRPARM**结构中。 
  
## <a name="see-also"></a>另请参阅



[ABProviderInit](abproviderinit.md)
  
[ADRENTRY](adrentry.md)
  
[ADRLIST](adrlist.md)
  
[ADRPARM](adrparm.md)
  
[FreePadrlist](freepadrlist.md)
  
[FreeProws](freeprows.md)
  
[IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMessage::ModifyRecipients](imessage-modifyrecipients.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[PidTagAddressType 规范属性](pidtagaddresstype-canonical-property.md)
  
[PidTagDisplayName 规范属性](pidtagdisplayname-canonical-property.md)
  
[PidTagDisplayType 规范属性](pidtagdisplaytype-canonical-property.md)
  
[PidTagEntryId 规范属性](pidtagentryid-canonical-property.md)
  
[PidTagRecipientType 规范属性](pidtagrecipienttype-canonical-property.md)
  
[SPropValue](spropvalue.md)
  
[SRowSet](srowset.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)


[管理 ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)

