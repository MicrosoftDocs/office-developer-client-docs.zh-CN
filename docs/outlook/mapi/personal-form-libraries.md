---
title: 个人表单库
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6ffcd93c-3737-4342-9cd0-2ca7c0fba52c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c84665077f9c8e02647a4d348042515366b0c090
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420407"
---
# <a name="personal-form-libraries"></a><span data-ttu-id="911a0-103">个人表单库</span><span class="sxs-lookup"><span data-stu-id="911a0-103">Personal Form Libraries</span></span>

  
  
<span data-ttu-id="911a0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="911a0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="911a0-105">顾名思义, 个人表单库包含特定用户感兴趣的窗体。</span><span class="sxs-lookup"><span data-stu-id="911a0-105">As its name suggests, personal form libraries contain forms of interest to a particular user.</span></span> <span data-ttu-id="911a0-106">用户的个人表单库是与用户配置文件中标识的默认邮件存储关联的表单库;在工作站上安装的每个配置文件都可以使用单独的默认存储, 因此是单独的个人表单库。</span><span class="sxs-lookup"><span data-stu-id="911a0-106">A user's personal form library is the form library associated with the default message store identified in the user's profile; each profile installed on a workstation can use a separate default store, and therefore, a separate personal form library.</span></span> <span data-ttu-id="911a0-107">个人窗体库除了包含其他表单之外, 还可以包含其他表单库中包含的表单的副本。</span><span class="sxs-lookup"><span data-stu-id="911a0-107">A personal form library can contain copies of forms that are also contained in other form libraries in addition to other forms.</span></span>
  
<span data-ttu-id="911a0-108">个人表单库在用户的默认邮件存储中的根文件夹的 "关联内容" 表中实现, 无论是驻留在服务器上还是位于用户工作站的本地, 都是 immaterial。</span><span class="sxs-lookup"><span data-stu-id="911a0-108">A personal form library is implemented in the associated-contents table of the root folder in a user's default message store — whether that resides on a server or locally on the user's workstation is immaterial.</span></span> <span data-ttu-id="911a0-109">如果用户的默认邮件存储区存储在用户的工作站上, 则个人表单库通过使应用程序能够在本地 (而不是通过网络) 访问表单来提供增强的性能。</span><span class="sxs-lookup"><span data-stu-id="911a0-109">If the user's default message store is stored on the user's workstation, personal form libraries offer enhanced performance by enabling applications to access forms locally instead of over the network.</span></span> <span data-ttu-id="911a0-110">它还使得脱机工作的用户可以使用表单, 当用户想要将他们的表单与便携式计算机一起使用, 而不访问网络时, 会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="911a0-110">It also makes forms available to users working offline, which can occur when users want to take their forms with them on portable computers and are without access to a network.</span></span>
  
<span data-ttu-id="911a0-111">个人表单库条目的属性和基础实现包括一个 "容器 ID" 属性, 该属性标识本地条目必须与之同步的主容器。</span><span class="sxs-lookup"><span data-stu-id="911a0-111">The properties and underlying implementation of personal form library entries include a "Container ID" property that identifies a master container that the local entry must be synchronized with.</span></span> <span data-ttu-id="911a0-112">它可以是包含表单的任意文件夹的标识符。</span><span class="sxs-lookup"><span data-stu-id="911a0-112">This can be the identifier of an arbitrary folder that contains forms.</span></span> <span data-ttu-id="911a0-113">如果您使用的自定义窗体管理器支持某种组织范围的表单库, 这将非常有用。表单管理器将负责同步存储在个人表单库和组织范围的表单库中的表单。</span><span class="sxs-lookup"><span data-stu-id="911a0-113">This is useful if you are using a custom form manager that supports some sort of organization-wide form library; the form manager would take care of synchronizing the forms stored in the personal form library and the organization-wide form library.</span></span> <span data-ttu-id="911a0-114">这可能会在表单管理器加载后发生, 但在理论上任何时候都可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="911a0-114">This would probably happen when the form manager was loaded, but could theoretically happen at any time.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="911a0-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="911a0-115">See also</span></span>



[<span data-ttu-id="911a0-116">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="911a0-116">MAPI Forms</span></span>](mapi-forms.md)

