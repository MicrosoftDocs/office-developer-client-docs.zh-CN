---
title: 文件夹表单库
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 62b7480e-b3eb-45fb-b74d-62f1dc918a53
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f95aa26d6104da657c6ae6ab0c449d45c073223a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580549"
---
# <a name="folder-form-libraries"></a><span data-ttu-id="a5bda-103">文件夹表单库</span><span class="sxs-lookup"><span data-stu-id="a5bda-103">Folder Form Libraries</span></span>

  
  
<span data-ttu-id="a5bda-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a5bda-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a5bda-105">在某些情况下，您可能想要将一个或多个窗体与特定文件夹相关联。</span><span class="sxs-lookup"><span data-stu-id="a5bda-105">In some cases, you might want to associate one or more forms with a specific folder.</span></span> <span data-ttu-id="a5bda-106">例如，您的组织中的员工无法所有具有进度报告文件夹创建和存储进度报告其个人消息存储中。</span><span class="sxs-lookup"><span data-stu-id="a5bda-106">For example, employees in your organization could all have a Progress Report folder in their personal message store for creating and storing progress reports.</span></span> <span data-ttu-id="a5bda-107">进度报告是特定于每个用户的进度报告文件夹，因为它可能不适合在系统范围的窗体库中存储的进度报告窗体。</span><span class="sxs-lookup"><span data-stu-id="a5bda-107">Because the progress report is specific to each user's Progress Report folder, it might not be appropriate to store the progress report form in the system wide form library.</span></span> <span data-ttu-id="a5bda-108">但是，可以关联内容表中的每个用户的进度报告文件夹中保留的进度报告窗体副本。</span><span class="sxs-lookup"><span data-stu-id="a5bda-108">However, a copy of the progress report form can be kept in the associated-contents table of each user's Progress Report folder.</span></span> <span data-ttu-id="a5bda-109">此限制将用户指定的文件夹之外使用进度报告表单。</span><span class="sxs-lookup"><span data-stu-id="a5bda-109">This restricts the user from using progress report forms outside of the designated folder.</span></span>
  
<span data-ttu-id="a5bda-110">从概念上讲，没有一个文件夹表单库的每个文件夹中的消息存储，即使没有窗体服务器安装中。</span><span class="sxs-lookup"><span data-stu-id="a5bda-110">Conceptually, there is one folder form library for every folder in a message store, even if no form servers are installed in it.</span></span> <span data-ttu-id="a5bda-111">文件夹表单库实现像其他窗体库 — 它们存储为文件夹的备用部件中的关联内容表。</span><span class="sxs-lookup"><span data-stu-id="a5bda-111">Folder form libraries are implemented like other form libraries — they are stored as associated-contents tables in the alternate part of the folder.</span></span> <span data-ttu-id="a5bda-112">因为文件夹表单库包含的文件夹中，将其复制以及其父文件夹中复制操作。</span><span class="sxs-lookup"><span data-stu-id="a5bda-112">Because folder form libraries are contained in the folder, they are copied along with their parent folder in copy operations.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a5bda-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5bda-113">See also</span></span>



[<span data-ttu-id="a5bda-114">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="a5bda-114">MAPI Forms</span></span>](mapi-forms.md)

