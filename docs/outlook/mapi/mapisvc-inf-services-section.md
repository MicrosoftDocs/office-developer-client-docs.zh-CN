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
# <a name="mapisvcinf-services-section"></a><span data-ttu-id="77687-103">MapiSvc.inf [服务] 部分</span><span class="sxs-lookup"><span data-stu-id="77687-103">MapiSvc.inf [Services] Section</span></span>

  
  
<span data-ttu-id="77687-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="77687-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="77687-105">**[服务]** 部分列出的计算机安装的消息服务。</span><span class="sxs-lookup"><span data-stu-id="77687-105">The **[Services]** section lists the message services that are installed on a computer.</span></span> <span data-ttu-id="77687-106">本节中的项使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="77687-106">Entries in this section use the following format:</span></span> 
  
 <span data-ttu-id="77687-107">**[服务]**</span><span class="sxs-lookup"><span data-stu-id="77687-107">**[Services]**</span></span>
  
 <span data-ttu-id="77687-108">_消息服务的部分名称_ =  _消息服务名称_</span><span class="sxs-lookup"><span data-stu-id="77687-108">_message-service section name_ =  _message service name_</span></span>
  
<span data-ttu-id="77687-109">消息服务节名称是一个字符串由定义邮件服务链接此条目到其他位置中 mapisvc.inf service 的相应部分。</span><span class="sxs-lookup"><span data-stu-id="77687-109">The message-service section name is a string defined by the message service that links this entry to a corresponding section for the service elsewhere in mapisvc.inf.</span></span> <span data-ttu-id="77687-110">消息服务名称是服务的已安装的名称。</span><span class="sxs-lookup"><span data-stu-id="77687-110">The message service name is the name of the installed service.</span></span> <span data-ttu-id="77687-111">以下部分显示三个消息服务： 在默认通讯簿、 我自己服务和邮件存储服务。</span><span class="sxs-lookup"><span data-stu-id="77687-111">The following section shows three message services: the Default Address Book, My Own Service, and the Message Store Service.</span></span> <span data-ttu-id="77687-112">这些服务是虚构的仅用于图。</span><span class="sxs-lookup"><span data-stu-id="77687-112">These services are fictional, for illustration purposes only.</span></span> <span data-ttu-id="77687-113">每个邮件服务实施将它替换他/她消息服务，在此部分的相应项。</span><span class="sxs-lookup"><span data-stu-id="77687-113">Each message service implementer would substitute the appropriate entry for his or her message service in this section.</span></span>
  
```cpp
[Services]
AB=Default Address Book
MsgService=My Own Service
MS=Message Store Service

```

<span data-ttu-id="77687-114">本节中的每个项具有相应节，其自己的消息服务的信息的存储位置。</span><span class="sxs-lookup"><span data-stu-id="77687-114">Each entry in this section has a corresponding section of its own where information for the message service is stored.</span></span> <span data-ttu-id="77687-115">例如，在默认通讯簿的相应部分调用 [AB]。</span><span class="sxs-lookup"><span data-stu-id="77687-115">For example, the corresponding section for the Default Address Book is called [AB].</span></span>
  

