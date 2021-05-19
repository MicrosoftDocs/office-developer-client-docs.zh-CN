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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410432"
---
# <a name="srow"></a>SRow

**适用于**：Outlook 2013 | Outlook 2016 
  
描述表中包含特定对象的选定属性的行。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 填充字节以正确对齐 **lpProps** 成员指向的属性值。 
    
**cValues**
  
> lpProps 指向的 **属性值计数**。 
    
**lpProps**
  
> 指向描述行中列的属性值的 [SPropValue](spropvalue.md) 结构的数组的指针。 
    
## <a name="remarks"></a>备注

**SRow** 结构描述表格中的行。 它包含在表 [通知TABLE_NOTIFICATION](table_notification.md) 中。 
  
**SRow** 结构用于以下方法： 
  
- [IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)
    
- [IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md)
    
- [IMAPITable::QueryRows](imapitable-queryrows.md)
    
- [IMAPITable::ExpandRow](imapitable-expandrow.md)
    
- [ITableData ：IUnknown](itabledataiunknown.md) (许多方法)  
    
- [FBadRowSet](fbadrowset.md)
    
- [FreeProws](freeprows.md)
    
- [HrQueryAllRows](hrqueryallrows.md)
    
当需要描述多个行时，使用 [SRowSet](srowset.md) 结构。 **SRowSet** 结构包含一个 **SRow** 结构数组和该数组中的结构计数。 
  
下图显示了 SRow 和 **SRowSet** 数据结构之间的关系。 
  
**SRow 和 SRowSet 之间的关系**
  
![SRow 和 SRowSet](media/amapi_17.gif "之间的关系 SRow 和 SRowSet 之间的关系")
  
**SRow** 结构的定义与 [ADRENTRY](adrentry.md) 结构相同。 因此，收件人表的一行和地址列表中的条目可以处理相同。 
  
有关应该如何分配 **SRow** 结构的内存的信息，请参阅 [管理 ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)。
  
## <a name="see-also"></a>另请参阅

- [ADRENTRY](adrentry.md)
- [SPropValue](spropvalue.md)
- [SRowSet](srowset.md)
- [TABLE_NOTIFICATION](table_notification.md)
- [MAPI 结构](mapi-structures.md)
- [管理 ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)

