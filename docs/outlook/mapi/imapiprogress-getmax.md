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
ms.openlocfilehash: 64b6235151c7700a24992bc1d4394553a53c0464
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436200"
---
# <a name="imapiprogressgetmax"></a>IMAPIProgress::GetMax

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回显示其进度信息的操作中的最大项目数。
  
```cpp
HRESULT GetMax(
  ULONG FAR * lpulMax
);
```

## <a name="parameters"></a>参数

 _lpulMax_
  
> 排除一个指针, 指向操作中的最大项目数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已检索到操作中的最大项目数。
    
## <a name="remarks"></a>说明

最大值表示以数字形式的运算的结束。 该值可以是全局最大值，用于表示整个进度显示的范围，也可以是本地值，用于仅表示显示的一部分。 
  
标记设置的值影响进度对象是否理解为本地或全局的最大值。 设置 MAPI_TOP_LEVEL 标志后, 最大值将被视为全局值, 用于计算整个操作的进度。 如果未设置 MAPI_TOP_LEVEL, 则将最大值视为本地, 并且提供程序在内部使用它来显示较低级别子集的进度。 进度对象仅保存本地最大值, 以通过**GetMax**调用将其返回给提供程序。 
  
有关如何调用进度对象以及何时调用的详细信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

将最大值初始化为1000。 服务提供程序可以通过调用 [IMAPIProgress::SetLimits](imapiprogress-setlimits.md) 方法重置此值。 有关如何实现**GetMax**和其他[IMAPIProgress](imapiprogressiunknown.md)方法的详细信息, 请参阅[实现进度指示器](implementing-a-progress-indicator.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProgress.cpp  <br/> |CMAPIProgress:: GetMax  <br/> |MFCMAPI 使用**IMAPIProgress:: GetMax**方法获取进度对象的最大值。 返回 1000, 除非以前使用**IMAPIProgress:: SetLimits**方法设置了限制。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProgress::GetMin](imapiprogress-getmin.md)
  
[IMAPIProgress::Progress](imapiprogress-progress.md)
  
[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[显示进度指示器](how-to-display-a-progress-indicator.md)
  
[实现进度指示器](implementing-a-progress-indicator.md)

