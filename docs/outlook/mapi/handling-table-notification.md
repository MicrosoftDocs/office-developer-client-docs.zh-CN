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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435892"
---
# <a name="handling-table-notification"></a>处理表通知

**适用于**：Outlook 2013 | Outlook 2016 
  
作为直接使用建议源对象（如文件夹或邮件用户）注册的替代方法，客户端可以注册内容或层次结构表上的通知。 通过内容或层次结构表跟踪通讯簿条目、文件夹和邮件的更改比通过单个对象更为简单和简单。 

例如，你可以对文件夹的层次结构表调用 [IMAPITable：：Advise，](imapitable-advise.md) 以发现何时更改其子文件夹之一。 如果支持查看远程邮件，请在状态表中注册以观察传输提供程序和 MAPI 后台处理程序的活动。 
  
但是，使用表通知而不是对象通知并不总是更可取。 监视文件夹中邮件数量的变化是客户端何时可能需要在文件夹上（而不是文件夹实现的表）上注册对象通知的示例。
  

