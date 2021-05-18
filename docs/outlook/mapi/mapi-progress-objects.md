---
title: MAPI Progress 对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e446004e-1ef2-4e58-b764-de7b4dcefaf1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 73d905028f8f62ad8cbb9da9b1ad61b8cab1065e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422024"
---
# <a name="mapi-progress-objects"></a>MAPI Progress 对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用进度对象的方法和数据，可以控制指示器报告进度的方式。 虽然客户端或 MAPI 实现了进度对象，但确保进度显示正确无误的多数负担都由服务提供商承担。 通过为传递给 progress 对象方法的参数指定特定顺序和值，可以保证其准确性。
  
以下参数将传递给 progress 对象：
  
- 标志的位掩码，使用 [IMAPIProgress：：SetLimits](imapiprogress-setlimits.md) 设置，使用 [IMAPIProgress：：GetFlags 检索](imapiprogress-getflags.md)。
    
- 本地和全局 (的最小值) **SetLimits** 设置，然后使用 [IMAPIProgress：：GetMin 检索](imapiprogress-getmin.md)。
    
- 本地和全局 (的最大值) **SetLimits** 设置，然后使用 [IMAPIProgress：：GetMax 检索](imapiprogress-getmax.md)。
    
- 一个值，指示操作的当前完成百分比，传递给 [IMAPIProgress：:P rogress](imapiprogress-progress.md)。
    
- 到目前为止已处理的对象数的计数，传递给 **Progress**。
    
- 操作中涉及的对象总数，传递给 Progress **。**
    
所有服务提供商都通过调用 **IMAPIProgress：：GetFlags** 以检索当前标志设置开始其进度显示处理。 目前，只能将标志设置为 MAPI_TOP_LEVEL。 客户端和 MAPI 将标志初始化为MAPI_TOP_LEVEL，并依赖服务提供商在适当的时候清除它。 
  
标志值设置为 MAPI_TOP_LEVEL处理操作中的顶级对象时。 顶级对象是由客户端调用以开始操作的对象。 在文件夹复制操作中，这是要复制的文件夹。 在文件夹删除操作中，这是要删除的文件夹。 调用处理较低级别对象或子对象时，请清除 flags 值。 在文件夹复制操作中，子对象是正在复制的文件夹中的子文件夹。 
  
MAPI 允许您区分顶级对象和具有 MAPI_TOP_LEVEL 标志的子对象，以便操作中涉及的所有对象可以使用同一 [IMAPIProgress](imapiprogressiunknown.md) 实现来显示进度，从而使指示器显示在单个正方向上平稳进行。 是否设置MAPI_TOP_LEVEL标记会影响后续调用进度对象时其他参数的设置。 
  
由于在多级操作的所有级别为进度显示设置适当的参数值是非特有的，因此一些服务提供商选择不显示子对象的进度。 
  
 **避免显示子对象的进度**
  
- 在调用中为  _lpProgress_ 参数传递 NULL 以处理子对象。 例如，如果要复制文件夹，则这是对子文件夹 [的 IMAPIFolder：：CopyFolder](imapifolder-copyfolder.md) 方法的调用。 
    
- 编写特殊代码以确定如何解释  _lpProgress_ 参数。 因为 _lpProgress_ 参数的 NULL 值还意味着客户端应该使用 MAPI 实现显示进度，所以需要特殊代码来确定何时忽略 _lpProgress_ 参数以及何时调用 [IMAPISupport：:D oProgressDialog。](imapisupport-doprogressdialog.md)
    
调用 **IMAPIProgress：：SetLimits** 设置或清除 MAPI_TOP_LEVEL 标志，并设置本地和全局最小值和最大值。 标志设置的值会影响进度对象是了解最小值还是最大值是本地值还是全局值。 设置 MAPI_TOP_LEVEL 标志时，这些值被视为全局值，用于计算整个操作的进度。 Progress 对象将全局最小值初始化为 0，将全局最大值初始化为 1000。 
  
未MAPI_TOP_LEVEL时，最小值和最大值被视为本地值，供提供程序在内部用于显示较低级别的子对象的进度。 Progress 对象仅保存本地最小值和最大值，以便它们可以在 **调用 GetMin** 和 **GetMax** 时返回到提供程序。 
  
值、对象计数和对象总数参数是 **IMAPIProgress：:P rogress 方法** 的输入。 value 参数是一个指示进度百分比的数值。 如果MAPI_TOP_LEVEL，则还可以传递对象计数和对象总数。 某些客户端使用这些值显示一个短语，例如"5 个项目已完成，10 个项目已完成"以及进度指示器。 可以严格按照百分比或百分比以及已处理项目数（从要处理的项目总数中）报告操作进度。 例如，如果您是邮件存储提供程序，并且正在执行复制 10 个文件夹的复制操作，则进度指示器可以通过显示短语（如"1/10"、"2/10"、"3 of 10"等）来向用户提供其他信息，直到操作完成。 
  
## <a name="see-also"></a>另请参阅



[MAPI 进度指示器](mapi-progress-indicators.md)

