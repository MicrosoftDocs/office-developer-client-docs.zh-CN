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
ms.openlocfilehash: 10f8f2cf44bf1a8e00f8c2b1a76826db5fc07161
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775233"
---
# <a name="iaddrbookaddress"></a>IAddrBook::Address

  
  
**适用于**： Outlook 
  
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
  
> [传入、 传出]指向对话框中的父窗口的句柄的指针。 在输入时，必须始终传递窗口句柄。 输出，如果_lpAdrParms_参数的**ulFlags**成员设置为 DIALOG_SDI，则返回无模式对话框的窗口句柄。 请参阅注解。 
    
 _lpAdrParms_
  
> [传入、 传出]指向控制的演示文稿和行为的地址对话框的[ADRPARM](adrparm.md)结构的指针。 
    
 _lppAdrList_
  
> [传入、 传出]指向[ADRLIST](adrlist.md)结构包含收件人信息的指针的指针。 在输入时，此参数可以为 NULL 或指向一个有效的指针。 输出，此参数是指向对有效收件人信息的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功显示常见的地址对话框。
    
## <a name="remarks"></a>说明

如果_lpAdrParms_参数的**ulFlags**成员设置为 DIALOG_SDI 预见无模式对话框的窗口句柄回报输出，则将被忽略; 在 Outlook 中非 Outlook 客户端中始终显示模式对话框的版本。 
  
**ADRLIST**结构后通过 MAPI 传递给呼叫者通过_lppAdrList_参数包含一个数组[ADRENTRY](adrentry.md)结构，每个收件人的一个结构。 传递给_lpMods_参数中的传出消息的[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法时， **ADRLIST**结构可用于更新其收件人列表。 
  
**ADRLIST**结构中的每个**ADRENTRY**结构包含零个或多个[SPropValue](spropvalue.md)结构、 一个结构收件人设置每个属性。 使用演示者的**地址**方法对话框中删除收件人时，可以是零**SPropValue**结构。 当存在一个或多个**SPropValue**结构时，相应**ADRENTRY**结构用于添加或更新收件人。 收件人可以解析，指示**SPropValue**结构之一描述收件人的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，或无法解析，指示**PR_ENTRYID**属性缺少。 
  
除了**PR_ENTRYID**，已解析的收件人包括以下属性：
  
- **PR_RECIPIENT_TYPE**([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))
    
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
- **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
- **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))
    
传入呼叫者的**ADRLIST**结构可能从结构的 MAPI 返回不同的大小。 如果 MAPI 必须返回较大的**ADRLIST**结构，它释放原始结构，并分配一个新。 当您为**ADRLIST**结构分配内存时，将单独为每个**SPropValue**结构分配内存。 有关如何分配和释放**ADRLIST**结构的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)
  
 **地址**立即返回如果_lpAdrParms_参数中的**ADRPARM**结构的**ulFlags**成员中设置 DIALOG_SDI 标志。 非 Outlook 客户端的情况下，将忽略 DIALOG_SDI 标志。 如果 DIALOG_SDI 将被忽略，将显示模式对话框的版本并不应该在_lpulUIParam_要求的句柄的指针。
  
 **地址** **ADRPARM**结构中支持 Unicode 字符的字符串，如果在**ADRPARM**的**ulFlags**成员_lpAdrParms_参数中指定 AB_UNICODEUI 而它支持**中的 Unicode 字符串ADRLIST**。 Unicode 字符串转换为多字节字符的字符串 (MBCS) 格式显示在 Outlook 通讯簿对话框之前。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIStoreFunctions.cpp  <br/> |OpenOtherUsersMailboxFromGal  <br/> |MFCMAPI 使用**地址**方法允许用户选择要打开的邮箱。  <br/> |
   
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

