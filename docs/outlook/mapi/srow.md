---
title: SRow
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SRow
api_type:
- COM
ms.assetid: 369c2d5c-8c2b-4314-9cb2-aaa89580aa2b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2e75bc6f8e14258787a6c9d80dfbf6334ec698b4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336512"
---
# <a name="srow"></a>SRow

**适用于**：Outlook 2013 | Outlook 2016 
  
描述包含特定对象的选定属性的表中的行。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _SRow
{
  ULONG ulAdrEntryPad;
  ULONG cValues;
  LPSPropValue lpProps;
} SRow, FAR *LPSRow;

```

## <a name="members"></a>Members

**ulAdrEntryPad**
  
> 用于正确对齐**lpProps**成员所指向的属性值的填充字节数。 
    
**cValues**
  
> 由**lpProps**指向的属性值的计数。 
    
**lpProps**
  
> 指向描述行中各列的属性值的[SPropValue](spropvalue.md)结构数组的指针。 
    
## <a name="remarks"></a>注解

**SRow**结构描述表格中的行。 它包含在表通知附带的[TABLE_NOTIFICATION](table_notification.md)结构中。 
  
在以下方法中使用**SRow**结构: 
  
- [IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)
    
- [IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md)
    
- [IMAPITable::QueryRows](imapitable-queryrows.md)
    
- [IMAPITable::ExpandRow](imapitable-expandrow.md)
    
- [ITableData: IUnknown](itabledataiunknown.md)(多个方法) 
    
- [FBadRowSet](fbadrowset.md)
    
- [FreeProws](freeprows.md)
    
- [HrQueryAllRows](hrqueryallrows.md)
    
如果需要描述多行, 则使用[SRowSet](srowset.md)结构。 **SRowSet**结构包含**SRow**结构的数组和数组中的结构计数。 
  
下图显示了**SRow**和**SRowSet**数据结构之间的关系。 
  
**SRow 和 SRowSet 之间的关系**
  
![SRow 和 SRowSet 之间的关系](media/amapi_17.gif "SRow 和 SRowSet 之间的关系")
  
**SRow**结构的定义与[ADRENTRY](adrentry.md)结构相同。 因此, 收件人表的行和地址列表中的条目可以被视为相同。 
  
有关应如何分配**SRow**结构的内存的信息, 请参阅[管理内存 for ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。
  
## <a name="see-also"></a>另请参阅

- [ADRENTRY](adrentry.md)
- [SPropValue](spropvalue.md)
- [SRowSet](srowset.md)
- [TABLE_NOTIFICATION](table_notification.md)
- [MAPI 结构](mapi-structures.md)
- [管理 ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)

