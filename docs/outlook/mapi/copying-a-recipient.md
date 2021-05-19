---
title: 复制收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b9a41f44-4c7e-4c57-b536-63fb85e4fae6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3a4fb1a3f76481bf1960c251a33911b871a8791c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419084"
---
# <a name="copying-a-recipient"></a>复制收件人

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要将一个或多个收件人从一个容器复制到另一个或同一个容器，请首先检查目标容器是否可修改。 可修改的容器AB_MODIFIABLE [PidTagContainerFlags](pidtagcontainerflags-canonical-property.md) PR_CONTAINER_FLAGS (设置) 标志。 
  
若要将一个或多个条目复制到可修改的容器中，请调用目标容器的 [IABContainer：：CopyEntries](iabcontainer-copyentries.md) 方法。 由于复制通讯簿条目可能很耗时， **因此 CopyEntries** 接受四个输入参数：要复制的条目的条目标识符数组、窗口句柄、进度指示器和标志位掩码。 
  
通讯簿提供程序使用窗口句柄和进度指示器向用户显示操作的状态。 如果要显示进度，请传递  _ulUIParam_ 参数中进度指示器的父窗口的窗口句柄，并且不要设置  _ulFlags_ 参数中的 AB_NO_DIALOG 标志。 如果您有自己实现进度指示器，请传递指向  _lpProgress_ 参数中的实现指针。 如果没有，则传递 NULL。 通讯簿提供程序将使用 MAPI 进度指示器实现。 
  
标志的位掩码指示是否要显示进度指示器以及如何处理重复条目检查。 设置AB_NO_DIALOG标记以禁止显示进度指示器。 设置 CREATE_CHECK_DUP_LOOSE 标志以指示通讯簿提供程序松散检查重复项，或设置 CREATE_CHECK_DUP_STRICT 标志进行更严格的重复检查。 设置CREATE_REPLACE标记，使复制的条目替换提供程序确定存在重复项时的现有条目。 
  
当复制到 PAB (个人通讯簿) ，提供程序会复制每个条目的一些或所有属性。 由于 MAPI 没有为实施容器副本操作提供程序建立要求，因此不能对使用通讯簿条目复制的属性的数量和类型做出假设。
  

