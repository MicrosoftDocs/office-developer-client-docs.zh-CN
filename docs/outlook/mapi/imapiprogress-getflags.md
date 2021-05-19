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
  
从计算进度信息的操作级别的进度对象中返回标志设置。
  
```cpp
HRESULT GetFlags(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [out]控制计算进度信息的操作级别的标志位掩码。 可以返回以下标志：
    
MAPI_TOP_LEVEL 
  
> 正在计算顶级对象的进度，该对象由客户端调用以开始操作。 例如，文件夹复制操作中的顶级对象是正在复制的文件夹。 未MAPI_TOP_LEVEL时，将计算较低级别对象或子对象的进度。 在文件夹复制操作中，较低级别的对象是正在复制的文件夹中的子文件夹之一。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 标志值已成功返回。
    
## <a name="remarks"></a>备注

MAPI 使服务提供商能够区分具有 MAPI_TOP_LEVEL 标志的顶级对象和子对象，以便操作中涉及的所有对象可以使用同一 [IMAPIProgress](imapiprogressiunknown.md) 实现来显示进度。 这将导致指示器在单个正方向上平稳地显示。 是否设置MAPI_TOP_LEVEL标记确定服务提供商如何在后续对 progress 对象的调用中设置其他参数。 
  
**GetFlags** 返回的值最初由实现者设置，随后由服务提供商通过调用 [IMAPIProgress：：SetLimits](imapiprogress-setlimits.md)方法进行设置。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

始终将标志初始化为MAPI_TOP_LEVEL，然后依赖服务提供商在适当的时候清除它。 服务提供商可以通过调用 **IMAPIProgress：：SetLimits** 方法清除和重置标志。 若要详细了解如何实现 **GetFlags** 和其他 **IMAPIProgress** 方法，请参阅 [实现进度指示器](implementing-a-progress-indicator.md)。
  
## <a name="notes-to-callers"></a>给调用方的说明

当你显示进度指示器时，请首先调用 **IMAPIProgress：：GetFlags**。 返回的值应MAPI_TOP_LEVEL，因为所有实现将  _lpulFlags_ 参数的内容初始化为此值。 有关对进度对象的调用顺序详细信息，请参阅 [显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProgress.cpp  <br/> |CMAPIProgress：：GetFlags  <br/> |MFCMAPI 使用 **IMAPIProgress：：GetFlags** 方法确定设置的标志。 除非MAPI_TOP_LEVEL **IMAPIProgress：：SetLimits** 方法设置了标志，否则返回值。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[显示进度指示器](how-to-display-a-progress-indicator.md)
  
[实现进度指示器](implementing-a-progress-indicator.md)

