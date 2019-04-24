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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270299"
---
# <a name="imapiprogressprogress"></a>IMAPIProgress::Progress

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将进度指示器更新为在完成操作时显示进度。 
  
```cpp
HRESULT Progress(
  ULONG ulValue,
  ULONG ulCount,
  ULONG ulTotal
);
```

## <a name="parameters"></a>参数

 _ulValue_
  
> 实时一个数字, 表示当前的进度级别 (从_ulCount_和_ulTotal_参数计算, 或从[IMAPIProgress:: SetLimits](imapiprogress-setlimits.md)方法的_lpulMin_和_lpulMax_参数中计算) 在全局下限和全局上限。 
    
 _ulCount_
  
> 实时一个指示当前处理的项相对于总数的数字。
    
 _ulTotal_
  
> 实时操作过程中要处理的项目总数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功更新进度指示器。
    
## <a name="notes-to-implementers"></a>针对实现者的说明

只有在操作完成时, _ulValue_参数才等于全局最小值, 且仅在操作完成时为全局最大值。 
  
使用_ulCount_和_ulTotal_参数 (如果可用) 显示可选的消息, 如 "5 个项目已完成10个"。 如果_ulCount_和_ulTotal_设置为 0, 则决定是否以可视方式更改进度指示器。 某些服务提供程序将这些参数设置为 0, 以指示它们正在处理其进度受监视的子对象相对于父对象。 在这种情况下, 仅在父对象报告进度时更改显示是有意义的。 某些服务提供程序每次都为这些参数传递0。 
  
有关如何实施**进度**和其他[IMAPIProgress](imapiprogressiunknown.md)方法的详细信息, 请参阅[实现进度指示器](implementing-a-progress-indicator.md)。
  
## <a name="notes-to-callers"></a>给调用方的说明

不是 IMAPIProgress 的所有三个参数都是必需的 **::P rogress** 。 唯一必需的参数是_ulValue_(一个指示进度百分比的数字)。 如果设置了 MAPI_TOP_LEVEL 标志, 则还可以传递对象数和对象总数。 某些实现使用这些值来显示一个短语, 如 "5 个项目已完成10个" (带有进度指示器)。 
  
如果要复制单个文件夹中的所有邮件, 请将_ulTotal_设置为要复制的邮件总数。 如果要复制文件夹, 请将_ulTotal_设置为该文件夹中的子文件夹数。 如果要复制的文件夹不包含子文件夹且仅包含邮件, 则将_ulTotal_设置为1。 
  
有关如何调用进度对象以及何时调用的详细信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProgress.cpp  <br/> |CMAPIProgress::P rogress  <br/> |MFCMAPI 使用**IMAPIProgress::P rogress**方法更新 MFCMAPI 状态栏, 该状态栏的当前进度百分比, 从_uValue_计算, 以及当前的最大值和最小值。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[显示进度指示器](how-to-display-a-progress-indicator.md)
  
[实现进度指示器](implementing-a-progress-indicator.md)

