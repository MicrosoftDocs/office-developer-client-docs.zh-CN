---
title: IMAPIControlGetState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIControl.GetState
api_type:
- COM
ms.assetid: fb321b48-3e5f-4b99-9af0-a57b66f26a2e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f477c617533d66fc129c7192c9f86bb8a46afbb1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280278"
---
# <a name="imapicontrolgetstate"></a>IMAPIControl::GetState

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索一个值, 该值指示按钮控件是否已启用或已禁用。
  
```cpp
HRESULT GetState(
  ULONG ulFlags,
  ULONG FAR * lpulState
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
 _lpulState_
  
> 排除指向指示按钮控件状态的值的指针。 可以返回下列值之一:
    
MAPI_DISABLED 
  
> 按钮控件已被禁用, 无法单击。 
    
MAPI_ENABLED 
  
> 按钮控件已启用, 可以单击。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索按钮控件的状态。
    
## <a name="remarks"></a>注解

服务提供程序实现**IMAPIControl:: GetState**方法, 以向 MAPI 提供按钮控件的状态。 如果按钮已启用, 则它可以响应鼠标单击或按键。 如果已禁用, 则按钮显示为灰色, 且不响应鼠标单击或按键。 
  
有关如何实现**GetState**和其他[IMAPIControl: IUnknown](imapicontroliunknown.md)方法的详细信息, 请参阅[Control Object 实现](control-object-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIControl::Activate](imapicontrol-activate.md)
  
[IMAPIControl : IUnknown](imapicontroliunknown.md)

