---
title: IMAPIProgressGetFlags
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProgress.GetFlags
api_type:
- COM
ms.assetid: 7af74fcc-c0df-4f58-a2d4-0a79c96b2e81
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 810192bfc85c9934a282f02a0839aaed539f744d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423641"
---
# <a name="imapiprogressgetflags"></a>IMAPIProgress::GetFlags

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回用于计算进度信息的操作级别的进度对象中的标志设置。
  
```cpp
HRESULT GetFlags(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> 排除标志的位掩码, 用于控制计算进度信息的操作级别。 可以返回以下标志:
    
MAPI_TOP_LEVEL 
  
> 正在为顶级对象 (由客户端调用以开始操作的对象) 计算进度。 例如, 文件夹复制操作中的顶级对象是要复制的文件夹。 如果未设置 MAPI_TOP_LEVEL, 则为较低级别的对象或子对象计算进度。 在文件夹复制操作中, 较低级别的对象是要复制的文件夹中的子文件夹之一。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回 flags 值。
    
## <a name="remarks"></a>说明

MAPI 使服务提供程序能够区分顶级对象和子对象与 MAPI_TOP_LEVEL 标志, 以便操作中涉及的所有对象都可以使用相同的[IMAPIProgress](imapiprogressiunknown.md)实现来显示进度。 这会使指示器显示在一个积极方向上平稳地进行。 是否设置 MAPI_TOP_LEVEL 标志确定服务提供程序如何在后续调用进度对象时设置其他参数。 
  
由实施者最初设置由**GetFlags**返回的值, 并通过调用[IMAPIProgress:: SetLimits](imapiprogress-setlimits.md)方法随后由服务提供商设置。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

始终将标志初始化为 MAPI_TOP_LEVEL, 然后依赖服务提供程序在适当的时候将其清除。 服务提供程序可以通过调用**IMAPIProgress:: SetLimits**方法来清除并重置该标记。 有关如何实现**GetFlags**和其他**IMAPIProgress**方法的详细信息, 请参阅[实现进度指示器](implementing-a-progress-indicator.md)。
  
## <a name="notes-to-callers"></a>给调用方的说明

当您显示进度指示器时, 请先调用**IMAPIProgress:: GetFlags**。 返回的值应为 MAPI_TOP_LEVEL, 因为所有实现都会将_lpulFlags_参数的内容初始化为此值。 有关对进度对象的调用序列的详细信息, 请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProgress.cpp  <br/> |CMAPIProgress:: GetFlags  <br/> |MFCMAPI 使用**IMAPIProgress:: GetFlags**方法来确定要设置的标志。 返回 MAPI_TOP_LEVEL, 除非使用**IMAPIProgress:: SetLimits**方法设置了 flags。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[显示进度指示器](how-to-display-a-progress-indicator.md)
  
[实现进度指示器](implementing-a-progress-indicator.md)

