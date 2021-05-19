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
ms.openlocfilehash: 3cf639286a504b9edb600214d13dbe50710e76a9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435493"
---
# <a name="imapiprogressprogress"></a>IMAPIProgress::Progress

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
更新进度指示器，并显示在操作完成时的进度。 
  
```cpp
HRESULT Progress(
  ULONG ulValue,
  ULONG ulCount,
  ULONG ulTotal
);
```

## <a name="parameters"></a>参数

 _ulValue_
  
> [in]一个数字，指示当前进度级别 (从 _ulCount_ 和 _ulTotal_ 参数计算，或者从 [IMAPIProgress：：SetLimits](imapiprogress-setlimits.md)方法的 _lpulMin_ 和 _lpulMax_ 参数计算) 在全局下限和全局上限之间计算。 
    
 _ulCount_
  
> [in]一个数字，指示当前处理的项目相对于总数。
    
 _ulTotal_
  
> [in]操作过程中要处理的项目总数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 进度指示器已成功更新。
    
## <a name="notes-to-implementers"></a>针对实现者的说明

_ulValue_ 参数仅在操作开始时等于全局最小值，并且仅在操作完成时等于全局最大值。 
  
使用  _ulCount_ 和  _ulTotal_ 参数（如果可用）显示可选消息，例如"5 个项目已完成，其中 10 项已完成"。 如果  _ulCount_ 和  _ulTotal_ 设置为 0，请决定是否直观地更改进度指示器。 某些服务提供商将这些参数设置为 0，以指示它们正在处理其进度相对于父对象监视的子对象。 在这种情况下，仅在父对象报告进度时更改显示是有意义的。 某些服务提供商每次为这些参数传递 0。 
  
若要详细了解如何实现 **进度和其他** [IMAPIProgress](imapiprogressiunknown.md) 方法，请参阅 [实现进度指示器](implementing-a-progress-indicator.md)。
  
## <a name="notes-to-callers"></a>给调用方的说明

**IMAPIProgress：:P参数并非全部** 是必需的。 唯一需要的参数是  _ulValue，_ 一个数字，指示进度百分比。 如果MAPI_TOP_LEVEL，则还可以传递对象计数和对象总数。 某些实现使用这些值来显示一个短语，如"5 个项目已完成，其中 10 个项目"具有进度指示器。 
  
如果要复制单个文件夹中的所有邮件，将  _ulTotal_ 设置为要复制的邮件总数。 如果要复制文件夹，将  _ulTotal_ 设置为文件夹中子文件夹的数量。 如果要复制的文件夹不包含子文件夹和仅邮件，则将  _ulTotal_ 设置为 1。 
  
有关如何调用进度对象以及何时调用的详细信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProgress.cpp  <br/> |CMAPIProgress：:P rogress  <br/> |MFCMAPI 使用 **IMAPIProgress：:P rogress** 方法使用当前进度百分比更新 MFCMAPI 状态栏，该进度百分比是根据  _uValue_ 以及当前最大值和最小值计算的。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[显示进度指示器](how-to-display-a-progress-indicator.md)
  
[实现进度指示器](implementing-a-progress-indicator.md)

