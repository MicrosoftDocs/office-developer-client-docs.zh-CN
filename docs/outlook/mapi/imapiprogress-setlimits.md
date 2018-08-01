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
ms.openlocfilehash: 14abfaadcdb1710a7cb8275c8f82d502aea8300e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775510"
---
# <a name="imapiprogresssetlimits"></a>IMAPIProgress::SetLimits

  
  
**适用于**： Outlook 
  
设置项的数目的上限和下限限制中操作，并且控制操作的进度信息的计算方式的标志。
  
```cpp
HRESULT SetLimits(
  LPULONG lpulMin,
  LPULONG lpulMax,
  LPULONG lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulMin_
  
> [in]指向包含操作中的项目的下限变量的指针。
    
 _lpulMax_
  
> [in]指向包含操作中的项目的上限变量的指针。
    
 _lpulFlags_
  
> [in]位掩码的标志控制级别的操作的进度信息的计算公式的。 可以设置以下标记：
    
MAPI_TOP_LEVEL 
  
> [IMAPIProgress::Progress](imapiprogress-progress.md)方法的_ulCount_和_ulTotal_参数，指示当前处理的项目和的项，分别增量操作的进度中使用的值。 当此标志设置时，必须设置全局上限和下限限制的值。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

服务提供商调用**IMAPIProgress::SetLimits**方法来设置或清除 MAPI_TOP_LEVEL 标志并设置本地和全局最小和最大值。 是否正在进行对象了解最小和最大值为本地域或全局设置会影响标志的值。 当设置 MAPI_TOP_LEVEL 标志时，这些值将被视为全局并用于计算整个操作的进度。 进度对象初始化为 1 的全局最小值和全局最大值为 1000年。 
  
当不设置 MAPI_TOP_LEVEL 时，最小和最大值被视为本地，并提供程序使用其内部显示正在进行较低级别的子对象。 仅，以便他们可以返回到提供程序的[IMAPIProgress::GetMin](imapiprogress-getmin.md)和[IMAPIProgress::GetMax](imapiprogress-getmax.md)方法调用时，进度对象保存本地的最小和最大值。 
  
有关如何实施**SetLimits**和其他[IMAPIProgress](imapiprogressiunknown.md)方法的详细信息，请参阅[实现进度指示器](implementing-a-progress-indicator.md)。
  
有关详细了解如何以及何时调用进度对象，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIProgress.cpp  <br/> |CMAPIProgress::SetLimits  <br/> |MFCMAPI 使用**IMAPIProgress::SetLimits**方法设置的最大和最小限制和进度对象的标志。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProgress::GetMax](imapiprogress-getmax.md)
  
[IMAPIProgress::GetMin](imapiprogress-getmin.md)
  
[IMAPIProgress::Progress](imapiprogress-progress.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[显示进度指示器](how-to-display-a-progress-indicator.md)
  
[实现进度指示器](implementing-a-progress-indicator.md)

