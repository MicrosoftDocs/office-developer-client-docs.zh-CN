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
ms.openlocfilehash: ab92aee6a8254a16c48352e371b711932bbe7427
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775505"
---
# <a name="imapiprogressgetmin"></a>IMAPIProgress::GetMin

  
  
**适用于**： Outlook 
  
对于的进度的信息将显示在[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)方法中返回的最小值。 
  
```cpp
HRESULT GetMin(
  ULONG FAR * lpulMin
);
```

## <a name="parameters"></a>参数

 _lpulMin_
  
> [输出]一个指向操作中的项的最小数目。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已检索的最小操作中的项目数。
    
## <a name="remarks"></a>说明

最小值表示数字形式操作的开始。 值可以是全局的最大值，用于表示显示整个进度的范围或本地值，用于表示仅显示的一部分。 
  
是否正在进行对象能够理解的最小值为本地域或全局设置会影响标志的值。 当设置 MAPI_TOP_LEVEL 标志时，最小值被视为全局和用于计算整个操作的进度。 时未设置 MAPI_TOP_LEVEL，最小值被视为本地，并提供程序将其内部来显示较低级别的子对象的进度。 进度对象保存仅使它返回到通过**GetMin**呼叫提供程序的本地最小值。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

初始化的最小值为 1。 服务提供商可以通过调用**IMAPIProgress::SetLimits**方法重置此值。 有关如何实施**GetMin**和其他[IMAPIProgress](imapiprogressiunknown.md)方法的详细信息，请参阅[实现进度指示器](implementing-a-progress-indicator.md)。
  
有关详细了解如何以及何时调用进度对象，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIProgress.cpp  <br/> |CMAPIProgress::GetMin  <br/> |MFCMAPI 使用**IMAPIProgress::GetMin**方法获取进度指示器的最小值。 除非限制先前已设置通过调用**IMAPIProgress::SetLimits**方法会返回 1。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProgress::GetMax](imapiprogress-getmax.md)
  
[IMAPIProgress::Progress](imapiprogress-progress.md)
  
[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[显示进度指示器](how-to-display-a-progress-indicator.md)
  
[实现进度指示器](implementing-a-progress-indicator.md)

