---
title: 支持只读邮件存储区中的表单和视图
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: da5f080d-4397-4ce6-8561-73dd13445e77
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 0b7ffe07278cfcbba95351f2720e427dd8500221
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432427"
---
# <a name="supporting-forms-and-views-in-read-only-message-stores"></a><span data-ttu-id="75bd4-103">支持只读邮件存储区中的表单和视图</span><span class="sxs-lookup"><span data-stu-id="75bd4-103">Supporting Forms and Views in Read-Only Message Stores</span></span>

  
  
<span data-ttu-id="75bd4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="75bd4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="75bd4-105">如果您的邮件存储区提供程序允许对基础存储机制进行只读权限, 客户端应用程序和 MAPI 表单管理器将无法执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="75bd4-105">If your message store provider allows read-only permission to the underlying storage mechanism, client applications and the MAPI form manager will be unable to do certain things.</span></span> <span data-ttu-id="75bd4-106">具体来说, 客户端将无法添加或修改自定义视图, MAPI 表单管理器将无法在存储文件夹的关联内容表中安装表单。</span><span class="sxs-lookup"><span data-stu-id="75bd4-106">Specifically, clients will be unable to add or modify custom views, and the MAPI form manager will be unable to install forms in the associated contents tables of the store's folders.</span></span>
  
<span data-ttu-id="75bd4-107">对于很多只读邮件存储区, 这可能不是问题。</span><span class="sxs-lookup"><span data-stu-id="75bd4-107">For many read-only message stores, that may not be a problem.</span></span> <span data-ttu-id="75bd4-108">如果是这种情况, 则邮件存储提供程序根本不需要支持关联的内容表。</span><span class="sxs-lookup"><span data-stu-id="75bd4-108">If that is the case, the message store provider does not need to support associated contents tables at all.</span></span> <span data-ttu-id="75bd4-109">但是, 如果您的邮件存储提供程序必须是只读的, 并且它还必须支持一组预定义的视图或表单, 则需要支持关联的内容表。</span><span class="sxs-lookup"><span data-stu-id="75bd4-109">However, if your message store provider must be read-only and it must also support a predefined set of views or forms, it will need to support associated contents tables.</span></span>
  
<span data-ttu-id="75bd4-110">执行此操作的最常见策略是, 因为客户端和 MAPI 表单管理器无法将视图或表单安装到邮件存储区本身, 所以邮件存储提供程序将这些视图或表单硬编码到邮件存储中。</span><span class="sxs-lookup"><span data-stu-id="75bd4-110">The most common strategy for doing this, because clients and the MAPI form manager cannot install the views or forms into the message store themselves, is for the message store provider to hard-code them into the message store.</span></span> <span data-ttu-id="75bd4-111">这意味着, 在创建邮件存储区时, 包含这些视图或表单的相关内容表将存在于邮件存储区中, 在任何客户端或 MAPI 表单管理器访问它之前。</span><span class="sxs-lookup"><span data-stu-id="75bd4-111">This means that the associated contents table or tables that contain the views or forms will exist in the message store when it is created, before any clients or the MAPI form manager ever access it.</span></span> <span data-ttu-id="75bd4-112">然后, 当客户端请求关联的内容表从表单中获取自定义视图或 MAPI 表单管理器请求关联的内容表来启动表单时, 邮件存储提供程序可以提供一个。</span><span class="sxs-lookup"><span data-stu-id="75bd4-112">Then, when a client requests an associated contents table to get custom views from a form or the MAPI form manager requests an associated contents table to launch a form, the message store provider can provide one.</span></span> 
  
<span data-ttu-id="75bd4-113">这要求在创建邮件存储区本身时创建并填充关联的内容表, 这意味着您的邮件存储提供程序将需要获取有关客户端和 MAPI 表单的特殊邮件格式的信息。管理器用于存储视图和表单。</span><span class="sxs-lookup"><span data-stu-id="75bd4-113">This requirement that the associated contents tables be created and populated when the message store itself is created implies that your message store provider will need to obtain information about the format of the special messages that clients and the MAPI form manager use to store views and forms.</span></span> <span data-ttu-id="75bd4-114">这些格式将取决于所使用的客户端和 MAPI 表单管理器, 因此无法在此处提供它们的说明。</span><span class="sxs-lookup"><span data-stu-id="75bd4-114">What those formats are will depend on the client and MAPI form manager being used, so a description of them cannot be provided here.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="75bd4-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75bd4-115">See also</span></span>



[<span data-ttu-id="75bd4-116">只读邮件存储</span><span class="sxs-lookup"><span data-stu-id="75bd4-116">Read-Only Message Stores</span></span>](read-only-message-stores.md)

