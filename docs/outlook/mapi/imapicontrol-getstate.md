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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a6ae89bf9b2b16439cc06f0e106859dda10ea22c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19775320"
---
# <a name="imapicontrolgetstate"></a>IMAPIControl::GetState

  
  
**适用于**： Outlook 
  
检索值，该值指示是否启用或禁用按钮控件。
  
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
  
> [输出]指向一个值，指示的状态按钮控件的指针。 可以返回下列值之一：
    
MAPI_DISABLED 
  
> 按钮控件将禁用，并且不能单击。 
    
MAPI_ENABLED 
  
> 按钮控件启用，并且可以单击。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索按钮控件的状态。
    
## <a name="remarks"></a>说明

服务提供商实现**IMAPIControl::GetState**方法使 MAPI 按钮控件的状态。 如果启用按钮，则它可以响应鼠标单击或击键。 如果它被禁用，该按钮变暗，并对鼠标单击或击键没有响应。 
  
有关如何实施**GetState**和其他详细信息[IMAPIControl: IUnknown](imapicontroliunknown.md)方法，请参阅[控件对象实现](control-object-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIControl::Activate](imapicontrol-activate.md)
  
[IMAPIControl : IUnknown](imapicontroliunknown.md)

