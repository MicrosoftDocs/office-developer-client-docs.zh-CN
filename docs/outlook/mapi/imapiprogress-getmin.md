---
title: IMAPIProgressGetMin
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProgress.GetMin
api_type:
- COM
ms.assetid: caceddf1-0f7c-47b5-97bf-17ffe3440a6c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6cd31f8ac713c21053db7ef461220a360ebeec74
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404846"
---
# <a name="imapiprogressgetmin"></a>IMAPIProgress::GetMin

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在显示其进度信息的 [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) 方法中返回最小值。 
  
```cpp
HRESULT GetMin(
  ULONG FAR * lpulMin
);
```

## <a name="parameters"></a>参数

 _lpulMin_
  
> [out] 指向操作中项数目最小值的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已检索到操作中项数目最小值。
    
## <a name="remarks"></a>备注

最小值表示在数值窗体中操作的开始。 该值可以是全局最大值，用于表示整个进度显示的范围，也可以是本地值，用于仅表示显示的一部分。 
  
标记设置的值会影响进度对象是将最小值理解为本地最小值还是全局最小值。 设置 MAPI_TOP_LEVEL 标记时，将最小值视为全局最小值，用于计算整个操作的进度。 如果未设置 MAPI_TOP_LEVEL，则将最小值视为本地最小值，并且提供程序在内部使用它来显示较低级别子对象的进度。 进度对象仅保存本地最小值，以通过 **GetMin** 调用将其返回给提供程序。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

将最小值初始化为 1。 服务提供程序可以通过调用 **IMAPIProgress::SetLimits** 方法重置此值。 有关如何实现 **GetMin** 和其他 [IMAPIProgress](imapiprogressiunknown.md) 方法的详细信息，请参阅 [实现进度指示器](implementing-a-progress-indicator.md)。
  
有关如何调用进度对象以及何时调用的详细信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProgress.cpp  <br/> |CMAPIProgress::GetMin  <br/> |MFCMAPI 使用 **IMAPIProgress::GetMin** 方法获取进度指示器的最小值。 除非之前通过调用 **IMAPIProgress::SetLimits** 方法设置了限制，否则返回 1。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProgress::GetMax](imapiprogress-getmax.md)
  
[IMAPIProgress::Progress](imapiprogress-progress.md)
  
[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[显示进度指示器](how-to-display-a-progress-indicator.md)
  
[实现进度指示器](implementing-a-progress-indicator.md)

