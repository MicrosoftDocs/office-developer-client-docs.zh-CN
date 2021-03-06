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
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[CbADRLIST](cbadrlist.md) [、CbNewADRLIST、CbNewADRLIST](cbnewadrlist.md) [](cbnewadrlist.md) <br/> |
   
```cpp
typedef struct _ADRLIST
{
  ULONG cEntries;
  ADRENTRY aEntries[MAPI_DIM];
} ADRLIST, FAR *LPADRLIST;

```

## <a name="members"></a>Members

**cEntries**
  
> **aEntries** 成员指定的数组中的条目计数。 
    
**aEntries**
  
> [ADRENTRY](adrentry.md)结构数组，每个收件人一个结构。 
    
## <a name="remarks"></a>备注

**ADRLIST** 结构包含一个或多个 **ADRENTRY** 结构，每个结构描述收件人的属性。 无法解析收件人。 这意味着它在其属性值数组中缺少条目标识符。 解析的收件人意味着包含 **PR \_ ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。 通常，解析的收件人还有一个电子邮件地址PR_EMAIL_ADDRESS ( [PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 属性。 但是，不需要电子邮件地址。 **例如，ADRLIST** 结构用于描述传出邮件的收件人列表，MAPI 用于显示通讯簿中的条目。 
  
**ADRLIST** 结构类似于 [SRowSet](srowset.md) 结构，用于表示表格中的行的结构。 实际上，这两种结构设计为可以互换使用。 二者都包含一个结构数组，用于描述一组属性和数组中的值计数。 而在 **ADRLIST** 结构中，数组包含 [ADRENTRY](adrentry.md) 结构，而在 **SRowSet** 结构中，数组包含 [SRow](srow.md) 结构。 **ADRENTRY** 结构和 **SRow** 结构在布局中是相同的。 由于 **ADRLIST** 和 **SRowSet** 结构遵循相同的分配规则，因此从通讯簿容器的内容表检索到的 **SRowSet** 结构可以强制转换到 **ADRLIST** 结构，并按如下方式使用。 
  
下图显示了 **ADRLIST** 结构的布局。 
  
**ADRLIST 组件**
  
![ADRLIST 组件](media/amapi_18.gif "ADRLIST 组件")
  
**ADRLIST 结构中 ADRENTRY** 和 [SPropValue](spropvalue.md)部分必须独立于其他部分进行分配和释放。  也就是说，在释放 **ADRENTRY** 结构之前，分配并释放 **ADRENTRY** 结构的内存后，必须单独分配每个 **SPropValue** 结构。 处理内存时这种独立性允许从地址列表中自由添加或删除收件人和各个收件人属性。 
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)和 [MAPIFreeBuffer](mapifreebuffer.md)函数必须用于分配和释放 **ADRLIST** 结构及其所有部分。 
  
如果收件人列表太大，无法容纳在内存中，则客户端可以调用 [IMessage：：ModifyRecipients](imessage-modifyrecipients.md) 方法以使用列表的子集。 在这种情况下，客户端不应使用通讯簿公用对话框。 
  
若要详细了解如何为 **ADRENTRY** 结构分配内存，请参阅管理 [ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)。 
  
## <a name="see-also"></a>另请参阅

- [ADRENTRY](adrentry.md)  
- [CbNewADRLIST](cbnewadrlist.md) 
- [IMessage::ModifyRecipients](imessage-modifyrecipients.md) 
- [SRowSet](srowset.md)
- [MAPI 结构](mapi-structures.md)

