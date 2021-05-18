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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413267"
---
# <a name="itabledatahrnotify"></a>ITableData::HrNotify

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
发送表行的通知。
  
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
  
> [in] [SPropValue](spropvalue.md) 结构中由  _lpSPropValue_ 参数指向的属性值计数。 
    
 _lpSPropValue_
  
> [in]指向描述目标行中列值的 **SPropValue** 结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

**ITableData：：HrNotify** 方法为TABLE_ROW_MODIFIED _lpSPropValue_ 参数指向的属性所描述的行匹配的行发送一个通知。 **HrNotify** 发送通知，而不管该行是否发生了更改。 所有具有表视图并且已调用 [IMAPITable：：Advise](imapitable-advise.md) 以注册其视图上的通知的客户端和服务提供商将收到此通知。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

