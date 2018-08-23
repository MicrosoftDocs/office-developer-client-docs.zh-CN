---
title: 复制收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b9a41f44-4c7e-4c57-b536-63fb85e4fae6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0105ac92c53424199685e76223e6d75792fb674e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566906"
---
# <a name="copying-a-recipient"></a>复制收件人

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
若要将一个或多个收件人复制到另一个容器或相同的容器，请先检查目标容器可修改。 容器的可修改其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中设置 AB_MODIFIABLE 标志。
  
要复制到可修改容器的一个或多个条目，调用目标容器[IABContainer::CopyEntries](iabcontainer-copyentries.md)方法。 由于复制通讯簿条目可能耗时， **CopyEntries**接受四个输入参数： 要复制的条目、 窗口句柄、 进度指示器和标志的位掩码的项标识符的数组。 
  
通过通讯簿提供程序使用的窗口句柄和进度指示器用于向用户显示操作的状态。 如果您想要显示进度， _ulUIParam_参数中传递的进度指示器的父窗口的窗口句柄，并且不要_ulFlags_参数中设置 AB_NO_DIALOG 标志。 如果您有自己的进度指示器的实现，请将指针传递给_lpProgress_参数中的实现。 如果没有，传递 NULL。 通讯簿提供程序将使用 MAPI 进度指示器实现。 
  
Flags 的位掩码指示您是否想要显示进度指示器和检查应处理方式重复项。 设置 AB_NO_DIALOG 标志禁止进度指示器。 设置 CREATE_CHECK_DUP_LOOSE 标志以指示通讯簿提供程序松散检查重复项或更严格的重复检查 CREATE_CHECK_DUP_STRICT 标记。 提供程序确定有重复项时，设置要复制条目的 CREATE_REPLACE 标志会替换现有条目。 
  
在复制到个人通讯簿 (PAB) 的容器，提供程序复制部分或全部为每个项的属性。 MAPI 无法建立实现容器复制操作的提供程序的要求，因为您无法进行假设数量和类型使用的通讯簿条目复制的属性。
  

