---
title: mapisvc.inf [默认服务] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: dec42f8d-0f5c-4665-b53a-11cbc58b8b76
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a7906a9a5e953332dba5c4776c63bb433a937a5d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435318"
---
# <a name="mapisvcinf-default-services-section"></a>mapisvc.inf [默认服务] 部分

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**[默认服务]** 部分列出了选定为默认邮件服务的所有邮件服务。 这些默认邮件服务是 **[服务]** 一节中列出的邮件服务的子集。 当配置文件配置程序创建默认配置文件时, 将自动包含此部分中的邮件服务。 
  
这些条目使用与 **[服务]** 部分中的条目相同的格式, 如下所示: 
  
 **[默认服务]**
  
 _message service 部分名称_ =  _邮件服务名称_
  
在前面的图所示的 mapisvc.inf 的 **[默认服务]** 部分中, 将包含以下项: 
  
```cpp
[Default Services]
AB=Default Address Book
MsgService=My Own Service

```


