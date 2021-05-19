---
title: 实现进度指示器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3a062a88-e87e-4c0c-944e-544a8f080930
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6972c960705c336aa6ff96d81b48ccbd490a22ee
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435094"
---
# <a name="implementing-a-progress-indicator"></a>实现进度指示器

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端启动的许多操作需要很长时间。 这些可能冗长的操作的输入参数之一是指向进度对象的指针— 实现 [IMAPIProgress ： IUnknown](imapiprogressiunknown.md) 接口的对象。 进度对象控制进度指示器的外观和显示，由客户端和 MAPI 实现。 可以选择是否实现进度对象。 如果您选择不提供实现，则服务提供商可以使用 MAPI 实现。 
  
Progress 对象处理以下数据片段：
  
- 全局最小值，在调用 [IMAPIProgress：:P rogress](imapiprogress-progress.md) 方法时，应当小于或等于  _ulValue_ 参数的值。 在操作开始时  _，ulValue_ 将等于此最小值。 
    
- 全局最大值，当调用 **IMAPIProgress：:P rogress** 方法时，该值应大于或等于  _ulValue_ 参数。 在操作结束时  _，ulValue_ 将等于此最大值。 
    
- 一个标志值，指示进度是否对应于顶级项或较低级别项目。
    
- 一个值，指示操作的当前进度级别。
    
- 当前处理的项数（相对于总数）。
    
- 操作过程中要处理的项目总数。
    
最小值和最大值表示数字形式的操作开始和结束。 使用 1 作为初始最小值，使用 1000 作为初始最大值，将这些值传递给 [IMAPIProgress：：GetMin](imapiprogress-getmin.md) 和 [IMAPIProgress：：GetMax](imapiprogress-getmax.md) 方法中的服务提供商。 服务提供商在调用 [IMAPIProgress：：SetLimits 时重置这些值](imapiprogress-setlimits.md)。 
  
服务提供程序使用标志值来确定它们如何设置其他值。 初始化标志值以MAPI_TOP_LEVEL **GetFlags** 的实现中返回此值，直到服务提供商通过调用 **SetLimits 重置它**。 
  
在 **SetLimits** 方法的实现中，保存每个参数的本地副本 _：lpulMin、lpulMax_ 和 _lpulFlags_。  当服务提供商调用 **GetMin、GetMax** 或 **GetFlags** 方法时，这些值应该随时可用。  
  
若要更新进度指示器的显示，服务提供商调用 **IMAPIProgress：:P rogress** 方法。 此方法有三个参数：值、计数和总计。 使用第一个参数  _ulValue_ 显示进度指示器。 _ulValue_ 参数是进度指示器，仅在操作开始时等于 global _ulMin，_ 仅在操作完成时等于 global _ulMax。_ 
  
使用第二个参数和第三个参数  _ulCount_ 和  _ulTotal（_ 如果可用）显示可选消息，如"5 个项目已完成，全部 10 项"。 如果第二个参数和第三个参数设置为 0，可以选择是否直观地更改进度指示器。 某些服务提供商将这些参数设置为零，以指示它们正在处理其进度相对于父对象监视的子对象。 在这种情况下，仅在父对象报告进度时更改显示是有意义的。 某些服务提供商每次为这些参数传递零。 
  

