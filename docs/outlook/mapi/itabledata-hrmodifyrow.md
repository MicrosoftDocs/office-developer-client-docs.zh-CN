---
title: ITableDataHrModifyRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrModifyRow
api_type:
- COM
ms.assetid: 9e255b3e-dd17-4528-ba4e-c3a1aef32b04
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 44ecf095ad24dd266dc5f603ace9c7b9f21c1b41
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348662"
---
# <a name="itabledatahrmodifyrow"></a>ITableData::HrModifyRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
插入一个新的表格行, 可能会替换现有行。
  
```cpp
HRESULT HrModifyRow(
  LPSRow lpSRow
);
```

## <a name="parameters"></a>参数

 _lpSRow_
  
> 实时指向描述要添加的行或要替换现有行的[SRow](srow.md)结构的指针。 **SRow**结构的**lpProps**成员所指向的某个属性值结构应包含索引列, 在对 CreateTable 的调用中的_ulPropTagIndexColumn_参数中指定的值相同。 [](createtable.md)函数。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 行已成功插入或修改。
    
MAPI_E_INVALID_PARAMETER 
  
> 传入的行没有索引列。
    
## <a name="remarks"></a>注解

**ITableData:: HrModifyRow**方法插入由_lpSRow_参数指向的**SRow**结构所描述的行。 如果与_lpSRow_指向的行在表中已存在具有相同的 index 列值的行, 则将替换现有行。 如果不存在与**SRow**结构中包含的行相匹配的行, 则**HrModifyRow**会将该行添加到表的末尾。 
  
将修改表的所有视图, 以包括由_lpSRow_指向的行。 但是, 如果视图具有排除行的限制, 则用户可能对其不可见。 
  
_lpSRow_所指向的行中的列不必与表中的列的顺序相同。 调用方还可以包含表中当前不包含的列属性。 对于现有视图, **HrModifyRow**使这些新列可用, 但不将其包含在当前列集中。 对于将来的视图, **HrModifyRow**包含列集中的新列。 
  
在**HrModifyRow**添加行后, 会将通知发送到具有表视图且已调用表的[IMAPITable:: Advise](imapitable-advise.md)方法以注册通知的所有客户端或服务提供程序。 
  
## <a name="see-also"></a>另请参阅



[SRow](srow.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

