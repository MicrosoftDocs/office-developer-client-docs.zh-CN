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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330224"
---
# <a name="adrentry"></a>ADRENTRY

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述属于收件人的零个或多个属性。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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
  
> 保留必须为零。
    
 **cValues**
  
> 属性值数组中由**rgPropVals**成员指向的属性的计数。 **cValues**成员可以为零。 
    
 **rgPropVals**
  
> 指向描述收件人属性的属性值数组的指针。 **rgPropVals**成员可以为 NULL。 
    
## <a name="remarks"></a>注解

**ADRENTRY**结构描述属于单个收件人的属性。 通常用于描述收件人的属性包括以下各项: 
  
 **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
  
 **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
  
 **PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))
  
 **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
  
当收件人的[SPropValue](spropvalue.md)数组中出现条目标识符或**PR_ENTRYID**属性时, 表示收件人已解决。 客户端调用[IAddrBook:: ResolveName](iaddrbook-resolvename.md)方法, 以确保已解决传出邮件的收件人列表中的所有收件人。 只有解析的收件人可以与邮件一起发送。 
  
 **ADRENTRY**结构通常组合在一起构成[ADRLIST](adrlist.md)结构的**aEntries**成员的数组。 
  
 **ADRENTRY**结构和[SRow](srow.md)结构相同, 因为它们都包含一个保留成员、属性值的数组和数组中的值的计数。 虽然**ADRENTRY**结构组合起来构成了**ADRLIST**结构的**aEntries**成员, 但**SRow**结构组合在一起构成了[aRow](srowset.md)结构的**SRowSet**成员。 这两种类型的结构都遵循相同的分配规则, 暗指从通讯簿容器的 "内容" 表中检索到的**SRowSet**结构可以转换为**ADRLIST**结构并按如下方式使用。 
  
**ADRENTRY**结构可以为空。 例如, 在删除收件人时, **ADRLIST**结构中包含的结构中包含的**ADRENTRY**结构, 在对**IAddrBook:: Address**的调用中, 该结构指向的_lppAdrList_参数可能为空。 
  
有关如何为**ADRENTRY**结构分配内存的详细信息, 请参阅[管理内存中的 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。
  
## <a name="see-also"></a>另请参阅



[IAddrBook::Address](iaddrbook-address.md)
  
[IMessage::ModifyRecipients](imessage-modifyrecipients.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[ADRLIST](adrlist.md)
  
[SRow](srow.md)
  
[SRowSet](srowset.md)


[MAPI 结构](mapi-structures.md)

