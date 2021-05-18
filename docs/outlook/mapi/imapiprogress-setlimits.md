---
title: IMAPIProgressSetLimits
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProgress.SetLimits
api_type:
- COM
ms.assetid: 63c9e316-ee53-4065-8154-449639643ff7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0810ed7ce20bba95c4286e6e042065c0c2d1a802
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421464"
---
# <a name="imapiprogresssetlimits"></a>IMAPIProgress::SetLimits

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置操作中项数的下限和上限，以及控制如何计算操作进度信息的标志。
  
```cpp
HRESULT SetLimits(
  LPULONG lpulMin,
  LPULONG lpulMax,
  LPULONG lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulMin_
  
> [in]指向包含操作中项下限的变量的指针。
    
 _lpulMax_
  
> [in]指向包含操作中项目的上限的变量的指针。
    
 _lpulFlags_
  
> [in]控制计算进度信息的操作级别的标志位掩码。 可以设置以下标志：
    
MAPI_TOP_LEVEL 
  
> 使用 [IMAPIProgress：:P rogress](imapiprogress-progress.md) 方法的  _ulCount_ 和  _ulTotal_ 参数中的值，分别指示当前处理的项和总项数，以递增操作的进度。 设置此标志时，必须设置全局下限和上限的值。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

服务提供商调用 **IMAPIProgress：：SetLimits** 方法来设置或清除 MAPI_TOP_LEVEL 标志，并设置本地和全局最小值和最大值。 标志设置的值会影响进度对象是了解最小值还是最大值是本地值还是全局值。 设置 MAPI_TOP_LEVEL 标志时，这些值被视为全局值，用于计算整个操作的进度。 Progress 对象将全局最小值初始化为 1，将全局最大值初始化为 1000。 
  
未MAPI_TOP_LEVEL时，最小值和最大值被视为本地值，提供程序在内部使用它们来显示较低级别的子对象的进度。 Progress 对象仅保存本地最小值和最大值，以便它们可以在 [调用 IMAPIProgress：：GetMin](imapiprogress-getmin.md) 和 [IMAPIProgress：：GetMax](imapiprogress-getmax.md) 方法时返回到提供程序。 
  
若要详细了解如何实现 **SetLimits 和其他** [IMAPIProgress](imapiprogressiunknown.md) 方法，请参阅 [实现进度指示器](implementing-a-progress-indicator.md)。
  
有关如何调用进度对象以及何时调用的详细信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProgress.cpp  <br/> |CMAPIProgress：：SetLimits  <br/> |MFCMAPI 使用 **IMAPIProgress：：SetLimits** 方法来设置进度对象的最大和最小限制和标志。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProgress::GetMax](imapiprogress-getmax.md)
  
[IMAPIProgress::GetMin](imapiprogress-getmin.md)
  
[IMAPIProgress::Progress](imapiprogress-progress.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[显示进度指示器](how-to-display-a-progress-indicator.md)
  
[实现进度指示器](implementing-a-progress-indicator.md)

