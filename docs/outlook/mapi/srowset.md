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
  
包含 [SRow 结构的](srow.md) 数组。 每个 **SRow** 结构描述表格中的一行。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[CbNewsRowSet](cbnewsrowset.md) [、CbsRowSet](cbsrowset.md) [、SizedsRowSet](sizedsrowset.md) <br/> |
   
```cpp
typedef struct _SRowSet
{
  ULONG cRows;
  SRow aRow[MAPI_DIM];
} SRowSet, FAR *LPSRowSet;

```

## <a name="members"></a>Members

 **cRows**
  
> **ARow 成员** 中的 **SRow 结构** 计数。 
    
 **aRow**
  
> **SRow 结构** 数组。 表格中每一行都有一个结构。 
    
## <a name="remarks"></a>备注

**SRowSet** 结构用于描述表中的多行数据。 **除了以下函数之外，SRowSet** 结构还用于 [IAddrBook、ITableData](iaddrbookimapiprop.md)和 [IMAPITable](imapitableiunknown.md)接口方法： [](itabledataiunknown.md) 
  
- [HrQueryAllRows](hrqueryallrows.md)
    
- [FBadRowSet](fbadrowset.md)
    
- [FreeProws](freeprows.md)
    
 **SRowSet** 结构的定义与 [ADRLIST](adrlist.md) 结构相同，以允许对收件人表的行和地址列表中的条目进行相同的处理。 **SRowSet** 结构和 **ADRLIST** 结构都可以传递到 [IMessage：：ModifyRecipients](imessage-modifyrecipients.md)和 [IAddrBook：：Address 等方法](iaddrbook-address.md)。 
  
此外 **，SRowSet** 结构的内存分配规则与 **ADRLIST 结构** 的规则相同。 总之，行集每一行的 **lpProps** 成员指向的数组中的每个 [SPropValue](spropvalue.md)结构都必须使用 [MAPIAllocateBuffer](mapiallocatebuffer.md)单独分配。 在取消分配其 **SRowSet** 结构之前，还必须使用 [MAPIFreeBuffer](mapifreebuffer.md)解除分配每个属性值结构，以便指向已分配的 **SPropValue** 结构的指针不会丢失。 然后，可以在 **SRowSet** 结构的上下文之外保留和重复使用行的已分配内存。 
  
有关应该如何分配 **SRowSet** 结构的内存的信息，请参阅 [管理 ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)。 
  
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[SPropValue](spropvalue.md)
  
[SRow](srow.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)


[MAPI 结构](mapi-structures.md)

