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
ms.openlocfilehash: 319c932862615e063a02ffac07e5541b1b20ac7e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415913"
---
# <a name="adrlist"></a>ADRLIST

**适用于**：Outlook 2013 | Outlook 2016 
  
描述属于一个或多个收件人的零个或多个属性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏:  <br/> |[CbADRLIST](cbadrlist.md)、 [CbNewADRLIST](cbnewadrlist.md)、 [CbNewADRLIST](cbnewadrlist.md) <br/> |
   
```cpp
typedef struct _ADRLIST
{
  ULONG cEntries;
  ADRENTRY aEntries[MAPI_DIM];
} ADRLIST, FAR *LPADRLIST;

```

## <a name="members"></a>Members

**cEntries**
  
> 由**aEntries**成员指定的数组中的条目数。 
    
**aEntries**
  
> [ADRENTRY](adrentry.md)结构的数组, 每个收件人一个结构。 
    
## <a name="remarks"></a>说明

**ADRLIST**结构包含一个或多个**ADRENTRY**结构, 每个结构描述收件人的属性。 收件人可以解析。 这意味着它在其属性值的数组中缺少条目标识符。 已解析的收件人意味着将包含 " **\_PR ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))" 属性。 通常, 解析的收件人还具有电子邮件地址**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 属性。 但是, 电子邮件地址不是必需的。 例如, 使用**ADRLIST**结构来描述收件人列表中的传出邮件和 MAPI, 以显示通讯簿中的条目。 
  
**ADRLIST**结构类似于[SRowSet](srowset.md)结构用于表示表中的行的结构。 事实上, 这两个结构设计为可互换使用。 两者都包含描述一组属性和数组中值的计数的结构数组。 而在**ADRLIST**结构中, 数组包含[ADRENTRY](adrentry.md)结构, 在**SRowSet**结构中, 数组包含[SRow](srow.md)结构。 **ADRENTRY**结构和**SRow**结构在布局中相同。 由于**ADRLIST**和**SRowSet**结构遵循相同的分配规则, 从通讯簿容器的 "内容" 表中检索到的**SRowSet**结构可以强制转换为**ADRLIST**结构并按如下方式使用。 
  
下图显示了**ADRLIST**结构的布局。 
  
**ADRLIST 组件**
  
![ADRLIST 组件](media/amapi_18.gif "ADRLIST 组件")
  
**ADRLIST**结构中的**ADRENTRY**和[SPropValue](spropvalue.md)部分必须独立于其他部件进行分配和释放。 也就是说, 在**ADRENTRY**结构的内存已分配并在**ADRENTRY**结构释放之前释放之后, 必须单独分配每个**SPropValue**结构。 处理内存的独立性使得收件人和单个收件人属性可以从地址列表中随意添加或删除。 
  
必须使用[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIFreeBuffer](mapifreebuffer.md)函数来分配和释放**ADRLIST**结构及其所有部分。 
  
如果收件人列表太大而无法装入内存, 客户端可以调用[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法来处理列表的子集。 在这种情况下, 客户端不应使用通讯簿常见的对话框。 
  
有关如何为**ADRENTRY**结构分配内存的详细信息, 请参阅[管理内存中的 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。 
  
## <a name="see-also"></a>另请参阅

- [ADRENTRY](adrentry.md)  
- [CbNewADRLIST](cbnewadrlist.md) 
- [IMessage::ModifyRecipients](imessage-modifyrecipients.md) 
- [SRowSet](srowset.md)
- [MAPI 结构](mapi-structures.md)

