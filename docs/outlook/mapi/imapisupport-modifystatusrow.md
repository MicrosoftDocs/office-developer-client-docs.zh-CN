---
title: IMAPISupportModifyStatusRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.ModifyStatusRow
api_type:
- COM
ms.assetid: a304ca8f-e404-4535-be76-0b673f2061a0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8c76e6059670e782ea6530ec8e94f77abfe5b9fe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417159"
---
# <a name="imapisupportmodifystatusrow"></a>IMAPISupport::ModifyStatusRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通过添加新行或修改现有行来修改状态表。
  
```cpp
HRESULT ModifyStatusRow(
ULONG cValues,
LPSPropValue lpColumnVals,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _cValues_
  
> 实时要包含在新的或修改的状态表行中的属性的计数。 
    
 _lpColumnVals_
  
> 实时指向属性值数组的指针, 这些属性值描述要作为新的或修改的状态表行中的列包含的属性。
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制如何处理定义状态表行的信息。 可以设置以下标志:
    
STATUSROW_UPDATE 
  
> 指示 MAPI 将由_lpColumnVals_指向的数组中包含的属性与现有状态表行 (而不是新行) 合并。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功更新状态表。
    
## <a name="remarks"></a>说明

**IMAPISupport:: ModifyStatusRow**方法是为所有服务提供程序支持对象实现的。 服务提供程序在登录时调用**ModifyStatusRow**以向状态表中添加行, 并在会话过程中的其他时间将行添加到更新行。 **ModifyStatusRow**为 MAPI 提供生成状态表所需的信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用**ModifyStatusRow**时设置 STATUSROW_UPDATE 标志, 以对现有状态表行中的属性进行更改。 这样做会通知 MAPI 仅在_lpColumnVals_参数中传递所更改的列。 
  
客户端可以使用状态表中的信息访问状态对象。 
  
若要获取您的状态表行中应包含的列的完整列表, 请参阅[状态表](status-tables.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

