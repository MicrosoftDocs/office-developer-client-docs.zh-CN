---
title: 实现进度指示器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3a062a88-e87e-4c0c-944e-544a8f080930
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1a359ec413da91b3e2819978e80ea0a921f6b245
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587122"
---
# <a name="implementing-a-progress-indicator"></a>实现进度指示器

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
由客户端启动的操作的许多需要很长的时间。 这些可能冗长的操作的输入参数之一是指向进度对象的指针 — 实现的对象[IMAPIProgress: IUnknown](imapiprogressiunknown.md)接口。 进度对象控制的外观和显示进度指示器，客户端和 MAPI 实现。 您可以选择要实现进度对象。 MAPI 实现了可供服务提供商使用如果您选择不提供的实现。 
  
进度对象使用数据的以下部分：
  
- 一个全局最小值，当调用[IMAPIProgress::Progress](imapiprogress-progress.md)方法时，应小于或等于_ulValue_参数的值。 在操作的开头， _ulValue_将等于此最小值。 
    
- 一个全局最大值，当调用**IMAPIProgress::Progress**方法时，应大于或等于_ulValue_参数。 在操作末尾， _ulValue_将等于此最大值。 
    
- 标志值表示进度是否对应于顶部或项目级别较低。
    
- 一个值，指示操作的进度的当前级别。
    
- 相对于总当前处理的项目数。
    
- 在操作过程中处理的项目总数。
    
最小和最大值表示的开头和结尾数值窗体中的操作。 用于初始的最小值和初始的最大值，这些值传递给服务提供商的[IMAPIProgress::GetMin](imapiprogress-getmin.md)和[IMAPIProgress::GetMax](imapiprogress-getmax.md)方法 1000年 1。 呼叫[IMAPIProgress::SetLimits](imapiprogress-setlimits.md)时，服务提供商重置这些值。 
  
服务提供商使用的标志值来确定其应该如何设置其他值。 初始化 MAPI_TOP_LEVEL 的标志值，并返回此值中的**GetFlags**实现，直到服务提供商将其重置通过调用**SetLimits**。 
  
**SetLimits**方法的实现中, 保存的每个参数的本地副本： _lpulMin_、 _lpulMax_和_lpulFlags_。 服务提供商呼叫**GetMin**、 **GetMax**或**GetFlags**方法时，这些值应为随时可用。 
  
若要更新进度指示器显示，服务提供商，请调用**IMAPIProgress::Progress**方法。 有此方法的三个参数： 一个值，计数，并且总。 第一个参数， _ulValue_，用于显示进度指示器。 _UlValue_参数进度指示器并且将等于在一开始操作的仅全局_ulMin_和等于全局_ulMax_仅在完成该操作。 
  
使用第二个和第三个参数、 _ulCount_和_ulTotal_，如果可用，以显示可选消息，例如"5 项目完成 10。" 如果第二个和第三个参数设置为 0，则可以选择以可视方式更改进度指示器。 某些服务提供商将这些参数设置为零，以指示它们处理相对于父对象监视其进度的子对象。 在此情况下，有意义的父对象报告进度时仅显示更改。 某些服务提供商传递零为这些参数每次。 
  

