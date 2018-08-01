---
title: 显示进度指示器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 20f5ad5a-b700-4fb5-9658-f71da5a06a12
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3c4c553a000dab233eb208c1222cc427c97b1e70
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775097"
---
# <a name="display-a-progress-indicator"></a>显示进度指示器
 
**适用于**： Outlook 
  
若要显示进度指示器，请调用[IMAPIProgress::GetFlags](imapiprogress-getflags.md)检索设置的当前标志。 
  
如果设置了 MAPI_TOP_LEVEL 标志，完成以下步骤：
  
1. 将变量等于设置为要处理操作中的项的总数。 例如，如果要复制的文件夹的内容，此值将等于的文件夹中的子文件夹数加上的消息数。 
    
2. 将变量等于设置为 1000 的项目数的比率。 
    
3. 如果显示进度的子对象时，调用进度对象的[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)方法并传递的三个参数的下列值： 
    
   - _LpulMin_参数设置为 0。 
    
   - 将_lpulMax_参数设置为 1000年。 
    
   - _LpulFlags_参数设置为 MAPI_TOP_LEVEL。 
    
4. 对于处理每个对象，完成以下步骤：
    
   1. 调用**IMAPIProgress::SetLimits**并传递的三个参数的下列值： 
      
     - _LpulMin_参数设置为在步骤 2 乘以减 1 之间的当前项目中设置的变量。 
      
     - _LpulMax_参数设置为设置在步骤 2 乘以当前对象的变量。 
      
     - _LpulFlags_参数设置为 0。 
      
   2. 执行此对象应的任何处理。 如果这是子对象和您想要在子对象上显示进度，请将指针传递给方法_lpProgress_参数中的进度对象。 
      
   3. 调用[IMAPIProgress::Progress](imapiprogress-progress.md)并传递的三个参数的下列值： 
      
     - _UlValue_参数设置为设置在步骤 2 乘以当前对象的变量。 
      
     - _UlCount_参数设置为当前对象。 
      
     - _UlTotal_参数设置为在步骤 1，对象总数中设置的变量。 
    
如果未设置 MAPI_TOP_LEVEL 标志，完成以下步骤：
  
1. 调用进度对象的[IMAPIProgress::GetMin](imapiprogress-getmin.md)方法来检索显示的最小值。 
    
2. 调用[IMAPIProgress::GetMax](imapiprogress-getmax.md)检索显示的最大值。 
    
3. 将变量等于设置为要处理的对象的总数。 
    
4. 设置变量等于为减去的最大值的最小值，然后除以对象总数的结果。
    
5. 对于处理每个对象，完成以下步骤：
    
   1. 如果您的提供商显示进度的子对象，调用**IMAPIProgress::SetLimits**并传递的三个参数的下列值： 
      
     - _LpulMin_参数设置为最小值再加上当前项值减 1 的第 4 步中设置的变量。 
      
     - _LpulMax_参数设置为最小值再加上当前单位乘以第 4 步中设置的变量。 
      
     - _LpulFlags_参数设置为 0。 
      
   2. 执行此对象应的任何处理。 如果对象是子对象和您的提供商显示进度的子对象，请将指针传递给方法_lpProgress_参数中的进度对象。 
      
   3. 调用[IMAPIProgress::Progress](imapiprogress-progress.md)并传递的三个参数的下列值： 
      
     - _UlValue_参数设置为设置在步骤 2 乘以当前对象的变量。 
      
     - _UlCount_参数设置为 0。 
      
     - _UlTotal_参数设置为 0。 
    
下面的代码示例说明了显示所有级别将包含五个子文件夹的文件夹的内容复制操作的进度所需的逻辑。 
  
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

