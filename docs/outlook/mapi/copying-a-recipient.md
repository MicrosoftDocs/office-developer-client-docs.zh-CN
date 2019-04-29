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
  
若要将一个或多个收件人从一个容器复制到另一个容器或同一容器, 请首先检查目标容器是否可修改。 可修改的容器在其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中设置 AB_MODIFIABLE 标志。
  
若要将一个或多个条目复制到可修改的容器中, 请调用目标容器的[IABContainer:: CopyEntries](iabcontainer-copyentries.md)方法。 由于复制通讯簿条目可能非常耗时, **CopyEntries**接受四个输入参数: 一个用于要复制的条目的条目标识符数组、一个窗口句柄、一个进度指示器和一个标志的位掩码。 
  
通讯簿提供程序使用窗口句柄和进度指示器向用户显示操作的状态。 如果要显示进度, 请在_ulUIParam_参数中为进度指示器的父窗口传递窗口句柄, 不要在_ulFlags_参数中设置 AB_NO_DIALOG 标志。 如果你有自己的进度指示器实现, 请在_lpProgress_参数中传递指向实现的指针。 如果不是, 则传递 NULL。 通讯簿提供程序将使用 MAPI 进度指示器实现。 
  
flags 的位掩码指示是否要显示进度指示器以及应如何处理重复项检查。 设置 AB_NO_DIALOG 标志以禁止显示进度指示器。 设置 CREATE_CHECK_DUP_LOOSE 标志以指示通讯簿提供程序对重复项或 CREATE_CHECK_DUP_STRICT 标志进行松散检查以进行更严格的重复检查。 将 CREATE_REPLACE 标志设置为当提供程序确定存在重复项时, 已复制的条目将替换现有的条目。 
  
当复制到个人通讯簿 (PAB) 容器中时, 提供程序将复制每个条目的部分或全部属性。 由于 MAPI 不会为实现容器复制操作的提供程序建立要求, 因此无法假设与通讯簿条目一起复制的属性的数量和类型。
  

