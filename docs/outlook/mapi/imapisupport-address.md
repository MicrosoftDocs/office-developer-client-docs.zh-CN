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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7300c11d5835640fe308430c9bb08d40b397e47b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331603"
---
# <a name="imapisupportaddress"></a>IMAPISupport::Address

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示 "常用地址" 对话框。 
  
```cpp
HRESULT Address(
  ULONG_PTR FAR * lpulUIParam,
  LPADRPARM lpAdrParms,
  LPADRLIST FAR * lppAdrList
);
```

## <a name="parameters"></a>参数

 _lpulUIParam_
  
> [in, out]指向对话框父窗口的句柄的指针。 在输入时, 必须始终传递窗口句柄。 在输出时, 如果在[ADRPARM](adrparm.md)结构中设置了_lpAdrParms_参数指向的 DIALOG_SDI 标志, 则将返回无模式对话框的窗口句柄。 
    
 _lpAdrParms_
  
> [in, out]指向控制 "地址" 对话框的外观和行为的**ADRPARM**结构的指针。 
    
 _lppAdrList_
  
> [in, out]指向地址列表的指针的指针。 在输入时, 此列表是邮件中的收件人的当前列表, 如果不存在这样的列表, 则为 NULL。 在输出时, _lppAdrList_指向已更新的邮件收件人列表。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功显示 "地址" 对话框。
    
## <a name="remarks"></a>注解

为通讯簿提供程序支持对象实现了**IMAPISupport:: Address**方法。 通讯簿提供程序呼叫**地址**以创建或更新邮件收件人的列表。 
  
每个收件人都在由_lppAdrList_参数指向的[ADRLIST](adrlist.md)结构中包含的[ADRENTRY](adrentry.md)结构中进行了描述。 **ADRENTRY**结构包含收件人属性值的数组, 其中一个是收件人的类型或**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性。 在对[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)的调用中, 可以将此**ADRLIST**结构传递给客户端, 以用作_lpMods_参数。
  
可以解析**ADRLIST**结构中的每个收件人, 这表示它的属性值之一是其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性或未解析, 这表示**PR_ENTRYID**属性为尚. 
  
除了**PR_ENTRYID**, 解析的收件人还包含以下属性:
  
- **PR_RECIPIENT_TYPE**
    
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
- **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
- **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))
    
未解析的收件人通常仅包括**PR_DISPLAY_NAME**和**PR_RECIPIENT_TYPE**。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用方传入的**ADRLIST**结构的大小可能与 MAPI 返回的结构不同。 为**ADRLIST**结构分配内存时, 请单独为每个[SPropValue](spropvalue.md)结构分配内存。 
  
使用指向传递给[ABProviderInit](abproviderinit.md)函数的 MAPI 内存分配函数的指针来分配内存。 使用**ADRLIST**的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数和**ADRLIST**中的**ADRENTRY**结构中的每个属性值结构分配内存。 
  
如果**address**必须返回一个更大的**ADRLIST**结构, 或者如果您为_lppAdrList_传递了 NULL, 则**address**将释放原始结构并分配一个新的结构。 **Address**还会在**ADRLIST**结构中分配其他属性值结构, 并根据需要释放旧的属性。 有关如何为**ADRLIST**结构管理内存的详细信息, 请参阅[管理内存用于 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。
  
 如果在_lpAdrParms_参数的**ADRPARM**结构中设置了 DIALOG_SDI 标志, 则立即返回**Address** 。 
  
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

