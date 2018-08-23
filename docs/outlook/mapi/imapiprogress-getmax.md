---
title: IMAPIProgressGetMax
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProgress.GetMax
api_type:
- COM
ms.assetid: 88a910ed-b55a-4e5b-a43d-eb3ea795a70e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2dadad410b9aaf1401d792de373e561c29183a12
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567235"
---
# <a name="imapiprogressgetmax"></a>IMAPIProgress::GetMax

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
对于的进度的信息将显示的操作中返回的最大项目数。
  
```cpp
HRESULT GetMax(
  ULONG FAR * lpulMax
);
```

## <a name="parameters"></a>参数

 _lpulMax_
  
> [输出]一个指向的最大操作中的项目数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已检索的最大操作中的项目数。
    
## <a name="remarks"></a>注解

最大值表示数字的窗体中的操作的末尾。 值可以是全局的最大值，用于表示显示整个进度的范围或本地值，用于表示仅显示的一部分。 
  
是否正在进行对象能够理解的最大值为本地域或全局设置会影响标志的值。 当设置 MAPI_TOP_LEVEL 标志时，最大值被视为全局和用于计算整个操作的进度。 时未设置 MAPI_TOP_LEVEL，最大值被视为本地，并提供程序将其内部来显示较低级别的子对象的进度。 进度对象保存仅使它返回到通过**GetMax**呼叫提供程序的本地最大值。 
  
有关详细了解如何以及何时调用进度对象，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="notes-to-implementers"></a>针对实施者的注释

初始化的最大值为 1000年。 服务提供商可以通过调用[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)方法重置此值。 有关如何实施**GetMax**和其他[IMAPIProgress](imapiprogressiunknown.md)方法的详细信息，请参阅[实现进度指示器](implementing-a-progress-indicator.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIProgress.cpp  <br/> |CMAPIProgress::GetMax  <br/> |MFCMAPI 使用**IMAPIProgress::GetMax**方法来获取进度对象的最大值。 除非限制之前已经设置了与**IMAPIProgress::SetLimits**方法返回 1000年。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProgress::GetMin](imapiprogress-getmin.md)
  
[IMAPIProgress::Progress](imapiprogress-progress.md)
  
[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[显示进度指示器](how-to-display-a-progress-indicator.md)
  
[实现进度指示器](implementing-a-progress-indicator.md)

