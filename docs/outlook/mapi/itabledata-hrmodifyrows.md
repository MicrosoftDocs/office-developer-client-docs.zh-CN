---
title: ITableDataHrModifyRows
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrModifyRows
api_type:
- COM
ms.assetid: d295c896-9882-4d6f-9689-5cf40db208c0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d0074dd006fda6d44252011d0b979169e0c3d4cb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405357"
---
# <a name="itabledatahrmodifyrows"></a>ITableData::HrModifyRows

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
插入多个表行, 这些行可能会替换现有行。
  
```cpp
HRESULT HrModifyRows(
  ULONG ulFlags,
  LPSRowSet lpSRowSet
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
 _lpSRowSet_
  
> 实时指向包含要添加的行集的[SRowSet](srowset.md)结构的指针, 如有必要, 替换现有行。 行集中每个[SRow](srow.md)结构的**lpProps**成员所指向的某个属性值结构中应包含索引列, 该值与调用__ [中的 ulPropTagIndexColumn 参数中指定的值相同。CreateTable](createtable.md)函数。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 行已成功插入或修改。
    
MAPI_E_INVALID_PARAMETER 
  
> 一个或多个传入的行没有索引列。 如果返回此错误, 则不会更改任何行。
    
## <a name="remarks"></a>说明

**ITableData:: HrModifyRows**方法插入由_lpSRowSet_参数指向的[SRowSet](srowset.md)结构所描述的行。 如果行中某一行的索引列值与表中现有行的值相匹配, 则将替换现有行。 如果不存在与**SRowSet**结构中包含的行相匹配的行, 则**HrModifyRows**会将该行添加到表的末尾。 
  
将修改表的所有视图, 以包括由_lpSRowSet_指向的行。 但是, 如果视图具有排除行的限制, 则用户可能对其不可见。 
  
_lpSRowSet_指向的行中的列不必与表中的列的顺序相同。 调用方还可以包含表中当前不包含的列属性。 对于现有视图, **HrModifyRows**使这些新列可用, 但不将其包含在当前列集中。 对于将来的视图, **HrModifyRows**包含列集中的新列。 
  
在**HrModifyRows**添加行后, 通知将发送到具有表视图且已调用表的[IMAPITable:: Advise](imapitable-advise.md)方法以注册通知的所有客户端或服务提供程序。 MAPI 为每个行 (最多八行) 发送 TABLE_ROW_ADDED 或 TABLE_ROW_MODIFIED 通知。 如果**HrModifyRows**调用影响八行以上, MAPI 将发送单个 TABLE_CHANGED 通知。 
  
## <a name="see-also"></a>另请参阅



[SRowSet](srowset.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

