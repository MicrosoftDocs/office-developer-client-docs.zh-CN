---
title: mapisvc.inf 邮件服务部分中的列表条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f4f052d6-ef63-421a-9d8c-4f3c6df83863
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b6b641a288cea8bac5a1990e85520f3583c02f22
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435927"
---
# <a name="list-entries-in-mapisvcinf-message-service-sections"></a>mapisvc.inf 邮件服务部分中的列表条目

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
有两种类型的节列表条目: 一个列出了服务提供程序部分, 另一个列出了其他特定于邮件服务的节。 这两种类型的条目显示在 mapisvc.inf 中, 使用以下格式:
  
```cpp
Providersprovider section1, provider section2, ...... provider sectionX
Sectionssection name1, section name2, ......section nameX

```

**提供程序**条目中的每个部分都映射到单个部分, 为属于邮件服务的服务提供程序提供配置信息。 **各**部分条目中的每个部分都映射到包含邮件服务所需的额外配置信息的部分。 邮件服务实现者在希望包含不能容纳在标准节中的特殊信息时, 可以定义额外的部分。 具有复杂配置的邮件服务通常使用**节**条目添加额外信息。 每个邮件服务部分都有一个**提供程序**条目, 列表中至少有一个部分;并不是所有的邮件服务部分都有**节**条目。 
  
以下是邮件服务节的两个示例。 第一部分是前面的图示中的默认通讯簿服务, 具有单个服务提供商的简单邮件服务。 第二部分是针对 MsgService 服务的, 它是一个包含三个服务提供商的更复杂的示例邮件服务。 
  
```cpp
[AB]
PR_DISPLAY_NAME=Default Address Book
Providers=AB Provider
PR_SERVICE_DLL_NAME=AB.DLL
PR_SERVICE_SUPPORT_FILES=AB.DLL
PR_SERVICE_ENTRY_NAME=DABServiceEntry
PR_RESOURCE_FLAGS=SERVICE_NO_PRIMARY_IDENTITY
[MsgService]
PR_DISPLAY_NAME=My Own Service
Providers=MsgService Prov1, MsgService Prov2, MsgService Prov3
Sections=First_Special_Section, Second_Special_Section
PR_SERVICE_DLL_NAME=MYSERV.DLL
PR_SERVICE_SUPPORT_FILES=MYSERV.DLL, MYXXX.DLL, MYZZZ.DLL
PR_SERVICE_ENTRY_NAME=MyServiceEntry
PR_RESOURCE_FLAGS=SERVICE_SINGLE_COPY
66040003=00000000

```

**[MsgService]** 一节中的**section**条目列出了两个附加部分, 称为 **[First_Special_Section]** , 另一个称为 **[Second_Special_Section]**。 可能出现在额外节中的数据对特定的邮件服务有意义。 以下各节将显示出来, 以阐释额外的部分。 
  
```cpp
[First_Special_Section]
UID=13DB0C8AA05101A9BB000AA002FC45A
66020003=01000000
66000003=00040000
66010003=06000000
66050003=03000000

```


