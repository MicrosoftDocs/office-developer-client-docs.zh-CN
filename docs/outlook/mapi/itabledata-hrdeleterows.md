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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 00662d7a5bf1c2addc5c4e0b39d657abd7073753
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776081"
---
# <a name="itabledatahrdeleterows"></a>ITableData::HrDeleteRows

  
  
**适用于**： Outlook 
  
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
  
> [in]位掩码的标志控制删除的。 可以设置以下标记：
    
TAD_ALL_ROWS 
  
> 从表和发送单个 TABLE_RELOAD 通知的所有相应的视图中删除所有行。
    
 _lprowsetToDelete_
  
> [in]一个指向介绍要删除的行的行集。 _LprowsetToDelete_参数可以是 NULL，如果_ulFlags_参数中设置 TAD_ALL_ROWS 标志。 
    
 _cRowsDeleted_
  
> [输出]已删除的行数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除的表格行。
    
## <a name="remarks"></a>说明

**ITableData::HrDeleteRows**方法查找并删除包含匹配指向按行中每个**aRow**条目的**lpProps**成员设置的属性的列的表格行。 索引列用于标识每一行;此列必须具有相同的属性标记为对[CreateTable](createtable.md)函数的调用中_ulPropTagIndexColumn_参数中传递的属性标记。 
  
_CRowsDeleted_返回的实际已删除的行数。 如果找不到一个或多个行，则不返回任何错误。 
  
删除行之后，通知便发送至所有客户端或服务提供商的具有查看表的和已在调用表的[IMAPITable::Advise](imapitable-advise.md)方法注册的通知。 
  
删除行不会降低到现有表视图中可用的列或随后打开表视图，即使已删除的行的最后一个具有特定的列的值。
  
## <a name="see-also"></a>另请参阅



[CreateTable](createtable.md)
  
[ITableData::HrDeleteRow](itabledata-hrdeleterow.md)
  
[ITableData::HrModifyRows](itabledata-hrmodifyrows.md)
  
[SRowSet](srowset.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

