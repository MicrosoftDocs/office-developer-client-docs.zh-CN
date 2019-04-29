---
title: MAPI 进度对象
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
# <a name="mapi-progress-objects"></a>MAPI 进度对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用进度对象的方法和数据, 可以控制指示器报告进度的方式。 虽然客户端或 MAPI 实现了进度对象, 但确保进度显示正确的大部分负担在服务提供商上。 您可以通过为传递给进度对象方法的参数指定特定的顺序和值来保证其准确性。
  
将以下参数传递给进度对象:
  
- 使用[IMAPIProgress:: SetLimits](imapiprogress-setlimits.md)设置的标志的位掩码, 并使用[IMAPIProgress:: GetFlags](imapiprogress-getflags.md)进行检索。
    
- 使用**SetLimits**设置的最小值 (本地和全局), 使用[IMAPIProgress:: GetMin](imapiprogress-getmin.md)进行检索。
    
- 使用**SetLimits**设置的最大值 (本地和全局), 使用[IMAPIProgress:: GetMax](imapiprogress-getmax.md)进行检索。
    
- 一个值, 该值指示传递给 IMAPIProgress 的当前完成的操作百分比[::P rogress](imapiprogress-progress.md)。
    
- 已传递到**进度**的已处理的对象数的计数。
    
- 传递给**进度**的操作中涉及的对象总数的计数。
    
所有服务提供程序都通过调用**IMAPIProgress:: GetFlags**检索显示的标志设置来开始处理其进度显示处理。 目前, 只能将标志设置为 MAPI_TOP_LEVEL。 客户端和 MAPI 将标志初始化为 MAPI_TOP_LEVEL, 并依赖服务提供程序在适当的时候将其清除。 
  
在处理操作中的顶级对象时, flags 值设置为 MAPI_TOP_LEVEL。 顶级对象是由客户端调用以开始操作的对象。 在文件夹复制操作中, 这是要复制的文件夹。 在文件夹删除操作中, 这是要删除的文件夹。 当您调用处理较低级别对象 (或子对象) 时, 请清除 flags 值。 在文件夹复制操作中, 子文件夹是要复制的文件夹中的子文件夹。 
  
MAPI 允许您区分顶级对象和子对象与 MAPI_TOP_LEVEL 标志, 以便操作中涉及的所有对象都可以使用相同的[IMAPIProgress](imapiprogressiunknown.md)实现来显示进度, 从而导致指示器显示在一个积极方向上顺利进行。 无论 MAPI_TOP_LEVEL 标志是否设置会影响对进度对象的后续调用中的其他参数的设置。 
  
由于可以将其设置为 nontrivial, 以便为多级操作的所有级别上的进度显示设置适当的参数值, 因此一些服务提供程序选择不显示子数据的进度。 
  
 **避免显示子进程的进度**
  
- 在调用中为处理子过程的_lpProgress_参数传递 NULL。 例如, 如果要复制文件夹, 这就是对子文件夹的[IMAPIFolder:: CopyFolder](imapifolder-copyfolder.md)方法的调用。 
    
- 编写特殊代码以确定如何解释_lpProgress_参数。 由于_lpProgress_参数的 NULL 值也可能意味着客户端应使用 MAPI 实现来显示进度, 因此需要特殊代码来确定何时忽略_lpProgress_参数以及何时调用[IMAPISupport::D oprogressdialog](imapisupport-doprogressdialog.md)。
    
调用**IMAPIProgress:: SetLimits**以设置或清除 MAPI_TOP_LEVEL 标志并设置本地和全局最小值和最大值。 flags 设置的值会影响进度对象是否理解为本地或全局的最小值和最大值。 设置 MAPI_TOP_LEVEL 标志后, 这些值被视为全局值, 用于计算整个操作的进度。 进度对象将全局最小值初始化为 0, 将全局最大值初始化为1000。 
  
如果未设置 MAPI_TOP_LEVEL, 最小值和最大值将被视为本地值, 并由提供程序在内部使用, 以显示较低级别的子数据的进度。 进度对象仅保存本地最小值和最大值, 以便在**GetMin**和**GetMax**调用时可以将其返回到提供程序。 
  
值、对象数和对象总计参数是**IMAPIProgress::P rogress**方法的输入。 value 参数 (一个指示进度百分比的数字) 是必需的。 如果设置了 MAPI_TOP_LEVEL 标志, 则还可以传递对象数和对象总数。 有些客户端使用这些值来显示一个短语, 如 "5 个项目已完成10个" (带有进度指示器)。 可以严格将操作的进度报告为百分比, 也可以根据处理的待处理的项目数的百分比形式报告。 例如, 如果您是一封邮件存储提供程序, 并且正在执行复制10个文件夹的复制操作, 则通过显示一个短语 (如 "1 个, 共10个"、"2 of 10"、"3 of 10"), 进度指示器可以为用户提供其他信息。等, 直到操作完成。 
  
## <a name="see-also"></a>另请参阅



[MAPI 进度指示器](mapi-progress-indicators.md)

