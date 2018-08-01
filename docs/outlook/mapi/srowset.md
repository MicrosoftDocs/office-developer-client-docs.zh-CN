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
ms.openlocfilehash: 5c634fe200dde4bfe6f190f8bfa9e5dfa0868db4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778886"
---
# <a name="srowset"></a>SRowSet

  
  
**适用于**： Outlook 
  
包含一个[SRow](srow.md)结构数组。 每个**SRow**结构介绍表中的行。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[CbNewSRowSet](cbnewsrowset.md)， [CbSRowSet](cbsrowset.md)， [SizedSRowSet](sizedsrowset.md) <br/> |
   
```cpp
typedef struct _SRowSet
{
  ULONG cRows;
  SRow aRow[MAPI_DIM];
} SRowSet, FAR *LPSRowSet;

```

## <a name="members"></a>Members

 **cRows**
  
> **SRow**结构**aRow**成员中的计数。 
    
 **aRow**
  
> **SRow**结构的数组。 没有一个结构表中的各行。 
    
## <a name="remarks"></a>说明

**SRowSet**结构用于描述多个表中的数据行。 **SRowSet**结构[IAddrBook](iaddrbookimapiprop.md)、 [ITableData](itabledataiunknown.md)和[IMAPITable](imapitableiunknown.md)接口方法，除了以下函数中使用： 
  
- [HrQueryAllRows](hrqueryallrows.md)
    
- [FBadRowSet](fbadrowset.md)
    
- [FreeProws](freeprows.md)
    
 定义**SRowSet**结构[ADRLIST](adrlist.md)结构，以允许将地址列表中的收件人的表和项的行视为相同的相同。 **SRowSet**结构和**ADRLIST**结构可以传递给[IAddrBook::Address](iaddrbook-address.md) [IMessage::ModifyRecipients](imessage-modifyrecipients.md)等的方法。 
  
此外， **SRowSet**结构的内存分配的规则都与**ADRLIST**结构相同。 总之，必须单独使用[MAPIAllocateBuffer](mapiallocatebuffer.md)分配指向由**lpProps**成员的每一行的行中设置该数组中每个[SPropValue](spropvalue.md)结构。 此外必须使用[MAPIFreeBuffer](mapifreebuffer.md)其**SRowSet**结构的释放之前，以便不会丢失指向分配**SPropValue**结构释放每个属性值结构。 行的分配内存可以随后可保留并重用**SRowSet**结构的上下文之外。 
  
有关应分配的内存**SRowSet**结构的方式的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。 
  
## <a name="see-also"></a>另请参阅



[ADRLIST](adrlist.md)
  
[SPropValue](spropvalue.md)
  
[SRow](srow.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)


[MAPI 结构](mapi-structures.md)

