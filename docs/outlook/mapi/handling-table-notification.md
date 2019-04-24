---
title: 处理表通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: edc9bc71-4885-4783-b465-0bafa20eff73
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6e6c24c3836f295054c1880dc506c5051078a9ab
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299487"
---
# <a name="handling-table-notification"></a>处理表通知

**适用于**：Outlook 2013 | Outlook 2016 
  
作为直接注册到建议源对象 (如文件夹或邮件用户) 的替代方法, 客户端可以为内容或层次结构表注册通知。 通过内容或层次结构表跟踪对通讯簿条目、文件夹和邮件所做的更改可能比通过单个对象更简单、更直接。 

例如, 可以对文件夹的层次结构表调用[IMAPITable:: Advise](imapitable-advise.md) , 以发现它的一个子文件夹发生更改的情况。 如果您支持查看远程消息, 请向状态表注册, 以观察传输提供程序和 MAPI 后台处理程序的活动。 
  
但是, 并不总是最好使用表通知而不是对象通知。 如果您的客户端可能需要在文件夹上注册对象通知, 而不是在由该文件夹实现的表上注册对象通知, 则监视文件夹中的邮件数量的更改就是一个示例。
  

