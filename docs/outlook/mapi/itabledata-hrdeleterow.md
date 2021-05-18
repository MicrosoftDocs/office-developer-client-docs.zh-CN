---
title: ITableDataHrDeleteRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrDeleteRow
api_type:
- COM
ms.assetid: 670c2291-d5b6-4dcf-9046-9125272dd8f8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b187cccc4505256b7ab4d580c30eeb2e15ebf574
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421674"
---
# <a name="itabledatahrdeleterow"></a>ITableData::HrDeleteRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
删除表格行。
  
```cpp
HRESULT HrDeleteRow(
  LPSPropValue lpSPropValue
);
```

## <a name="parameters"></a>参数

 _lpSPropValue_
  
> [in]指向描述要删除的行的索引列的属性值结构的指针。 属性值 **结构的 ulPropTag** 成员应包含与从调用 [CreateTable](createtable.md)函数调用中的 _ulPropTagIndexColumn_ 参数相同的属性标记。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 该行已成功删除。
    
MAPI_E_NOT_FOUND 
  
> _lpSPropValue_ 参数指向的属性不标识表中的行。 
    
## <a name="remarks"></a>备注

**ITableData：：HrDeleteRow** 方法删除包含与 _lpSPropValue_ 参数指向的属性匹配的列的表行。 该行的数据将被删除，并且该行将从所有打开的视图中删除。 
  
删除行后，通知将发送给所有具有表视图并且已调用表 [的 IMAPITable：：Advise](imapitable-advise.md) 方法来注册通知的客户端或服务提供商。 
  
删除行不会减少可用于现有视图或随后打开的视图的列集，即使删除的行是具有特定列的值的最后一行。
  
## <a name="see-also"></a>另请参阅



[CreateTable](createtable.md)
  
[ITableData::HrDeleteRows](itabledata-hrdeleterows.md)
  
[ITableData::HrModifyRow](itabledata-hrmodifyrow.md)
  
[SPropValue](spropvalue.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

