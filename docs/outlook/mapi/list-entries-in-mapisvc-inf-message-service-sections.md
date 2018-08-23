---
title: MapiSvc.inf 邮件服务部分中的列表条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f4f052d6-ef63-421a-9d8c-4f3c6df83863
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c5b5c468b56e5b34d265e7f00bbee96142a88e1c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591119"
---
# <a name="list-entries-in-mapisvcinf-message-service-sections"></a><span data-ttu-id="66b1b-103">MapiSvc.inf 邮件服务部分中的列表条目</span><span class="sxs-lookup"><span data-stu-id="66b1b-103">List Entries in MapiSvc.inf Message Service Sections</span></span>

  
  
<span data-ttu-id="66b1b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="66b1b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="66b1b-105">有两种类型的部分列表条目： 一个列出了服务提供程序部分和一列中列出 miscellaneous 消息特定于服务的部分。</span><span class="sxs-lookup"><span data-stu-id="66b1b-105">There are two types of section list entries: one that lists service provider sections and one that lists miscellaneous message service-specific sections.</span></span> <span data-ttu-id="66b1b-106">使用以下格式的 mapisvc.inf 中出现以下两种类型的项：</span><span class="sxs-lookup"><span data-stu-id="66b1b-106">These two types of entries appear in mapisvc.inf using the following formats:</span></span>
  
```cpp
Providersprovider section1, provider section2, ...... provider sectionX
Sectionssection name1, section name2, ......section nameX

```

<span data-ttu-id="66b1b-107">**提供程序**条目中的每一节将映射到单个节提供属于邮件服务的服务提供商的配置信息。</span><span class="sxs-lookup"><span data-stu-id="66b1b-107">Each section in the **Providers** entry maps to an individual section providing configuration information for a service provider that belongs to the message service.</span></span> <span data-ttu-id="66b1b-108">每节中的**各节**项映射到包含额外的配置信息消息服务所需的内容。</span><span class="sxs-lookup"><span data-stu-id="66b1b-108">Each section in the **Sections** entry maps to a section that contains extra configuration information needed by the message service.</span></span> <span data-ttu-id="66b1b-109">消息服务实施定义多余的部分时要包括特殊不符合标准的各节中的信息。</span><span class="sxs-lookup"><span data-stu-id="66b1b-109">Message service implementers define extra sections when they want to include special information that does not fit in the standard sections.</span></span> <span data-ttu-id="66b1b-110">通常具有复杂的配置的消息服务使用的**各节**条目添加额外信息。</span><span class="sxs-lookup"><span data-stu-id="66b1b-110">Message services that have complicated configurations typically use the **Sections** entry to add extra information.</span></span> <span data-ttu-id="66b1b-111">每个邮件服务部分包含在列表中至少一个部分的**提供程序**条目并非所有消息服务部分都有一个**部分**条目。</span><span class="sxs-lookup"><span data-stu-id="66b1b-111">Every message services section has a **Providers** entry with at least one section in the list; not all message service sections have a **Sections** entry.</span></span> 
  
<span data-ttu-id="66b1b-112">消息服务节的两个示例。</span><span class="sxs-lookup"><span data-stu-id="66b1b-112">Two examples of message service sections follow.</span></span> <span data-ttu-id="66b1b-113">从早期的图中，单个服务提供商的简单消息服务默认通讯簿服务的第一节。</span><span class="sxs-lookup"><span data-stu-id="66b1b-113">The first section is for the Default Address Book service from the earlier illustration, a straightforward message service with a single service provider.</span></span> <span data-ttu-id="66b1b-114">在第二个部分，对于 MsgService 服务，更复杂的示例邮件服务三种服务提供商使用。</span><span class="sxs-lookup"><span data-stu-id="66b1b-114">The second section is for the MsgService service, a more complex sample message service with three service providers.</span></span> 
  
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

<span data-ttu-id="66b1b-115">**[MsgService]** 节中的**各节**项列出两个其他部分，一个称为 **[First_Special_Section]** 并另调用 **[Second_Special_Section]**。</span><span class="sxs-lookup"><span data-stu-id="66b1b-115">The **Sections** entry in the **[MsgService]** section lists two additional sections, one called **[First_Special_Section]** and the other called **[Second_Special_Section]**.</span></span> <span data-ttu-id="66b1b-116">可能会出现额外的各节中的数据有意义的特定邮件服务。</span><span class="sxs-lookup"><span data-stu-id="66b1b-116">The data that might appear in extra sections is meaningful to the specific message service.</span></span> <span data-ttu-id="66b1b-117">以下各节显示以下说明多余的部分。</span><span class="sxs-lookup"><span data-stu-id="66b1b-117">These sections appear following to illustrate extra sections.</span></span> 
  
```cpp
[First_Special_Section]
UID=13DB0C8AA05101A9BB000AA002FC45A
66020003=01000000
66000003=00040000
66010003=06000000
66050003=03000000

```


