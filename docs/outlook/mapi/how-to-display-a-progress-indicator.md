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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345127"
---
# <a name="display-a-progress-indicator"></a>显示进度指示器
 
**适用于**：Outlook 2013 | Outlook 2016 
  
若要显示进度指示器, 请调用[IMAPIProgress:: GetFlags](imapiprogress-getflags.md)以检索当前标记设置。 
  
如果设置了 MAPI_TOP_LEVEL 标志, 请完成以下步骤:
  
1. 将变量设置为与操作中要处理的总项数相同。 例如, 如果要复制文件夹的内容, 此值将等于文件夹中的子文件夹数加上邮件数。 
    
2. 设置一个等于1000的变量除以项目数。 
    
3. 如果要显示子对象的进度, 请调用进度对象的[IMAPIProgress:: SetLimits](imapiprogress-setlimits.md)方法, 并为三个参数传递以下值: 
    
   - 将_lpulMin_参数设置为0。 
    
   - 将_lpulMax_参数设置为1000。 
    
   - 将_lpulFlags_参数设置为 MAPI_TOP_LEVEL。 
    
4. 对于要处理的每个对象, 请完成以下步骤:
    
   1. 调用**IMAPIProgress:: SetLimits**并为三个参数传递以下值: 
      
     - 将在步骤2中设置的变量的_lpulMin_参数设置为当前项减去1的乘积。 
      
     - 将_lpulMax_参数设置为第2步中的变量集与当前对象的乘积。 
      
     - 将_lpulFlags_参数设置为0。 
      
   2. 执行应对此对象执行的任何处理。 如果这是一个子对象, 并且您想要显示子对象的进度, 请将指向该方法的_lpProgress_参数中的进度对象的指针传递给该方法。 
      
   3. 调用[IMAPIProgress::P rogress](imapiprogress-progress.md)并为三个参数传递以下值: 
      
     - 将_ulValue_参数设置为第2步中的变量集与当前对象的乘积。 
      
     - 将_ulCount_参数设置为当前对象。 
      
     - 将_ulTotal_参数设置为第1步中的变量集, 即对象的总数。 
    
如果未设置 MAPI_TOP_LEVEL 标志, 请完成以下步骤:
  
1. 调用进度对象的[IMAPIProgress:: GetMin](imapiprogress-getmin.md)方法以检索显示的最小值。 
    
2. 调用[IMAPIProgress:: GetMax](imapiprogress-getmax.md)检索显示的最大值。 
    
3. 将变量设置为与要处理的对象总数相等的值。 
    
4. 将变量设置为与最大值相减的最小值, 然后除以对象总数所得的结果。
    
5. 对于要处理的每个对象, 请完成以下步骤:
    
   1. 如果提供程序显示子数据子数据的进度, 则调用**IMAPIProgress:: SetLimits** , 并为三个参数传递以下值: 
      
     - 将_lpulMin_参数设置为最小值加上当前项目减去1乘以步骤4中的变量集。 
      
     - 将_lpulMax_参数设置为最小值加上当前单位乘以步骤4中的变量集。 
      
     - 将_lpulFlags_参数设置为0。 
      
   2. 执行应对此对象执行的任何处理。 如果对象是一个子对象, 并且您的提供程序显示子对象的进度, 则将指向该方法的_lpProgress_参数中的进度对象的指针传递给该方法。 
      
   3. 调用[IMAPIProgress::P rogress](imapiprogress-progress.md)并为三个参数传递以下值: 
      
     - 将步骤2中的变量集的_ulValue_参数设置为当前对象的乘积。 
      
     - 将_ulCount_参数设置为0。 
      
     - 将_ulTotal_参数设置为0。 
    
下面的代码示例演示在复制包含五个子文件夹的文件夹内容的操作的所有级别上显示进度所需的逻辑。 
  
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

