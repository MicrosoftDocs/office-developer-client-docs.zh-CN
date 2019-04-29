---
title: SRowSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SRowSet
api_type:
- COM
ms.assetid: 7e3761be-afd6-46cb-9a08-25e9016c1241
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 63cef6ef2bb26e8b723c60fe01dd6771aa070ae8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407254"
---
# <a name="srowset"></a>SRowSet

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含[SRow](srow.md)结构的数组。 每个**SRow**结构描述表中的行。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏:  <br/> |[CbNewSRowSet](cbnewsrowset.md)、 [CbSRowSet](cbsrowset.md)、 [SizedSRowSet](sizedsrowset.md) <br/> |
   
```cpp
typedef struct _SRowSet
{
  ULONG cRows;
  SRow aRow[MAPI_DIM];
} SRowSet, FAR *LPSRowSet;

```

## <a name="members"></a>Members

 **cRows**
  
> **aRow**成员中的**SRow**结构的计数。 
    
 **aRow**
  
> **SRow**结构的数组。 表中的每一行都有一个结构。 
    
## <a name="remarks"></a>说明

**SRowSet**结构用于描述表中的多行数据。 除了以下函数之外, 还可以在[IAddrBook](iaddrbookimapiprop.md)、 [ITableData](itabledataiunknown.md)和[IMAPITable](imapitableiunknown.md)接口方法中使用**SRowSet**结构: 
  
- [HrQueryAllRows](hrqueryallrows.md)
    
- [FBadRowSet](fbadrowset.md)
    
- [FreeProws](freeprows.md)
    
 **SRowSet**结构的定义与[ADRLIST](adrlist.md)结构相同, 以允许收件人表的行和地址列表中的条目被视为相同。 **SRowSet**结构和**ADRLIST**结构都可以传递给方法, 如[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)和[IAddrBook:: Address](iaddrbook-address.md)。 
  
此外, 为**SRowSet**结构分配的内存规则与**ADRLIST**结构的规则相同。 总而言之, 必须使用[MAPIAllocateBuffer](mapiallocatebuffer.md)分别分配行集中每行的**lpProps**成员所指向的数组中的每个[SPropValue](spropvalue.md)结构。 在取消分配其**SRowSet**结构之前, 还必须使用[MAPIFreeBuffer](mapifreebuffer.md)释放每个属性值结构, 这样, 指向分配的**SPropValue**结构的指针不会丢失。 然后, 可以保留行的已分配内存, 并在**SRowSet**结构的上下文外部重用它。 
  
有关应如何分配**SRowSet**结构的内存的详细信息, 请参阅[管理内存用于 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。 
  
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[SPropValue](spropvalue.md)
  
[SRow](srow.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)


[MAPI 结构](mapi-structures.md)

