---
title: IMAPIProgressProgress
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProgress.Progress
api_type:
- COM
ms.assetid: edbf7623-a64e-43b8-8379-e3cde2433d91
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2a003be35fc9c3ef8efc7c66997ee99f6e578f09
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775509"
---
# <a name="imapiprogressprogress"></a>IMAPIProgress::Progress

  
  
**适用于**： Outlook 
  
更新进度指示器进度的显示做出的操作完成。 
  
```cpp
HRESULT Progress(
  ULONG ulValue,
  ULONG ulCount,
  ULONG ulTotal
);
```

## <a name="parameters"></a>参数

 _ulValue_
  
> [in]一个数字，指示之间全局 （计算的_ulCount_和_ulTotal_参数从或[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)方法的_lpulMin_和_lpulMax_参数） 的进度的当前级别下限和全局上限。 
    
 _ulCount_
  
> [in]一个数字，表示相对于总当前处理的项目。
    
 _ulTotal_
  
> [in]在操作过程中处理的项目总数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功更新进度指示器。
    
## <a name="notes-to-implementers"></a>针对实施者的注释

_UlValue_参数将只操作的开头的全局最小值到和仅在完成该操作的全局最大值相等。 
  
使用的_ulCount_和_ulTotal_参数，如果可用，以显示可选消息，例如"5 项目完成 10。" 如果_ulCount_和_ulTotal_都设为 0，决定是否以可视方式更改进度指示器。 某些服务提供商将这些参数设置为 0，以指示它们处理相对于父对象监视其进度的子对象。 在此情况下，有意义的父对象报告进度时仅显示更改。 某些服务提供商传递为这些参数的 0 每次。 
  
有关如何实施**进度**和其他[IMAPIProgress](imapiprogressiunknown.md)方法的详细信息，请参阅[实现进度指示器](implementing-a-progress-indicator.md)。
  
## <a name="notes-to-callers"></a>给调用方的说明

并非所有三个向**IMAPIProgress::Progress**参数都是必需的。 所需的唯一参数是_ulValue_，一个数字，指示正在进行的百分比。 如果设置了 MAPI_TOP_LEVEL 标志，您还可以传递对象计数和对象的汇总。 某些实现使用这些值来显示进度指示器的短语，例如"5 项目完成 10"。 
  
如果要将所有邮件都复制到一个文件夹中，设置_ulTotal_为复制的消息的总数。 如果要复制的文件夹，设置_ulTotal_到文件夹中的子文件夹数。 如果要复制的文件夹中包含没有子文件夹和仅邮件，设置为 1 _ulTotal_ 。 
  
有关详细了解如何以及何时调用进度对象，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIProgress.cpp  <br/> |CMAPIProgress::Progress  <br/> |MFCMAPI 使用**IMAPIProgress::Progress**方法使用当前的进度，从_uValue_和当前的最大和最小值计算百分比更新 MFCMAPI 状态栏。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[显示进度指示器](how-to-display-a-progress-indicator.md)
  
[实现进度指示器](implementing-a-progress-indicator.md)

