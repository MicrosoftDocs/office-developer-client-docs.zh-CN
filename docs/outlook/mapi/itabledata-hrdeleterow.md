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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 37d0ce65e125b2420af775d61ead51db189758ca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776085"
---
# <a name="itabledatahrdeleterow"></a>ITableData::HrDeleteRow

  
  
**适用于**： Outlook 
  
删除表格行。
  
```cpp
HRESULT HrDeleteRow(
  LPSPropValue lpSPropValue
);
```

## <a name="parameters"></a>参数

 _lpSPropValue_
  
> [in]指向描述要删除的行的索引列的属性值结构的指针。 属性值结构的**ulPropTag**成员应包含作为_ulPropTagIndexColumn_参数对[CreateTable](createtable.md)函数的调用中的相同属性标记。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除行。
    
MAPI_E_NOT_FOUND 
  
> 未识别_lpSPropValue_参数指向的属性表中的行。 
    
## <a name="remarks"></a>说明

**ITableData::HrDeleteRow**方法将删除包含_lpSPropValue_参数指向的属性相匹配的列的表格行。 删除行的数据，并从所有打开的视图中删除行。 
  
删除行之后，通知便发送至所有客户端或服务提供商的具有查看表的和已在调用表的[IMAPITable::Advise](imapitable-advise.md)方法注册的通知。 
  
删除行不会降低列设置可供现有视图或随后打开视图，即使已删除的行具有特定的列的值的最后一行。
  
## <a name="see-also"></a>另请参阅



[CreateTable](createtable.md)
  
[ITableData::HrDeleteRows](itabledata-hrdeleterows.md)
  
[ITableData::HrModifyRow](itabledata-hrmodifyrow.md)
  
[SPropValue](spropvalue.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

