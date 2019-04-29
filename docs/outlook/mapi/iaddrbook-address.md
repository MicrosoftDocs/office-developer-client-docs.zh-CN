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
  
显示 "Outlook 通讯簿" 对话框。 
  
```cpp
HRESULT Address(
  ULONG_PTR FAR * lpulUIParam,
  LPADRPARM lpAdrParms,
  LPADRLIST FAR * lppAdrList
);
```

## <a name="parameters"></a>参数

 _lpulUIParam_
  
> [in, out]指向对话框父窗口的句柄的指针。 在输入时, 必须始终传递窗口句柄。 在输出时, 如果_lpAdrParms_参数的**ulFlags**成员设置为 DIALOG_SDI, 则将返回无模式对话框的窗口句柄。 请参阅注解。 
    
 _lpAdrParms_
  
> [in, out]指向控制 "地址" 对话框的外观和行为的[ADRPARM](adrparm.md)结构的指针。 
    
 _lppAdrList_
  
> [in, out]指向包含收件人信息的[ADRLIST](adrlist.md)结构的指针的指针。 在输入时, 此参数可以为 NULL 或指向有效指针。 在输出时, 此参数指向有效收件人信息的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功显示 "常用地址" 对话框。
    
## <a name="remarks"></a>说明

如果_lpAdrParms_参数的**ulFlags**成员设置为 DIALOG_SDI 在输出时预测无模式对话框的窗口句柄的返回, 则在 Outlook 中将被忽略;对话框的模式版本始终显示在非 Outlook 客户端中。 
  
MAPI 通过_lppAdrList_参数传递给呼叫者的**ADRLIST**结构包含一个[ADRENTRY](adrentry.md)结构数组, 每个收件人一个结构。 当传递给_lpMods_参数中的传出邮件的[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法时, 可以使用**ADRLIST**结构更新其收件人列表。 
  
**ADRLIST**结构中的每个**ADRENTRY**结构都包含零个或多个[SPropValue](spropvalue.md)结构, 为收件人的每个属性集设置一个结构。 当**Address**方法所显示的对话框用于删除收件人时, 可以有零个**SPropValue**结构。 如果有一个或多个**SPropValue**结构, 相应的**ADRENTRY**结构将用于添加或更新收件人。 可以解析收件人, 这表示**SPropValue**结构中的一个结构描述了收件人的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性或未解析, 这表示**PR_ENTRYID**属性是尚. 
  
除了**PR_ENTRYID**, 解析的收件人还包含以下属性:
  
- **PR_RECIPIENT_TYPE**([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))
    
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
- **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
- **PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))
    
调用方传入的**ADRLIST**结构的大小可能与 MAPI 返回的结构不同。 如果 MAPI 必须返回一个更大的**ADRLIST**结构, 它将释放原始结构并分配一个新的结构。 为**ADRLIST**结构分配内存时, 请单独为每个**SPropValue**结构分配内存。 有关如何分配和释放**ADRLIST**结构的详细信息, 请参阅[管理内存用于 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)
  
 如果在_lpAdrParms_参数的**ADRPARM**结构的**ulFlags**成员中设置 DIALOG_SDI 标志, 则会立即返回**Address** 。 对于非 Outlook 客户端, 将忽略 DIALOG_SDI 标志。 如果忽略 DIALOG_SDI, 则将显示对话框的模式版本, 并且在_lpulUIParam_中不应出现指向句柄的指针。
  
 **地址**支持**ADRPARM**结构中的 unicode 字符字符串 (如果 AB_UNICODEUI 是在_lpAdrParms_参数中的**ADRPARM**的**ulFlags**成员中指定的), 并且它支持中**的 unicode 字符字符串ADRLIST**。 在将 Unicode 字符串显示在 "Outlook 通讯簿" 对话框中之前, 它们将转换为多字节字符字符串 (MBCS) 格式。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIStoreFunctions  <br/> |OpenOtherUsersMailboxFromGal  <br/> |MFCMAPI 使用**Address**方法, 以允许用户选择要打开的邮箱。  <br/> |
   
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

