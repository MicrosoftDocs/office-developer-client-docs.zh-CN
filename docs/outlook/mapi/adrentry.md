---
title: ADRENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ADRENTRY
api_type:
- COM
ms.assetid: 5fa091a4-3a84-4881-91b3-e34fd9ca6f38
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 36e0218c9e4e312a138bef7517242f74079212c4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421436"
---
# <a name="adrentry"></a>ADRENTRY

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述属于收件人的零个或多个属性。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _ADRENTRY
{
  ULONG ulReserved1;
  ULONG cValues;
  LPSPropValue rgPropVals;
} ADRENTRY, FAR *LPADRENTRY;

```

## <a name="members"></a>Members

 **ulReserved1**
  
> 保留;必须为零。
    
 **cValues**
  
> **rgPropVals** 成员指向的属性值数组中的属性计数。 **cValues** 成员可以是零。 
    
 **rgPropVals**
  
> 指向描述收件人属性的属性值数组的指针。 **rgPropVals** 成员可以是 NULL。 
    
## <a name="remarks"></a>备注

**ADRENTRY** 结构描述属于单个收件人的属性。 通常用于描述收件人的属性包括： 
  
 **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
  
 **PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) 
  
 **PR_EMAIL_ADDRESS (** [PidTagEmailAddress)](pidtagemailaddress-canonical-property.md)
  
 **PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) 
  
当条目标识符 **或** PR_ENTRYID属性出现在收件人 [的 SPropValue](spropvalue.md) 数组中时，这表示收件人已解析。 客户端调用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md) 方法，以确保已解析传出邮件的收件人列表中的所有收件人。 只有解析的收件人才能随邮件一起发送。 
  
 **ADRENTRY** 结构通常组合在一起，形成 [ADRLIST](adrlist.md)结构的 **aEntries** 成员数组。 
  
 **ADRENTRY** 结构和 [SRow](srow.md) 结构是相同的，因为它们都包含保留成员、属性值数组和数组中的值计数。 而 **ADRENTRY** 结构组合形成 **ADRLIST** 结构的 **aEntries** 成员，**而 SRow** 结构组合在一起形成 **SRowSet** 结构的 [Row](srowset.md)成员。 这两种类型的结构都遵循相同的分配规则，这意味着从通讯簿容器的内容表检索到的 **SRowSet** 结构可以转换到 **ADRLIST** 结构，并按如下方式使用。 
  
**ADRENTRY** 结构可以为空。 例如，在删除收件人时，包含在对 **IAddrBook：：Address** 的调用中 _lppAdrList_ 参数指向的 **ADRLIST** 结构的 **ADRENTRY** 结构可能为空。 
  
若要详细了解如何为 **ADRENTRY** 结构分配内存，请参阅管理 [ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)。
  
## <a name="see-also"></a>另请参阅



[IAddrBook::Address](iaddrbook-address.md)
  
[IMessage::ModifyRecipients](imessage-modifyrecipients.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[ADRLIST](adrlist.md)
  
[SRow](srow.md)
  
[SRowSet](srowset.md)


[MAPI 结构](mapi-structures.md)

