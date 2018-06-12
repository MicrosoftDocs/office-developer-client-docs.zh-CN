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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 8b4e090b3dd6bf8ecd2517dee57093106147e22d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778873"
---
# <a name="srow"></a>SRow

**适用于**： Outlook 
  
介绍包含特定对象的选定的属性表中的行。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SRow
{
  ULONG ulAdrEntryPad;
  ULONG cValues;
  LPSPropValue lpProps;
} SRow, FAR *LPSRow;

```

## <a name="members"></a>成员

**ulAdrEntryPad**
  
> 填充字节正确地对齐的属性值指向**lpProps**成员。 
    
**cValues**
  
> 属性值所指的**lpProps**计数。 
    
**lpProps**
  
> 指向一个[SPropValue](spropvalue.md)结构描述行中的列的属性值的数组。 
    
## <a name="remarks"></a>备注

**SRow**结构描述表中的行。 它包含附带表通知的[TABLE_NOTIFICATION](table_notification.md)结构中。 
  
**SRow**结构使用以下方法： 
  
- [IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)
    
- [IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md)
    
- [IMAPITable::QueryRows](imapitable-queryrows.md)
    
- [IMAPITable::ExpandRow](imapitable-expandrow.md)
    
- [ITableData: IUnknown](itabledataiunknown.md)（许多方法） 
    
- [FBadRowSet](fbadrowset.md)
    
- [FreeProws](freeprows.md)
    
- [HrQueryAllRows](hrqueryallrows.md)
    
当多个行需要在所述时，请使用[SRowSet](srowset.md)结构。 **SRowSet**结构包含数组**SRow**结构和结构数组中的计数。 
  
下图显示**SRow**和**SRowSet**数据结构之间的关系。 
  
**SRow 和 SRowSet 之间的关系**
  
![SRow 和 SRowSet 之间的关系](media/amapi_17.gif "SRow 和 SRowSet 之间的关系")
  
**SRow**结构定义[ADRENTRY](adrentry.md)结构相同。 因此，收件人的表和地址列表中的项的行可以视为相同。 
  
有关应分配的内存**SRow**结构的方式的信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。
  
## <a name="see-also"></a>另请参阅

- [ADRENTRY](adrentry.md)
- [SPropValue](spropvalue.md)
- [SRowSet](srowset.md)
- [TABLE_NOTIFICATION](table_notification.md)
- [MAPI 结构](mapi-structures.md)
- [ADRLIST 和 SRowSet 结构管理内存](managing-memory-for-adrlist-and-srowset-structures.md)

