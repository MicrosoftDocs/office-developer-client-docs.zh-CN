---
title: ITableDataHrNotify
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrNotify
api_type:
- COM
ms.assetid: 98548b50-342e-434a-9ad3-c37ba418c5ce
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1be4fd95d29859c542fe553bdc3728ea23444694
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776103"
---
# <a name="itabledatahrnotify"></a>ITableData::HrNotify

  
  
**适用于**： Outlook 
  
发送通知的表格行。
  
```cpp
HRESULT HrNotify(
  ULONG ulFlags,
  ULONG cValues,
  LPSPropValue lpSPropValue
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _cValues_
  
> [in]_LpSPropValue_参数指向[SPropValue](spropvalue.md)结构中的属性值的计数。 
    
 _lpSPropValue_
  
> [in]指向介绍的目标行中的列的值的**SPropValue**结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

**ITableData::HrNotify**方法发送 TABLE_ROW_MODIFIED 通知匹配_lpSPropValue_参数指向属性并由它们所述的行的行。 **HrNotify**发送无论是否发生了更改行的通知。 所有客户端和视图的表的和具有其视图上的通知调用[IMAPITable::Advise](imapitable-advise.md)注册的服务提供商收到此通知。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

