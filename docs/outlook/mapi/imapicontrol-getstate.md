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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419007"
---
# <a name="imapicontrolgetstate"></a>IMAPIControl::GetState

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索一个值，该值指示按钮控件是启用还是禁用。
  
```cpp
HRESULT GetState(
  ULONG ulFlags,
  ULONG FAR * lpulState
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpulState_
  
> [out]指向指示按钮控件状态的值的指针。 可以返回下列值之一：
    
MAPI_DISABLED 
  
> 按钮控件处于禁用状态，无法单击。 
    
MAPI_ENABLED 
  
> 按钮控件已启用，可单击。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索按钮控件的状态。
    
## <a name="remarks"></a>备注

服务提供商实现 **IMAPIControl：：GetState** 方法，以向 MAPI 提供按钮控件的状态。 如果启用该按钮，它可以响应鼠标单击或按键。 如果禁用，按钮将灰显，并且不会响应鼠标单击或按键。 
  
若要详细了解如何实现 **GetState** 和其他 [IMAPIControl ： IUnknown](imapicontroliunknown.md) 方法，请参阅 [控件对象实现](control-object-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIControl::Activate](imapicontrol-activate.md)
  
[IMAPIControl : IUnknown](imapicontroliunknown.md)

