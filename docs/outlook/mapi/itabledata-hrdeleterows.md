---
title: ITableDataHrDeleteRows
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrDeleteRows
api_type:
- COM
ms.assetid: 7b351eec-9624-4b38-9978-5d0b67b64687
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fdd6f40b4d7aa7f65bf1a46d3d9a4f18472b19f7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278945"
---
# <a name="itabledatahrdeleterows"></a>ITableData::HrDeleteRows

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
删除多个表行。
  
```cpp
HRESULT HrDeleteRows(
  ULONG ulFlags,
  LPSRowSet lprowsetToDelete,
  ULONG FAR * cRowsDeleted
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时用于控制删除的标志的位掩码。 可以设置以下标志:
    
TAD_ALL_ROWS 
  
> 删除表中的所有行和所有对应的视图, 并发送一个 TABLE_RELOAD 通知。
    
 _lprowsetToDelete_
  
> 实时指向描述要删除的行的行集的指针。 如果在_ulFlags_参数中设置 TAD_ALL_ROWS 标志, 则_lprowsetToDelete_参数可以为 NULL。 
    
 _cRowsDeleted_
  
> 排除已删除行的计数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除表行。
    
## <a name="remarks"></a>注解

**ITableData:: HrDeleteRows**方法查找并删除包含与行集中每个**aRow**条目的**lpProps**成员所指向的属性的列相匹配的表格行。 索引列用于标识每一行;在对[CreateTable](createtable.md)函数的调用中, 此列必须具有与在_ulPropTagIndexColumn_参数中传递的属性标记相同的属性标记。 
  
实际删除的行数在_cRowsDeleted_中返回。 如果找不到一个或多个行, 则不会返回错误。 
  
删除行后, 会将通知发送到具有表视图且已调用表的[IMAPITable:: Advise](imapitable-advise.md)方法以注册通知的所有客户端或服务提供程序。 
  
删除行并不会减小现有的表视图或后续打开的表视图的可用列, 即使删除的行是具有特定列的值的最后, 也是如此。
  
## <a name="see-also"></a>另请参阅



[CreateTable](createtable.md)
  
[ITableData::HrDeleteRow](itabledata-hrdeleterow.md)
  
[ITableData::HrModifyRows](itabledata-hrmodifyrows.md)
  
[SRowSet](srowset.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

