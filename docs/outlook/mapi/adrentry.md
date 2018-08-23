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
ms.openlocfilehash: f3a62f6783e3b1a0a0423a08c7f5e866b42b81f6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569174"
---
# <a name="adrentry"></a>ADRENTRY

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
介绍属于收件人的零个或多个属性。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 属性值数组中的属性数目所指的**rgPropVals**成员。 **CValues**成员可以为零。 
    
 **rgPropVals**
  
> 指向收件人描述属性的属性值数组。 **RgPropVals**成员可以为 NULL。 
    
## <a name="remarks"></a>注解

**ADRENTRY**结构介绍属于单个收件人的属性。 通常用来描述收件人的属性包括： 
  
 **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
  
 **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
  
 **PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))
  
 **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
  
当条目标识符或**PR_ENTRYID**属性显示收件人[SPropValue](spropvalue.md)数组中时，这表示收件人已解决。 客户端调用[IAddrBook::ResolveName](iaddrbook-resolvename.md)方法，以确保已解决的传出邮件的收件人列表中的所有收件人。 只有解析的收件人可以发送消息。 
  
 **ADRENTRY**结构通常被组合为**aEntries** [ADRLIST](adrlist.md)结构的成员的数组。 
  
 **ADRENTRY**结构和[SRow](srow.md)结构是相同的因为都包含保留的成员，属性值的数组和值数组中的计数。 组合**ADRENTRY**结构以形成**ADRLIST**结构的**aEntries**成员，而组合**SRow**结构以形成[SRowSet](srowset.md)结构的**aRow**成员。 两种类型的结构遵循相同的分配规则，这意味着可以强制转换为**ADRLIST**结构和原样使用从通讯簿容器内容表中检索**SRowSet**结构。 
  
**ADRENTRY**结构可以为空。 例如，收件人被删除时，包含在**ADRLIST**结构**IAddrBook::Address**将调用_lppAdrList_参数指向**ADRENTRY**结构可以为空。 
  
有关如何为**ADRENTRY**结构分配内存的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。
  
## <a name="see-also"></a>另请参阅



[IAddrBook::Address](iaddrbook-address.md)
  
[IMessage::ModifyRecipients](imessage-modifyrecipients.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[ADRLIST](adrlist.md)
  
[SRow](srow.md)
  
[SRowSet](srowset.md)


[MAPI 结构](mapi-structures.md)

