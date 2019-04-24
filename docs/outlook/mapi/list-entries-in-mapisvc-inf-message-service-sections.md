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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307831"
---
# <a name="list-entries-in-mapisvcinf-message-service-sections"></a><span data-ttu-id="0c0da-103">mapisvc.inf 邮件服务部分中的列表条目</span><span class="sxs-lookup"><span data-stu-id="0c0da-103">List Entries in MapiSvc.inf Message Service Sections</span></span>

  
  
<span data-ttu-id="0c0da-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0c0da-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0c0da-105">有两种类型的节列表条目: 一个列出了服务提供程序部分, 另一个列出了其他特定于邮件服务的节。</span><span class="sxs-lookup"><span data-stu-id="0c0da-105">There are two types of section list entries: one that lists service provider sections and one that lists miscellaneous message service-specific sections.</span></span> <span data-ttu-id="0c0da-106">这两种类型的条目显示在 mapisvc.inf 中, 使用以下格式:</span><span class="sxs-lookup"><span data-stu-id="0c0da-106">These two types of entries appear in mapisvc.inf using the following formats:</span></span>
  
```cpp
Providersprovider section1, provider section2, ...... provider sectionX
Sectionssection name1, section name2, ......section nameX

```

<span data-ttu-id="0c0da-107">**提供程序**条目中的每个部分都映射到单个部分, 为属于邮件服务的服务提供程序提供配置信息。</span><span class="sxs-lookup"><span data-stu-id="0c0da-107">Each section in the **Providers** entry maps to an individual section providing configuration information for a service provider that belongs to the message service.</span></span> <span data-ttu-id="0c0da-108">**各**部分条目中的每个部分都映射到包含邮件服务所需的额外配置信息的部分。</span><span class="sxs-lookup"><span data-stu-id="0c0da-108">Each section in the **Sections** entry maps to a section that contains extra configuration information needed by the message service.</span></span> <span data-ttu-id="0c0da-109">邮件服务实现者在希望包含不能容纳在标准节中的特殊信息时, 可以定义额外的部分。</span><span class="sxs-lookup"><span data-stu-id="0c0da-109">Message service implementers define extra sections when they want to include special information that does not fit in the standard sections.</span></span> <span data-ttu-id="0c0da-110">具有复杂配置的邮件服务通常使用**节**条目添加额外信息。</span><span class="sxs-lookup"><span data-stu-id="0c0da-110">Message services that have complicated configurations typically use the **Sections** entry to add extra information.</span></span> <span data-ttu-id="0c0da-111">每个邮件服务部分都有一个**提供程序**条目, 列表中至少有一个部分;并不是所有的邮件服务部分都有**节**条目。</span><span class="sxs-lookup"><span data-stu-id="0c0da-111">Every message services section has a **Providers** entry with at least one section in the list; not all message service sections have a **Sections** entry.</span></span> 
  
<span data-ttu-id="0c0da-112">以下是邮件服务节的两个示例。</span><span class="sxs-lookup"><span data-stu-id="0c0da-112">Two examples of message service sections follow.</span></span> <span data-ttu-id="0c0da-113">第一部分是前面的图示中的默认通讯簿服务, 具有单个服务提供商的简单邮件服务。</span><span class="sxs-lookup"><span data-stu-id="0c0da-113">The first section is for the Default Address Book service from the earlier illustration, a straightforward message service with a single service provider.</span></span> <span data-ttu-id="0c0da-114">第二部分是针对 MsgService 服务的, 它是一个包含三个服务提供商的更复杂的示例邮件服务。</span><span class="sxs-lookup"><span data-stu-id="0c0da-114">The second section is for the MsgService service, a more complex sample message service with three service providers.</span></span> 
  
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

<span data-ttu-id="0c0da-115">**[MsgService]** 一节中的**section**条目列出了两个附加部分, 称为 **[First_Special_Section]** , 另一个称为 **[Second_Special_Section]**。</span><span class="sxs-lookup"><span data-stu-id="0c0da-115">The **Sections** entry in the **[MsgService]** section lists two additional sections, one called **[First_Special_Section]** and the other called **[Second_Special_Section]**.</span></span> <span data-ttu-id="0c0da-116">可能出现在额外节中的数据对特定的邮件服务有意义。</span><span class="sxs-lookup"><span data-stu-id="0c0da-116">The data that might appear in extra sections is meaningful to the specific message service.</span></span> <span data-ttu-id="0c0da-117">以下各节将显示出来, 以阐释额外的部分。</span><span class="sxs-lookup"><span data-stu-id="0c0da-117">These sections appear following to illustrate extra sections.</span></span> 
  
```cpp
[First_Special_Section]
UID=13DB0C8AA05101A9BB000AA002FC45A
66020003=01000000
66000003=00040000
66010003=06000000
66050003=03000000

```


