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
  
插入多个表格行，可能会替换现有行。
  
```cpp
HRESULT HrModifyRows(
  ULONG ulFlags,
  LPSRowSet lpSRowSet
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpSRowSet_
  
> [in]指向包含要添加 [的行集的 SRowSet](srowset.md) 结构的指针，如有必要，替换现有行。 行集内每个 [SRow](srow.md)结构的 **lpProps** 成员指向的属性值结构之一应包含索引列，该值与调用 [CreateTable](createtable.md)函数的 _ulPropTagIndexColumn_ 参数中指定的值相同。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功插入或修改行。
    
MAPI_E_INVALID_PARAMETER 
  
> 一个或多个传入行没有索引列。 如果返回此错误，则不更改任何行。
    
## <a name="remarks"></a>备注

**ITableData：：HrModifyRows** 方法插入 _由 lpSRowSet_ 参数指向 [的 SRowSet](srowset.md)结构所描述的行。 如果行集内行的索引列值与表中现有行的值相匹配，则替换现有行。 如果不存在与 **SRowSet** 结构中包含的行匹配的行， **则 HrModifyRows** 会将该行添加到表的末尾。 
  
该表的所有视图都经过修改，以包括  _lpSRowSet 指向的行_。 但是，如果视图具有排除行的就地限制，则用户可能无法看到该视图。 
  
_lpSRowSet_ 指向的行中的列不一定与表中的列的顺序相同。 调用方还可以包括为表中当前未包含的列属性。 对于现有视图 **，HrModifyRows** 使这些新列可用，但不包括在当前列集内。 对于将来视图 **，HrModifyRows** 包括列集内的新列。 
  
**在 HrModifyRows** 添加行后，通知将发送给所有具有表视图并且已调用表 [的 IMAPITable：：Advise](imapitable-advise.md)方法来注册通知的客户端或服务提供商。 MAPI 发送TABLE_ROW_ADDED或TABLE_ROW_MODIFIED行（最多八行）的通知。 如果 **HrModifyRows** 调用影响超过 8 行，MAPI 将改为发送单个TABLE_CHANGED通知。 
  
## <a name="see-also"></a>另请参阅



[SRowSet](srowset.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

