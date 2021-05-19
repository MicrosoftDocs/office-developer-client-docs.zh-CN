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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435437"
---
# <a name="itabledatahrinsertrow"></a>ITableData::HrInsertRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
插入表格行。 
  
```cpp
HRESULT HrInsertRow(
  ULONG uliRow,
  LPSRow lpSRow
);
```

## <a name="parameters"></a>参数

 _一起_
  
> [in]一个代表特定行的顺序行号。 新行将放置在数字指示的行之后。 _uliRow_ 参数可包含 0 到 n 之间的行号，其中 n 是表中的总行数。 在  _一行中传递_ n 将行追加到表的末尾。 
    
 _lpSRow_
  
> [in]指向描述要插入的行的 [SRow](srow.md) 结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 该行已成功插入。
    
MAPI_E_INVALID_PARAMETER 
  
> 表中已存在与要插入的行具有相同的索引列值的行。
    
## <a name="remarks"></a>备注

**ITableData：：HrInsertRow** 方法将一行插入到表中的特定位置。 新行将插入到 一行之后，该行位于  _一行中由 一行参数_ 指定的位置。 
  
如果  _一行_ 设置为表格中的行数，则新行将追加到表格的末尾。 
  
充当表的索引列的属性必须包含在 _lpSRow_ 参数指向 [的 SRow](srow.md)结构的 **lpProps** 成员中。 此索引属性通常PR_INSTANCE_KEY ( [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) ，用于唯一标识用于将来维护任务的行。
  
**SRow** 结构中的属性列不一定与表中的属性列的顺序相同。 
  
插入行后，通知将发送给所有具有表视图并且已调用表 [的 IMAPITable：：Advise](imapitable-advise.md) 方法来注册通知的客户端或服务提供商。 如果由于限制而未在视图中包含插入的行，则不发送任何通知。 
  
## <a name="see-also"></a>另请参阅



[SRow](srow.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

