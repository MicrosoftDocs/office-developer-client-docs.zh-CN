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
# <a name="mapisvcinf-services-section"></a><span data-ttu-id="9904d-103">MapiSvc.inf [Services] Section</span><span class="sxs-lookup"><span data-stu-id="9904d-103">MapiSvc.inf [Services] Section</span></span>

  
  
<span data-ttu-id="9904d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9904d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9904d-105">**[服务]** 部分列出了计算机上安装的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="9904d-105">The **[Services]** section lists the message services that are installed on a computer.</span></span> <span data-ttu-id="9904d-106">本节中的条目使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="9904d-106">Entries in this section use the following format:</span></span> 
  
 <span data-ttu-id="9904d-107">**[服务]**</span><span class="sxs-lookup"><span data-stu-id="9904d-107">**[Services]**</span></span>
  
 <span data-ttu-id="9904d-108">_message-service 节名称_  =  _邮件服务名称_</span><span class="sxs-lookup"><span data-stu-id="9904d-108">_message-service section name_ =  _message service name_</span></span>
  
<span data-ttu-id="9904d-109">message-service 节名称是由邮件服务定义的字符串，用于将此项链接到 mapisvc.inf 中其他位置的服务的相应部分。</span><span class="sxs-lookup"><span data-stu-id="9904d-109">The message-service section name is a string defined by the message service that links this entry to a corresponding section for the service elsewhere in mapisvc.inf.</span></span> <span data-ttu-id="9904d-110">邮件服务名称是已安装服务的名称。</span><span class="sxs-lookup"><span data-stu-id="9904d-110">The message service name is the name of the installed service.</span></span> <span data-ttu-id="9904d-111">以下部分显示了三种邮件服务：默认通讯簿、My Own Service 和邮件存储服务。</span><span class="sxs-lookup"><span data-stu-id="9904d-111">The following section shows three message services: the Default Address Book, My Own Service, and the Message Store Service.</span></span> <span data-ttu-id="9904d-112">这些服务是虚构的，仅用于说明目的。</span><span class="sxs-lookup"><span data-stu-id="9904d-112">These services are fictional, for illustration purposes only.</span></span> <span data-ttu-id="9904d-113">每个邮件服务实施者将替换本节中其邮件服务的适当条目。</span><span class="sxs-lookup"><span data-stu-id="9904d-113">Each message service implementer would substitute the appropriate entry for his or her message service in this section.</span></span>
  
```cpp
[Services]
AB=Default Address Book
MsgService=My Own Service
MS=Message Store Service

```

<span data-ttu-id="9904d-114">本节中的每个条目都有其自己的相应节，其中存储了邮件服务的信息。</span><span class="sxs-lookup"><span data-stu-id="9904d-114">Each entry in this section has a corresponding section of its own where information for the message service is stored.</span></span> <span data-ttu-id="9904d-115">例如，默认通讯簿的相应部分称为 [AB]。</span><span class="sxs-lookup"><span data-stu-id="9904d-115">For example, the corresponding section for the Default Address Book is called [AB].</span></span>
  

