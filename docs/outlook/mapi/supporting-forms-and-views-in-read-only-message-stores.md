---
title: 支持只读邮件存储区中的表单和视图
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: da5f080d-4397-4ce6-8561-73dd13445e77
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 52aebb53f2bc0e5af72f2da47b91ba2806d7f709
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563350"
---
# <a name="supporting-forms-and-views-in-read-only-message-stores"></a><span data-ttu-id="53941-103">支持只读邮件存储区中的表单和视图</span><span class="sxs-lookup"><span data-stu-id="53941-103">Supporting Forms and Views in Read-Only Message Stores</span></span>

  
  
<span data-ttu-id="53941-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="53941-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="53941-105">如果您的消息存储提供程序允许对基础存储机制的只读权限，客户端应用程序和 MAPI 窗体管理器将无法执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="53941-105">If your message store provider allows read-only permission to the underlying storage mechanism, client applications and the MAPI form manager will be unable to do certain things.</span></span> <span data-ttu-id="53941-106">具体而言，将无法添加或修改自定义视图，客户端和 MAPI 窗体管理器将不能安装关联的内容存储的文件夹的表中的表单。</span><span class="sxs-lookup"><span data-stu-id="53941-106">Specifically, clients will be unable to add or modify custom views, and the MAPI form manager will be unable to install forms in the associated contents tables of the store's folders.</span></span>
  
<span data-ttu-id="53941-107">对于许多只读消息存储，可能不出现问题。</span><span class="sxs-lookup"><span data-stu-id="53941-107">For many read-only message stores, that may not be a problem.</span></span> <span data-ttu-id="53941-108">如果是这样，则不需要在所有支持关联的内容表的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="53941-108">If that is the case, the message store provider does not need to support associated contents tables at all.</span></span> <span data-ttu-id="53941-109">但是，如果您的消息存储提供程序必须是只读的并且它还必须支持一组预定义的视图或表单，它将需要支持关联的内容的表格。</span><span class="sxs-lookup"><span data-stu-id="53941-109">However, if your message store provider must be read-only and it must also support a predefined set of views or forms, it will need to support associated contents tables.</span></span>
  
<span data-ttu-id="53941-110">这样，客户端和 MAPI 窗体管理器无法安装视图或窗体插入邮件存储，因为的最常见策略是硬编码的消息存储提供程序它们到邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="53941-110">The most common strategy for doing this, because clients and the MAPI form manager cannot install the views or forms into the message store themselves, is for the message store provider to hard-code them into the message store.</span></span> <span data-ttu-id="53941-111">这意味着或多个关联的内容包含视图或窗体的表将存在于消息存储库创建时，任何客户端或 MAPI 之前窗体管理器以往访问它。</span><span class="sxs-lookup"><span data-stu-id="53941-111">This means that the associated contents table or tables that contain the views or forms will exist in the message store when it is created, before any clients or the MAPI form manager ever access it.</span></span> <span data-ttu-id="53941-112">然后，在客户端请求从窗体中获取自定义视图关联的内容表或 MAPI 窗体管理器请求相关联的内容表格，以启动窗体时，消息存储提供程序可以提供一个。</span><span class="sxs-lookup"><span data-stu-id="53941-112">Then, when a client requests an associated contents table to get custom views from a form or the MAPI form manager requests an associated contents table to launch a form, the message store provider can provide one.</span></span> 
  
<span data-ttu-id="53941-113">关联的内容表的创建和填充时创建邮件存储本身此要求意味着您的消息存储提供程序需要该客户端和 MAPI 窗体获得的特殊的消息的格式信息用于存储视图和窗体管理器。</span><span class="sxs-lookup"><span data-stu-id="53941-113">This requirement that the associated contents tables be created and populated when the message store itself is created implies that your message store provider will need to obtain information about the format of the special messages that clients and the MAPI form manager use to store views and forms.</span></span> <span data-ttu-id="53941-114">什么是这些格式将取决于客户端和 MAPI 窗体管理器被使用，以便无法此处提供的说明。</span><span class="sxs-lookup"><span data-stu-id="53941-114">What those formats are will depend on the client and MAPI form manager being used, so a description of them cannot be provided here.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="53941-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53941-115">See also</span></span>



[<span data-ttu-id="53941-116">只读邮件存储区</span><span class="sxs-lookup"><span data-stu-id="53941-116">Read-Only Message Stores</span></span>](read-only-message-stores.md)

