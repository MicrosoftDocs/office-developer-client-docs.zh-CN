---
title: ITableDataHrInsertRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrInsertRow
api_type:
- COM
ms.assetid: e5ae37ea-81a5-49c7-9ad0-0bfac518426c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9aa038958e26652ae7ead728ab15d068e080dc69
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579884"
---
# <a name="itabledatahrinsertrow"></a>ITableData::HrInsertRow

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
插入表格行。 
  
```cpp
HRESULT HrInsertRow(
  ULONG uliRow,
  LPSRow lpSRow
);
```

## <a name="parameters"></a>参数

 _uliRow_
  
> [in]代表对特定行顺序的行号。 将数字表示的行后面放置新行。 _UliRow_参数可以包含从 0 到 n 的行号，其中 n 是表中的行的总数。 _UliRow_中传递 n 追加表末尾的行。 
    
 _lpSRow_
  
> [in]一个指向[SRow](srow.md)结构，描述要插入的行。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功插入行。
    
MAPI_E_INVALID_PARAMETER 
  
> 都有其索引列的值相同，如下表中存在已插入的行的行。
    
## <a name="remarks"></a>注解

**ITableData::HrInsertRow**方法插入表格中的特定位置插入一行。 _UliRow_参数指定的位置中的行后面插入新行。 
  
_UliRow_设置为表中的行数，如果新行所追加到末尾的表。 
  
[SRow](srow.md)结构_lpSRow_参数指向的**lpProps**成员必须包含充当表的索引列的属性。 此索引属性，通常**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))，用于唯一标识未来的维护任务的行。
  
**SRow**结构中的属性列不必为表中的属性列的顺序相同。 
  
插入行之后，通知便发送至所有客户端或服务提供商的具有查看表的和已在调用表的[IMAPITable::Advise](imapitable-advise.md)方法注册的通知。 如果由于限制的视图中不包含插入的行，则不发送任何通知。 
  
## <a name="see-also"></a>另请参阅



[SRow](srow.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

