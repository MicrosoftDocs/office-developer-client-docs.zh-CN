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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5ef210aedc884e5c09eca6335199e2ef284b901c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574829"
---
# <a name="itabledatahrmodifyrow"></a>ITableData::HrModifyRow

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
插入一个新的表格行，原因可能替换现有行。
  
```cpp
HRESULT HrModifyRow(
  LPSRow lpSRow
);
```

## <a name="parameters"></a>参数

 _lpSRow_
  
> [in]一个指向[SRow](srow.md)结构，描述要添加或替换现有行的行。 一个指向由**SRow**结构**lpProps**成员的属性值结构应包含索引列中，已对[CreateTable 的调用中的_ulPropTagIndexColumn_参数中指定的相同值](createtable.md)函数。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 行成功插入或修改。
    
MAPI_E_INVALID_PARAMETER 
  
> 传入的行不具有索引列。
    
## <a name="remarks"></a>注解

**ITableData::HrModifyRow**方法插入_lpSRow_参数指向**SRow**结构所描述的行。 如果该行的行及其索引列的相同的值的_lpSRow_点表中已存在，将替换现有行。 如果没有行存在相匹配的**SRow**结构中包含的一个， **HrModifyRow**表末尾添加行。 
  
修改表的所有视图以包括指向_lpSRow_的行。 但是，如果视图中排除行的位置有限制，则它可能不对用户可见。 
  
指的_lpSRow_行中的列不需要在表中的列的顺序相同。 呼叫者还可以包括为当前不是表中的列属性。 对于现有视图， **HrModifyRow**使这些新列可用，但不包括其当前列集合中。 对于将来视图**HrModifyRow**列设置中包括的新列。 
  
**HrModifyRow**添加行之后，通知便发送至所有客户端或服务提供商的具有查看表的和已在调用表的[IMAPITable::Advise](imapitable-advise.md)方法注册的通知。 
  
## <a name="see-also"></a>另请参阅



[SRow](srow.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

