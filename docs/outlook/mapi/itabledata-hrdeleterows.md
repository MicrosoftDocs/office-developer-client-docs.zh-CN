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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416452"
---
# <a name="itabledatahrdeleterows"></a>ITableData::HrDeleteRows

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
删除多个表格行。
  
```cpp
HRESULT HrDeleteRows(
  ULONG ulFlags,
  LPSRowSet lprowsetToDelete,
  ULONG FAR * cRowsDeleted
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制删除的标记的位掩码。 可以设置以下标志：
    
TAD_ALL_ROWS 
  
> 从表中删除所有行以及所有相应的视图，发送单个TABLE_RELOAD通知。
    
 _lprowsetToDelete_
  
> [in]指向描述要删除的行的行集的指针。 如果在 _ulFlags_ 参数中设置了 TAD_ALL_ROWS 标志，则 _lprowsetToDelete_ 参数可以是 NULL。 
    
 _cRowsDeleted_
  
> [out]已删除行的计数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除表行。
    
## <a name="remarks"></a>备注

**ITableData：：HrDeleteRows** 方法查找并删除包含与行集内每个 **aRow** 条目的 **lpProps** 成员所指向的属性匹配的列的表行。 索引列用于标识每一行;此列必须与调用 [CreateTable](createtable.md)函数的 _ulPropTagIndexColumn_ 参数中传递的属性标记具有相同的属性标记。 
  
实际删除的行数在  _cRowsDeleted 中返回_。 如果找不到一行或多行，则不返回错误。 
  
删除行后，通知将发送给所有具有表视图并且已调用表 [的 IMAPITable：：Advise](imapitable-advise.md) 方法来注册通知的客户端或服务提供商。 
  
删除行不会减少可用于现有表视图或随后打开的表视图的列，即使删除的行是具有特定列的值的最后一行。
  
## <a name="see-also"></a>另请参阅



[CreateTable](createtable.md)
  
[ITableData::HrDeleteRow](itabledata-hrdeleterow.md)
  
[ITableData::HrModifyRows](itabledata-hrmodifyrows.md)
  
[SRowSet](srowset.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

