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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2709ac612fc9e2edaa57b280d52c0a5229ee9978
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278804"
---
# <a name="itabledatahrinsertrow"></a>ITableData::HrInsertRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
插入一个表格行。 
  
```cpp
HRESULT HrInsertRow(
  ULONG uliRow,
  LPSRow lpSRow
);
```

## <a name="parameters"></a>参数

 _uliRow_
  
> 实时一个表示特定行的按顺序的行号。 新行将放置在该数字所指示的行之后。 _uliRow_参数可以包含从0到 n 的行号, 其中 n 是表中的总行数。 在_uliRow_中传递 n 会将行追加到表的末尾。 
    
 _lpSRow_
  
> 实时指向描述要插入的行的[SRow](srow.md)结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功插入该行。
    
MAPI_E_INVALID_PARAMETER 
  
> 与要插入的行在表中已存在的索引列具有相同值的行。
    
## <a name="remarks"></a>注解

**ITableData:: HrInsertRow**方法在表中的特定位置插入一行。 在_uliRow_参数所指定的位置中的行之后插入新行。 
  
如果将_uliRow_设置为表格中的行数, 则新行将追加到表的末尾。 
  
充当表的索引列的属性必须包含在_lpSRow_参数指向的[SRow](srow.md)结构的**lpProps**成员中。 此索引属性 (通常为**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))) 用于唯一标识该行, 以用于将来的维护任务。
  
**SRow**结构中的属性列不必与表中的属性列的顺序相同。 
  
在插入行后, 会将通知发送到具有表视图且已调用表的[IMAPITable:: Advise](imapitable-advise.md)方法以注册通知的所有客户端或服务提供程序。 如果由于限制而在视图中不包含所插入的行, 则不会发送任何通知。 
  
## <a name="see-also"></a>另请参阅



[SRow](srow.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

