---
title: MapiSvc.inf 消息服务各节中的列表项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f4f052d6-ef63-421a-9d8c-4f3c6df83863
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cfb06e8dd305add6049d035c44685be047dc744f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776140"
---
# <a name="list-entries-in-mapisvcinf-message-service-sections"></a>MapiSvc.inf 消息服务各节中的列表项

  
  
**适用于**： Outlook 
  
有两种类型的部分列表条目： 一个列出了服务提供程序部分和一列中列出 miscellaneous 消息特定于服务的部分。 使用以下格式的 mapisvc.inf 中出现以下两种类型的项：
  
```cpp
Providersprovider section1, provider section2, ...... provider sectionX
Sectionssection name1, section name2, ......section nameX

```

**提供程序**条目中的每一节将映射到单个节提供属于邮件服务的服务提供商的配置信息。 每节中的**各节**项映射到包含额外的配置信息消息服务所需的内容。 消息服务实施定义多余的部分时要包括特殊不符合标准的各节中的信息。 通常具有复杂的配置的消息服务使用的**各节**条目添加额外信息。 每个邮件服务部分包含在列表中至少一个部分的**提供程序**条目并非所有消息服务部分都有一个**部分**条目。 
  
消息服务节的两个示例。 从早期的图中，单个服务提供商的简单消息服务默认通讯簿服务的第一节。 在第二个部分，对于 MsgService 服务，更复杂的示例邮件服务三种服务提供商使用。 
  
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

**[MsgService]** 节中的**各节**项列出两个其他部分，一个称为 **[First_Special_Section]** 并另调用 **[Second_Special_Section]**。 可能会出现额外的各节中的数据有意义的特定邮件服务。 以下各节显示以下说明多余的部分。 
  
```cpp
[First_Special_Section]
UID=13DB0C8AA05101A9BB000AA002FC45A
66020003=01000000
66000003=00040000
66010003=06000000
66050003=03000000

```


