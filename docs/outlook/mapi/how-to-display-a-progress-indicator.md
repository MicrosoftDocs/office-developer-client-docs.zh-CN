---
title: 显示进度指示器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 20f5ad5a-b700-4fb5-9658-f71da5a06a12
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7b0ce0ab75ffdce045ccde5bf6ea8a7da046f463
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408024"
---
# <a name="display-a-progress-indicator"></a>显示进度指示器
 
**适用于**：Outlook 2013 | Outlook 2016 
  
若要显示进度指示器，请调用 [IMAPIProgress：：GetFlags](imapiprogress-getflags.md) 以检索当前标志设置。 
  
如果MAPI_TOP_LEVEL，请完成以下步骤：
  
1. 将变量设置为等于操作中要处理的项目总数。 例如，如果要复制文件夹的内容，则此值将等于文件夹中子文件夹的数量以及邮件数。 
    
2. 将变量设置为等于 1000 除以项目数。 
    
3. 如果要显示子对象的进度，请调用进度对象的 [IMAPIProgress：：SetLimits](imapiprogress-setlimits.md) 方法，并传递以下三个参数的值： 
    
   - 将  _lpulMin_ 参数设置为 0。 
    
   - 将  _lpulMax_ 参数设置为 1000。 
    
   - 将  _lpulFlags_ 参数设置为 MAPI_TOP_LEVEL。 
    
4. 对于要处理的每个对象，请完成以下步骤：
    
   1. 调用 **IMAPIProgress：：SetLimits** 并传递以下三个参数的值： 
      
     - 将  _lpulMin_ 参数设置为步骤 2 乘以当前项减 1 中设置的变量。 
      
     - 将  _lpulMax_ 参数设置为步骤 2 中与当前对象相乘的变量集。 
      
     - 将  _lpulFlags_ 参数设置为 0。 
      
   2. 对此对象执行应执行的任何处理。 如果这是一个子对象，并且您希望显示子对象上的进度，则向该方法传递指向  _lpProgress_ 参数中 progress 对象的指针。 
      
   3. 调用 [IMAPIProgress：:P rogress](imapiprogress-progress.md) 并传递以下三个参数的值： 
      
     - 将  _ulValue_ 参数设置为步骤 2 中与当前对象相乘的变量集。 
      
     - 将  _ulCount_ 参数设置为当前对象。 
      
     - 将  _ulTotal_ 参数设置为步骤 1 中设置的变量（对象总数）。 
    
如果未MAPI_TOP_LEVEL，请完成以下步骤：
  
1. 调用进度对象的 [IMAPIProgress：：GetMin](imapiprogress-getmin.md) 方法来检索显示器的最小值。 
    
2. 调用 [IMAPIProgress：：GetMax](imapiprogress-getmax.md) 以检索显示器的最大值。 
    
3. 设置一个等于要处理的对象总数的变量。 
    
4. 将变量设置为等于最大值减去最小值后除以对象总数的结果。
    
5. 对于要处理的每个对象，请完成以下步骤：
    
   1. 如果提供程序显示子对象的进度，请调用 **IMAPIProgress：：SetLimits** 并传递以下三个参数的值： 
      
     - 将  _lpulMin_ 参数设置为最小值加上当前项减去 1 乘以步骤 4 中设置的变量。 
      
     - 将  _lpulMax_ 参数设置为最小值加上当前单位乘以步骤 4 中设置的变量。 
      
     - 将  _lpulFlags_ 参数设置为 0。 
      
   2. 对此对象执行应执行的任何处理。 如果对象是子对象，并且您的提供程序显示子对象的进度，则向该方法传递指向  _lpProgress_ 参数中 progress 对象的指针。 
      
   3. 调用 [IMAPIProgress：:P rogress](imapiprogress-progress.md) 并传递以下三个参数的值： 
      
     - 将  _ulValue_ 参数设置为步骤 2 中与当前对象相乘的变量集。 
      
     - 将  _ulCount 参数_ 设置为 0。 
      
     - 将  _ulTotal_ 参数设置为 0。 
    
以下代码示例演示了在复制包含五个子文件夹的文件夹的内容的操作的所有级别显示进度所需的逻辑。 
  
```cpp
lpProgress->GetFlags (lpulFlags);
ulFlags = *lpulFlags;
/* The folder in charge of the display. It contains 5 subfolders. */
if (ulFlags & MAPI_TOP_LEVEL)
{
    ulItems = 5                         // 5 subfolders in this folder
    ulScale = (ulMax / ulItems)         // 200 because ulMax = 1000
    lpProgress->SetLimits(0, ulMax, MAPI_TOP_LEVEL)
    for (i = 1; i <= ulItems; i++)      // for each subfolder to copy
    {
        lpProgress->SetLimits( (i - 1) * ulScale, i * ulScale, 0)
        CopyOneFolder(lpFolder(i), lpProgress)
        lpProgress->Progress( i * ulScale, i, ulItems)
    }
}
else
/* One of the subfolders to be copied. It contains 3 messages. */
{
    lpProgress->GetMin(&ulMin);
    lpProgress->GetMax(&ulMax);
    ulItems = 3;
    ulDelta = (ulMax - ulMin) / ulItems;
    for (i = 1; i <= ulItems; i++)
    {
        lpProgress->SetLimits(ulMin + (i - 1) * ulDelta,
                              ulMin + i * ulDelta, 0)
        CopyOneFolder(lpFolder(i), lpProgress)
        /* Pass 0 for ulCount and ulTotal because this is not the */
        /* top-level display, and that information is unavailable  */
        lpProgress->Progress( i * ulDelta, 0, 0)
    }
}
 
```

## <a name="see-also"></a>另请参阅

- [MAPI 进度指示器](mapi-progress-indicators.md)

