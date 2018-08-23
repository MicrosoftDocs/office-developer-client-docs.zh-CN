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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 06356d60b43d7e5be61d944c07001570bdd5c678
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571106"
---
# <a name="itabledatahrmodifyrows"></a>ITableData::HrModifyRows

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
插入多个表行，原因可能替换现有行。
  
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
  
> [in]指向[SRowSet](srowset.md)结构的指针，包含要添加的行集替换现有行，如有必要。 一个指向按行中每个[SRow](srow.md)结构的**lpProps**成员设置的属性值结构应包含索引列中，已对[的调用中的_ulPropTagIndexColumn_参数中指定的相同值CreateTable](createtable.md)函数。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功插入或修改行。
    
MAPI_E_INVALID_PARAMETER 
  
> 一个或多个传入的行不具有索引列。 如果将返回此错误，不更改任何行。
    
## <a name="remarks"></a>注解

**ITableData::HrModifyRows**方法插入_lpSRowSet_参数指向[SRowSet](srowset.md)结构所描述的行。 如果在行集中的行的索引列值与现有行表中的值相匹配，将替换现有行。 如果没有行存在相匹配的**SRowSet**结构中包含的一个， **HrModifyRows**表末尾添加行。 
  
修改表的所有视图以包括指向_lpSRowSet_的行。 但是，如果视图中排除行的位置有限制，则它可能不对用户可见。 
  
指向_lpSRowSet_的行中的列不需要在表中的列的顺序相同。 呼叫者还可以包括为当前不是表中的列属性。 对于现有视图， **HrModifyRows**使这些新列可用，但不包括其当前列集合中。 对于将来视图**HrModifyRows**列设置中包括的新列。 
  
**HrModifyRows**已添加行之后，通知便发送至所有客户端或服务提供商的具有查看表的和已在调用表的[IMAPITable::Advise](imapitable-advise.md)方法注册的通知。 MAPI 发送每一行，最多八个行的 TABLE_ROW_ADDED 或 TABLE_ROW_MODIFIED 的通知。 如果不会影响八个以上的行由**HrModifyRows**呼叫，MAPI 发送单个 TABLE_CHANGED 通知相反。 
  
## <a name="see-also"></a>另请参阅



[SRowSet](srowset.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

