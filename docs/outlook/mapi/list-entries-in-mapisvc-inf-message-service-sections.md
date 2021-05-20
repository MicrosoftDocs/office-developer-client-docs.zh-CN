---
title: MapiSvc.inf 邮件服务节中的列表条目
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
# <a name="list-entries-in-mapisvcinf-message-service-sections"></a>MapiSvc.inf 邮件服务节中的列表条目

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
有两种类型的节列表条目：一种是列出服务提供程序部分，另一种是列出其他邮件服务特定节。 这两种类型的条目以以下格式显示在 mapisvc.inf 中：
  
```cpp
Providersprovider section1, provider section2, ...... provider sectionX
Sectionssection name1, section name2, ......section nameX

```

"提供程序"条目 **的每个** 部分都映射到单个部分，该节提供属于邮件服务的服务提供商的配置信息。 "分区"条目 **的每个** 部分映射到包含邮件服务所需的额外配置信息的节。 当邮件服务实施者要包含标准节中不适合的特殊信息时，会定义额外的节。 具有复杂配置的邮件服务通常使用 **"分区** "条目添加额外信息。 每个邮件服务部分都有一 **个提供程序** 条目，列表中至少有一个部分;并非所有邮件服务部分都有" **节"** 条目。 
  
以下是邮件服务分区的两个示例。 第一部分适用于上图中的默认通讯簿服务，即具有单个服务提供程序的简单邮件服务。 第二部分针对 MsgService 服务，这是一个包含三个服务提供程序的更复杂的示例邮件服务。 
  
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

**[MsgService]** 部分中的 **Sections** 条目列出了两个其他部分，一个称为 **[First_Special_Section]** ，另一个称为 **[Second_Special_Section]**。 可能显示在额外节中的数据对特定邮件服务有意义。 以下各节演示了额外的部分。 
  
```cpp
[First_Special_Section]
UID=13DB0C8AA05101A9BB000AA002FC45A
66020003=01000000
66000003=00040000
66010003=06000000
66050003=03000000

```


