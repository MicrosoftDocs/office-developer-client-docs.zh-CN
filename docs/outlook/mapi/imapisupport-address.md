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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407317"
---
# <a name="imapisupportaddress"></a>IMAPISupport::Address

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示公用地址对话框。 
  
```cpp
HRESULT Address(
  ULONG_PTR FAR * lpulUIParam,
  LPADRPARM lpAdrParms,
  LPADRLIST FAR * lppAdrList
);
```

## <a name="parameters"></a>参数

 _lpulUIParam_
  
> [in， out]指向对话框父窗口句柄的指针。 在输入时，必须始终传递窗口句柄。 输出时，如果在 _lpAdrParms_ 参数指向的 [ADRPARM](adrparm.md)结构中设置了 DIALOG_SDI 标志，则返回无模式对话框的窗口句柄。 
    
 _lpAdrParms_
  
> [in， out]指向控制地址对话框的显示和行为 **的 ADRPARM** 结构的指针。 
    
 _lppAdrList_
  
> [in， out]指向指向地址列表的指针的指针。 在输入时，此列表是邮件中的收件人当前列表或 NULL（如果不存在此类列表）。 在输出上  _，lppAdrList_ 指向更新的邮件收件人列表。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功显示地址对话框。
    
## <a name="remarks"></a>备注

**为通讯簿提供程序支持对象实现 IMAPISupport：：Address** 方法。 通讯簿提供商调用 **Address** 来创建或更新邮件收件人列表。 
  
每个收件人在 [ADRENTRY](adrentry.md)结构中进行描述，该结构包含在 _lppAdrList_ 参数指向的 [ADRLIST](adrlist.md)结构中。 **ADRENTRY** 结构包含收件人属性值的数组，其中一个为收件人的类型，PR_RECIPIENT_TYPE ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性。  可以将 **此 ADRLIST** 结构传递给客户端，以在 [调用 IMessage：：ModifyRecipients](imessage-modifyrecipients.md)时用作 _lpMods_ 参数。
  
**ADRLIST** 结构中的每个收件人都可以解析，这表示它的一个属性值是 **它的 PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，或者未解析，这表示 **缺少 PR_ENTRYID** 属性。 
  
除了 **PR_ENTRYID**，已解析的收件人还包括以下属性：
  
- **PR_RECIPIENT_TYPE**
    
- **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
    
- **PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) 
    
- **PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 
    
未解析的收件人通常仅包括 **PR_DISPLAY_NAME** 和 **PR_RECIPIENT_TYPE**。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用方 **传递的 ADRLIST** 结构的大小可能不同于 MAPI 返回的结构。 为 **ADRLIST** 结构分配内存时，请单独为每个 [SPropValue](spropvalue.md) 结构分配内存。 
  
使用传递给 [ABProviderInit](abproviderinit.md) 函数的 MAPI 内存分配函数的指针分配内存。 使用 ADRLIST [的 MAPIAllocateBuffer](mapiallocatebuffer.md) 函数和 **ADRLIST** **中的 ADRENTRY** 结构的每个属性值结构分配 **内存**。 
  
如果 **Address** 必须返回更大的 **ADRLIST** 结构，或者如果为 _lppAdrList_ 传递了 NULL，Address 将释放原始结构并分配一个新结构。  **Address** 还会在 **ADRLIST** 结构中分配其他属性值结构，并在适当时释放旧属性值结构。 For more information about how memory is managed for **ADRLIST** structures， see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).
  
 **如果在** _lpAdrParms_ 参数的 **ADRPARM** 结构中设置了 DIALOG_SDI 标志，则 Address 将立即返回。 
  
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

