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
ms.openlocfilehash: 9a5e4205a808c7a6e469d2e9cb0a1b3c17a92d21
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573542"
---
# <a name="imapiprogressgetflags"></a>IMAPIProgress::GetFlags

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回标记的操作对其计算进度信息的级别的进度对象中的设置。
  
```cpp
HRESULT GetFlags(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [输出]位掩码的标志控制级别的操作的进度信息的计算公式的。 可以返回以下标记：
    
MAPI_TOP_LEVEL 
  
> 正在计算进度的顶级对象，由客户端开始操作调用的对象。 例如，文件夹复制操作中的顶级对象是正在将复制的文件夹。 如果未设置 MAPI_TOP_LEVEL，进度计算较低级别的对象或子对象。 文件夹复制操作，较低的 level 对象是正在将复制的文件夹中的子文件夹之一。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回的标志值。
    
## <a name="remarks"></a>注解

MAPI 启用服务提供商要区分顶级对象，并与 MAPI_TOP_LEVEL 标志的子对象，以便在操作中涉及的所有对象可以使用相同的[IMAPIProgress](imapiprogressiunknown.md)实现以显示进度。 这会导致标记显示的一个正数方向顺利。 是否设置 MAPI_TOP_LEVEL 标志确定服务提供程序如何设置对进度对象的后续呼叫中的其他参数。 
  
通过实施并随后服务提供程序通过对[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)方法的调用最初设置**GetFlags**返回的值。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

始终初始化 MAPI_TOP_LEVEL 标志，然后依赖服务提供商，以将其适当时清除。 服务提供商可以清除，并重置通过调用**IMAPIProgress::SetLimits**方法的标志。 有关如何实施**GetFlags**和其他**IMAPIProgress**方法的详细信息，请参阅[实现进度指示器](implementing-a-progress-indicator.md)。
  
## <a name="notes-to-callers"></a>给调用方的说明

显示进度指示器，使您第一次调用**IMAPIProgress::GetFlags**调用。 返回的值应为 MAPI_TOP_LEVEL，因为所有实现都初始化_lpulFlags_参数为此值的内容。 调用进度对象的顺序的详细信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIProgress.cpp  <br/> |CMAPIProgress::GetFlags  <br/> |MFCMAPI 使用**IMAPIProgress::GetFlags**方法来确定哪些标志设置。 返回 MAPI_TOP_LEVEL，除非已设置使用**IMAPIProgress::SetLimits**方法的标志。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[显示进度指示器](how-to-display-a-progress-indicator.md)
  
[实现进度指示器](implementing-a-progress-indicator.md)

