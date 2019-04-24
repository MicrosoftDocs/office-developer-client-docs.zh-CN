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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: aa2170bf4bedfb441ad4808f774f6f71d5caf85e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348634"
---
# <a name="itabledatahrnotify"></a>ITableData::HrNotify

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为表行发送通知。
  
```cpp
HRESULT HrNotify(
  ULONG ulFlags,
  ULONG cValues,
  LPSPropValue lpSPropValue
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
 _cValues_
  
> 实时由_lpSPropValue_参数指向的[SPropValue](spropvalue.md)结构中的属性值的计数。 
    
 _lpSPropValue_
  
> 实时指向描述目标行中各列的值的**SPropValue**结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

**ITableData:: HrNotify**方法发送与_lpSPropValue_参数所指向的属性所描述的行相匹配的行的 TABLE_ROW_MODIFIED 通知。 **HrNotify**发送通知, 无论行是否发生了更改。 所有具有表视图且已调用[IMAPITable:: 建议](imapitable-advise.md)在其视图中注册通知的客户端和服务提供程序都会收到此通知。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

