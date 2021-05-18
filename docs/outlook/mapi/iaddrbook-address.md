---
title: IAddrBookAddress
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.Address
api_type:
- COM
ms.assetid: ef2112c7-35cd-4106-ad18-a45e1dbe07d6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c2546fc990169526361f2c452c50212123d8284d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407905"
---
# <a name="iaddrbookaddress"></a>IAddrBook::Address

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示 Outlook 通讯簿对话框。 
  
```cpp
HRESULT Address(
  ULONG_PTR FAR * lpulUIParam,
  LPADRPARM lpAdrParms,
  LPADRLIST FAR * lppAdrList
);
```

## <a name="parameters"></a>参数

 _lpulUIParam_
  
> [in， out]指向对话框父窗口的句柄的指针。 在输入时，必须始终传递窗口句柄。 在输出时，如果 _lpAdrParms_ 参数的 **ulFlags** 成员设置为 DIALOG_SDI，则返回无模式对话框的窗口句柄。 请参阅注解。 
    
 _lpAdrParms_
  
> [in， out]指向控制地址对话框的显示和行为 [的 ADRPARM](adrparm.md) 结构的指针。 
    
 _lppAdrList_
  
> [in， out]指向包含收件人信息的 [ADRLIST](adrlist.md) 结构的指针的指针。 在输入时，此参数可以是 NULL 或指向有效的指针。 在输出上，此参数指向指向有效收件人信息的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功显示公用地址对话框。
    
## <a name="remarks"></a>备注

如果 _lpAdrParms_ 参数的 **ulFlags** 成员设置为 DIALOG_SDI预期在输出上返回无模式对话框的窗口句柄，则 Outlook 中将忽略该成员;对话框的模式版本始终显示在非 Outlook 客户端中。 
  
MAPI 通过 _lppAdrList_ 参数传递回调用方的 **ADRLIST** 结构包含 [ADRENTRY](adrentry.md)结构数组，每个收件人一个结构。 当传递到 _lpMods_ 参数中的传出邮件 [的 IMessage：：ModifyRecipients](imessage-modifyrecipients.md)方法时，**可以使用 ADRLIST** 结构更新其收件人列表。 
  
**ADRLIST** 结构中的每个 **ADRENTRY** 结构包含零个或多个 [SPropValue](spropvalue.md)结构，一个针对收件人的每个属性集的结构。 使用 Address 方法呈现的对话框删除收件人时，可以有零个 **SPropValue** 结构。 当存在一个或多个 **SPropValue** 结构时，相应的 **ADRENTRY** 结构用于添加或更新收件人。 可以解析收件人，这表示其中一个 **SPropValue** 结构描述收件人的 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性或 unresolved，这表示 **缺少 PR_ENTRYID** 属性。 
  
除了 **PR_ENTRYID**，已解析的收件人还包括以下属性：
  
- **PR_RECIPIENT_TYPE (** [PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 
    
- **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
    
- **PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) 
    
- **PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 
    
调用方 **传递的 ADRLIST** 结构的大小可能不同于 MAPI 返回的结构。 如果 MAPI 必须返回更大的 **ADRLIST** 结构，它将释放原始结构并分配一个新结构。 为 **ADRLIST** 结构分配内存时，请单独为每个 **SPropValue** 结构分配内存。 若要详细了解如何分配和释放 **ADRLIST** 结构，请参阅管理 [ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)
  
 **如果在** _lpAdrParms_ 参数的 **ADRPARM** 结构的 **ulFlags** 成员中设置了 DIALOG_SDI 标志，则 Address 将立即返回。 对于DIALOG_SDI Outlook 客户端，将忽略该标记。 如果DIALOG_SDI，将显示对话框的模式版本，并且不应在  _lpulUIParam_ 中期望指向句柄的指针。
  
 **如果** aDRPARM 的 **ulFlags** 成员在 _lpAdrParms_ 参数中指定了 AB_UNICODEUI，则 Address 支持 **ADRPARM** 结构中的 Unicode 字符字符串，并支持 **ADRLIST** 中的 Unicode 字符字符串。  在 Outlook 通讯簿对话框中显示 Unicode 字符串 (MBCS) 格式转换为多字节字符串。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIStoreFunctions.cpp  <br/> |OpenOtherUsersMailboxFromGal  <br/> |MFCMAPI 使用 **Address** 方法允许用户选择要打开的邮箱。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ADRENTRY](adrentry.md)
  
[ADRLIST](adrlist.md)
  
[ADRPARM](adrparm.md)
  
[FreePadrlist](freepadrlist.md)
  
[FreeProws](freeprows.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMessage::ModifyRecipients](imessage-modifyrecipients.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropValue](spropvalue.md)
  
[SRowSet](srowset.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

