---
title: mapisvc.inf [服务] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 99f8e623-3138-4def-9778-5580326111a5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e5bf5242ef673976ebda928d6ce4862e3e7dd072
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270019"
---
# <a name="mapisvcinf-services-section"></a>mapisvc.inf [服务] 部分

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**[服务]** 部分列出了计算机上安装的邮件服务。 此部分中的条目使用以下格式: 
  
 **服务行业**
  
 _message service 部分名称_ =  _邮件服务名称_
  
message service 节名称是由邮件服务定义的一个字符串, 可将此条目链接到 mapisvc.inf 中其他位置的服务的相应部分。 邮件服务名称是已安装服务的名称。 下面的部分显示了三种邮件服务: 默认通讯簿、我自己的服务和邮件存储服务。 这些服务是虚构的, 仅用于说明目的。 每个邮件服务实施者将在此部分中替换其邮件服务的相应条目。
  
```cpp
[Services]
AB=Default Address Book
MsgService=My Own Service
MS=Message Store Service

```

本节中的每个条目都有自己的相应部分, 其中存储了邮件服务的信息。 例如, 默认通讯簿对应的部分称为 [AB]。
  

