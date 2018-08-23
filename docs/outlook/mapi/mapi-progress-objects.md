---
title: MAPI 进度对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e446004e-1ef2-4e58-b764-de7b4dcefaf1
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c6079a62464231536c0fa6b5bacc291997fe38d9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567921"
---
# <a name="mapi-progress-objects"></a>MAPI 进度对象

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
使用的方法和进度对象的数据，您可以控制如何标记报告进度。 客户端或 MAPI 实现进度对象，虽然大部分的负担，确保正确的进度显示属于服务提供商。 您可以通过指定特定的顺序和传递给进度对象方法的参数值保证其准确性。
  
以下参数传递给进度对象：
  
- 标志，与[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)设置和检索与[IMAPIProgress::GetFlags](imapiprogress-getflags.md)的位掩码。
    
- （本地和全局） 的最小值与**SetLimits**设置，并检索与[IMAPIProgress::GetMin](imapiprogress-getmin.md)。
    
- （本地和全局） 的最大值与**SetLimits**设置，并检索与[IMAPIProgress::GetMax](imapiprogress-getmax.md)。
    
- 一个值，指示当前操作，传递给[IMAPIProgress::Progress](imapiprogress-progress.md)完成百分比。
    
- 到目前为止已处理，传递给**进度**的对象数的计数。
    
- 操作，传递给**进度**中所涉及的对象的总数的计数。
    
所有服务提供商都开始处理与**IMAPIProgress::GetFlags**到呼叫中以检索存在标志设置其进行显示。 目前，可以仅对 MAPI_TOP_LEVEL 设置标志。 客户端和 MAPI 初始化 MAPI_TOP_LEVEL，标志依赖于服务提供商，以将其适当时清除。 
  
Flags 值设置为 MAPI_TOP_LEVEL 时您正在使用操作中的顶级对象。 顶级对象是由客户端开始操作调用的对象。 在文件夹复制操作，这是要复制的文件夹。 在文件夹删除操作中，这是要删除的文件夹。 当您进行的呼叫处理较低的 level 对象或子对象，请清除该标志值。 在文件夹复制操作，子对象是要复制的文件夹中的子文件夹。 
  
MAPI 允许您区分顶级对象，并与 MAPI_TOP_LEVEL 标志的子对象，以便在操作中涉及的所有对象可以使用相同的[IMAPIProgress](imapiprogressiunknown.md)实现以显示进度，从而导致到标记显示顺利的一个正数方向。 设置了 MAPI_TOP_LEVEL 标志会影响的后面对进度对象中的其他参数的设置。 
  
由于可能很重要多级操作的所有级别设置适当的参数值的进度显示，某些服务提供商选择不显示进度的子对象。 
  
 **若要避免显示进度的子对象**
  
- 呼叫处理子对象中的_lpProgress_参数传递 NULL。 例如，如果要复制的文件夹，这是对的子文件夹[IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)方法的调用。 
    
- 编写特殊代码以确定如何解释_lpProgress_参数。 因为_lpProgress_参数的 NULL 值还意味着在客户端，应使用 MAPI 实现显示进度，都需要以确定何时忽略_lpProgress_参数以及何时调用[特殊代码IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)。
    
调用**IMAPIProgress::SetLimits**设置或清除 MAPI_TOP_LEVEL 标志并设置本地和全局最小和最大值。 是否设置会影响 flags 的值的进度对象可识别为本地域或全局的最小和最大值。 当设置 MAPI_TOP_LEVEL 标志时，这些值将被视为全局并用于计算整个操作的进度。 进度对象初始化为 0 的全局最小值和全局最大值为 1000年。 
  
当不设置 MAPI_TOP_LEVEL 时，最小和最大值将被视为本地并用于内部由提供商提供显示正在进行较低级别的子对象。 进度对象仅，以便他们可以返回到提供程序时调用**GetMin**和**GetMax**保存本地的最小和最大值。 
  
值对象计数和对象总参数是输入**IMAPIProgress::Progress**方法。 需要 value 参数，一个数字，指示的进度，百分比。 如果设置了 MAPI_TOP_LEVEL 标志，您还可以传递对象计数和对象的汇总。 某些客户端使用这些值显示进度指示器的短语，例如"5 项目完成 10"。 以百分比形式或百分比和已处理的总处理出的项目数方面可以严格报告上操作的进度。 例如，如果您是消息存储提供程序，并且您执行复制 10 文件夹复制操作，进度指示器可以提供的其他信息的用户通过显示"10 的 1"、"为 10 2"、"3 为 10"等的短语操作完成之前，依此类推。 
  
## <a name="see-also"></a>另请参阅



[MAPI 进度指示器](mapi-progress-indicators.md)

