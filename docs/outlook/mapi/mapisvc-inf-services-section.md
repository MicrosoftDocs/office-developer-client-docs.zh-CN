---
title: MapiSvc.inf [Services] Section
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 99f8e623-3138-4def-9778-5580326111a5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e5bf5242ef673976ebda928d6ce4862e3e7dd072
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434779"
---
# <a name="mapisvcinf-services-section"></a>MapiSvc.inf [Services] Section

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**[服务]** 部分列出了计算机上安装的邮件服务。 本节中的条目使用以下格式： 
  
 **[服务]**
  
 _message-service 节名称_  =  _邮件服务名称_
  
message-service 节名称是由邮件服务定义的字符串，用于将此项链接到 mapisvc.inf 中其他位置的服务的相应部分。 邮件服务名称是已安装服务的名称。 以下部分显示了三种邮件服务：默认通讯簿、My Own Service 和邮件存储服务。 这些服务是虚构的，仅用于说明目的。 每个邮件服务实施者将替换本节中其邮件服务的适当条目。
  
```cpp
[Services]
AB=Default Address Book
MsgService=My Own Service
MS=Message Store Service

```

本节中的每个条目都有其自己的相应节，其中存储了邮件服务的信息。 例如，默认通讯簿的相应部分称为 [AB]。
  

