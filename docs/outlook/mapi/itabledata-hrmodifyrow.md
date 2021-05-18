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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408997"
---
# <a name="itabledatahrmodifyrow"></a>ITableData::HrModifyRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
插入新的表格行，可能会替换现有的行。
  
```cpp
HRESULT HrModifyRow(
  LPSRow lpSRow
);
```

## <a name="parameters"></a>参数

 _lpSRow_
  
> [in]指向描述要添加的行或替换现有行的 [SRow](srow.md) 结构的指针。 **SRow** 结构的 **lpProps** 成员指向的属性值结构之一应包含索引列，该值与调用 [CreateTable](createtable.md)函数的 _ulPropTagIndexColumn_ 参数中指定的值相同。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 该行已成功插入或修改。
    
MAPI_E_INVALID_PARAMETER 
  
> 传入行没有索引列。
    
## <a name="remarks"></a>备注

**ITableData：：HrModifyRow** 方法插入 _由 lpSRow_ 参数指向 **的 SRow** 结构所描述的行。 如果与  _lpSRow_ 所指向的行的索引列值相同的行在表中已存在，则替换现有行。 如果不存在与 **SRow** 结构中包含的行匹配的行， **则 HrModifyRow** 会将该行添加到表的末尾。 
  
该表的所有视图都经过修改，以包括  _lpSRow 指向的行_。 但是，如果视图具有排除行的就地限制，则用户可能无法看到该视图。 
  
_lpSRow_ 指向的行中的列与表格中的列的顺序不一样。 调用方还可以包括为表中当前未包含的列属性。 对于现有视图 **，HrModifyRow** 使这些新列可用，但不包括在当前列集内。 对于以后的视图 **，HrModifyRow** 包括列集的新列。 
  
**HrModifyRow** 添加行后，通知将发送到所有具有表视图并且已调用表 [的 IMAPITable：：Advise](imapitable-advise.md)方法来注册通知的客户端或服务提供商。 
  
## <a name="see-also"></a>另请参阅



[SRow](srow.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

