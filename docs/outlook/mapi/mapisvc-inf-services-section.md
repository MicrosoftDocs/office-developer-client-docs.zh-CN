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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434779"
---
# <a name="mapisvcinf-services-section"></a><span data-ttu-id="4c7a8-103">mapisvc.inf [服务] 部分</span><span class="sxs-lookup"><span data-stu-id="4c7a8-103">MapiSvc.inf [Services] Section</span></span>

  
  
<span data-ttu-id="4c7a8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4c7a8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4c7a8-105">**[服务]** 部分列出了计算机上安装的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="4c7a8-105">The **[Services]** section lists the message services that are installed on a computer.</span></span> <span data-ttu-id="4c7a8-106">此部分中的条目使用以下格式:</span><span class="sxs-lookup"><span data-stu-id="4c7a8-106">Entries in this section use the following format:</span></span> 
  
 <span data-ttu-id="4c7a8-107">**服务行业**</span><span class="sxs-lookup"><span data-stu-id="4c7a8-107">**[Services]**</span></span>
  
 <span data-ttu-id="4c7a8-108">_message service 部分名称_ =  _邮件服务名称_</span><span class="sxs-lookup"><span data-stu-id="4c7a8-108">_message-service section name_ =  _message service name_</span></span>
  
<span data-ttu-id="4c7a8-109">message service 节名称是由邮件服务定义的一个字符串, 可将此条目链接到 mapisvc.inf 中其他位置的服务的相应部分。</span><span class="sxs-lookup"><span data-stu-id="4c7a8-109">The message-service section name is a string defined by the message service that links this entry to a corresponding section for the service elsewhere in mapisvc.inf.</span></span> <span data-ttu-id="4c7a8-110">邮件服务名称是已安装服务的名称。</span><span class="sxs-lookup"><span data-stu-id="4c7a8-110">The message service name is the name of the installed service.</span></span> <span data-ttu-id="4c7a8-111">下面的部分显示了三种邮件服务: 默认通讯簿、我自己的服务和邮件存储服务。</span><span class="sxs-lookup"><span data-stu-id="4c7a8-111">The following section shows three message services: the Default Address Book, My Own Service, and the Message Store Service.</span></span> <span data-ttu-id="4c7a8-112">这些服务是虚构的, 仅用于说明目的。</span><span class="sxs-lookup"><span data-stu-id="4c7a8-112">These services are fictional, for illustration purposes only.</span></span> <span data-ttu-id="4c7a8-113">每个邮件服务实施者将在此部分中替换其邮件服务的相应条目。</span><span class="sxs-lookup"><span data-stu-id="4c7a8-113">Each message service implementer would substitute the appropriate entry for his or her message service in this section.</span></span>
  
```cpp
[Services]
AB=Default Address Book
MsgService=My Own Service
MS=Message Store Service

```

<span data-ttu-id="4c7a8-114">本节中的每个条目都有自己的相应部分, 其中存储了邮件服务的信息。</span><span class="sxs-lookup"><span data-stu-id="4c7a8-114">Each entry in this section has a corresponding section of its own where information for the message service is stored.</span></span> <span data-ttu-id="4c7a8-115">例如, 默认通讯簿对应的部分称为 [AB]。</span><span class="sxs-lookup"><span data-stu-id="4c7a8-115">For example, the corresponding section for the Default Address Book is called [AB].</span></span>
  

