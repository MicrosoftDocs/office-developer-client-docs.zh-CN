---
title: 文件夹表单库
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 62b7480e-b3eb-45fb-b74d-62f1dc918a53
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ec12cf567dbbd8c1710f835a3c19369dd3626fd4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281555"
---
# <a name="folder-form-libraries"></a><span data-ttu-id="52b94-103">文件夹表单库</span><span class="sxs-lookup"><span data-stu-id="52b94-103">Folder Form Libraries</span></span>

  
  
<span data-ttu-id="52b94-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="52b94-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="52b94-105">在某些情况下, 您可能需要将一个或多个表单与特定文件夹相关联。</span><span class="sxs-lookup"><span data-stu-id="52b94-105">In some cases, you might want to associate one or more forms with a specific folder.</span></span> <span data-ttu-id="52b94-106">例如, 组织中的员工都可以在其个人邮件存储中拥有一个进度报告文件夹, 用于创建和存储进度报告。</span><span class="sxs-lookup"><span data-stu-id="52b94-106">For example, employees in your organization could all have a Progress Report folder in their personal message store for creating and storing progress reports.</span></span> <span data-ttu-id="52b94-107">由于进度报告是特定于每个用户的进度报告文件夹的, 因此在系统范围的表单库中存储进度报告表单可能不合适。</span><span class="sxs-lookup"><span data-stu-id="52b94-107">Because the progress report is specific to each user's Progress Report folder, it might not be appropriate to store the progress report form in the system wide form library.</span></span> <span data-ttu-id="52b94-108">但是, 可以将进度报告表单的副本保存在每个用户的 "进度报告" 文件夹的 "相关内容" 表中。</span><span class="sxs-lookup"><span data-stu-id="52b94-108">However, a copy of the progress report form can be kept in the associated-contents table of each user's Progress Report folder.</span></span> <span data-ttu-id="52b94-109">这将限制用户在指定的文件夹之外使用进度报告表单。</span><span class="sxs-lookup"><span data-stu-id="52b94-109">This restricts the user from using progress report forms outside of the designated folder.</span></span>
  
<span data-ttu-id="52b94-110">从概念上讲, 邮件存储区中的每个文件夹都有一个 "文件夹表单库", 即使其中未安装表单服务器也是如此。</span><span class="sxs-lookup"><span data-stu-id="52b94-110">Conceptually, there is one folder form library for every folder in a message store, even if no form servers are installed in it.</span></span> <span data-ttu-id="52b94-111">文件夹表单库的实现方式与其他表单库一样, 它们在文件夹的备用部分中存储为关联表。</span><span class="sxs-lookup"><span data-stu-id="52b94-111">Folder form libraries are implemented like other form libraries — they are stored as associated-contents tables in the alternate part of the folder.</span></span> <span data-ttu-id="52b94-112">由于文件夹表单库包含在文件夹中, 因此它们会在复制操作中与其父文件夹一起复制。</span><span class="sxs-lookup"><span data-stu-id="52b94-112">Because folder form libraries are contained in the folder, they are copied along with their parent folder in copy operations.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52b94-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52b94-113">See also</span></span>



[<span data-ttu-id="52b94-114">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="52b94-114">MAPI Forms</span></span>](mapi-forms.md)

