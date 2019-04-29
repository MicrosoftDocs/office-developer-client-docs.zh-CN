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
  
客户端启动的许多操作花费的时间很长。 这些可能漫长的操作的输入参数之一是指向进度对象的指针, 该对象是一个实现[IMAPIProgress: IUnknown](imapiprogressiunknown.md)接口的对象。 进度对象控制进度指示器的外观和显示, 并由客户端和 MAPI 实现。 您可以选择是否实现进度对象。 如果选择不提供实现, 则可使用 MAPI 实施服务提供商。 
  
进度对象使用以下数据片段:
  
- 一个全局最小值, 在调用[IMAPIProgress::P rogress](imapiprogress-progress.md)方法时, 应小于或等于_ulValue_参数的值。 在操作开始时, _ulValue_将等于此最小值。 
    
- 当调用**IMAPIProgress::P rogress**方法时, 全局最大值应大于或等于_ulValue_参数。 在操作结束时, _ulValue_将等于此最大值。 
    
- 一个标志值, 指示进度是否对应于顶层或较低级别的项。
    
- 一个指示操作的当前进度级别的值。
    
- 当前处理的项相对于总数的数目。
    
- 操作过程中要处理的项目总数。
    
最小值和最大值代表数字形式的操作的开始和结束。 使用1作为初始最小值, 并1000将这些值传递给[IMAPIProgress:: GetMin](imapiprogress-getmin.md)和[IMAPIProgress:: GetMax](imapiprogress-getmax.md)方法中的服务提供程序。 服务提供程序在调用[IMAPIProgress:: SetLimits](imapiprogress-setlimits.md)时重置这些值。 
  
"flags" 值由服务提供商用来确定应如何设置其他值。 将 flags 值初始化为 MAPI_TOP_LEVEL, 并在**GetFlags**的实现中返回此值, 直到服务提供程序通过调用**SetLimits**重置它。 
  
在**SetLimits**方法的实现中, 保存每个参数的本地副本: _lpulMin_、 _lpulMax_和_lpulFlags_。 当服务提供商调用您的**GetMin**、 **GetMax**或**GetFlags**方法时, 这些值应易于使用。 
  
若要更新进度指示器的显示, 服务提供商将呼叫您的**IMAPIProgress::P rogress**方法。 此方法有三个参数: 值、计数和总计。 使用第一个参数_ulValue_显示进度指示器。 _ulValue_参数是进度指示器, 它将等于全局_ulMin_仅在操作开始时等于全局 ulMax, 并且仅在操作完成时才等于全局__ 。 
  
使用第二个和第三个参数_ulCount_和_ulTotal_(如果可用) 显示可选的消息, 如 "5 个项目已完成10次"。 如果第二个和第三个参数设置为 0, 则可以选择是否以可视方式更改进度指示器。 某些服务提供程序将这些参数设置为零, 以指示它们正在处理其进度受监视的子对象相对于父对象。 在这种情况下, 仅在父对象报告进度时更改显示是有意义的。 某些服务提供程序每次传递这些参数的零。 
  

