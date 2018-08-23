---
title: ADRLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ADRLIST
api_type:
- COM
ms.assetid: 85f0d8a5-6dd3-4f33-b31a-246d286d6286
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 87b91b66807ce79533029a8d5b5c4956bc4d5ce9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565765"
---
# <a name="adrlist"></a>ADRLIST

**适用于**： Outlook 2013 |Outlook 2016 
  
介绍属于一个或多个收件人的零个或多个属性。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[CbADRLIST](cbadrlist.md)， [CbNewADRLIST](cbnewadrlist.md)， [CbNewADRLIST](cbnewadrlist.md) <br/> |
   
```cpp
typedef struct _ADRLIST
{
  ULONG cEntries;
  ADRENTRY aEntries[MAPI_DIM];
} ADRLIST, FAR *LPADRLIST;

```

## <a name="members"></a>Members

**cEntries**
  
> 指定由**aEntries**成员的数组中的条目的计数。 
    
**aEntries**
  
> [ADRENTRY](adrentry.md)结构数组，每个收件人的一个结构。 
    
## <a name="remarks"></a>注解

**ADRLIST**结构包含一个或多个**ADRENTRY**结构，每个描述收件人的属性。 收件人可以是未解析。 这意味着缺少的属性值的数组中的项标识符。 解析的收件人是指**PR\_ENTRYID**包括的 ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。 通常，已解析的收件人也有电子邮件地址的**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 属性。 但是，不需要的电子邮件地址。 **ADRLIST**结构用于，例如，描述传出消息和 MAPI 在通讯簿中显示的项的收件人列表。 
  
**ADRLIST**结构类似于[SRowSet](srowset.md)结构用于表示表中的行的结构。 实际上，这些两个结构设计，以便可以交替使用它们。 同时包含数组的结构，描述了一组属性和值数组中的计数。 而在**ADRLIST**结构中，该数组包含[ADRENTRY](adrentry.md)结构， **SRowSet**结构数组中的包含[SRow](srow.md)结构。 **ADRENTRY**结构和**SRow**结构是布局中相同的。 因为**ADRLIST**和**SRowSet**结构遵循相同的分配规则，则可以强制转换为**ADRLIST**结构从通讯簿容器内容表中检索**SRowSet**结构，并将其原样使用。 
  
下图显示了**ADRLIST**结构的布局。 
  
**ADRLIST 组件**
  
![ADRLIST 组件](media/amapi_18.gif "ADRLIST 组件")
  
**ADRLIST**结构中的**ADRENTRY**和[SPropValue](spropvalue.md)部分必须分配，并可以独立于其他部件释放。 即，每个**SPropValue**结构必须分配单独分配内存**ADRENTRY**结构并将其释放之前释放**ADRENTRY**结构之后。 处理内存此独立性允许收件人和单个收件人属性自由地添加或从地址列表中删除。 
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIFreeBuffer](mapifreebuffer.md)函数必须用于分配和释放**ADRLIST**结构和所有部件。 
  
如果太长而在内存中的收件人列表，客户端可以调用[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法用于列表的子集。 客户端不应使用地址簿常见对话框在此情况下。 
  
有关如何为**ADRENTRY**结构分配内存的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。 
  
## <a name="see-also"></a>另请参阅

- [ADRENTRY](adrentry.md)  
- [CbNewADRLIST](cbnewadrlist.md) 
- [IMessage::ModifyRecipients](imessage-modifyrecipients.md) 
- [SRowSet](srowset.md)
- [MAPI 结构](mapi-structures.md)

