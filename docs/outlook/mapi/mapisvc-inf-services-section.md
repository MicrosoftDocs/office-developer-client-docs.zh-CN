---
title: MapiSvc.inf [服务] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 99f8e623-3138-4def-9778-5580326111a5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 19031f6c02f3e8e925adfc8d2affa43fb6532fee
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776400"
---
# <a name="mapisvcinf-services-section"></a>MapiSvc.inf [服务] 部分

  
  
**适用于**： Outlook 
  
**[服务]** 部分列出的计算机安装的消息服务。 本节中的项使用以下格式： 
  
 **[服务]**
  
 _消息服务的部分名称_ =  _消息服务名称_
  
消息服务节名称是一个字符串由定义邮件服务链接此条目到其他位置中 mapisvc.inf service 的相应部分。 消息服务名称是服务的已安装的名称。 以下部分显示三个消息服务： 在默认通讯簿、 我自己服务和邮件存储服务。 这些服务是虚构的仅用于图。 每个邮件服务实施将它替换他/她消息服务，在此部分的相应项。
  
```cpp
[Services]
AB=Default Address Book
MsgService=My Own Service
MS=Message Store Service

```

本节中的每个项具有相应节，其自己的消息服务的信息的存储位置。 例如，在默认通讯簿的相应部分调用 [AB]。
  

