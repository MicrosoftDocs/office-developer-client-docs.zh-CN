---
title: 个人表单库
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6ffcd93c-3737-4342-9cd0-2ca7c0fba52c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 546b45deaa856bbfa002797e491d9b47be0dd34a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581585"
---
# <a name="personal-form-libraries"></a><span data-ttu-id="ab5be-103">个人表单库</span><span class="sxs-lookup"><span data-stu-id="ab5be-103">Personal Form Libraries</span></span>

  
  
<span data-ttu-id="ab5be-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ab5be-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ab5be-105">顾名思义，个人窗体库包含关注某个特定用户的窗的体。</span><span class="sxs-lookup"><span data-stu-id="ab5be-105">As its name suggests, personal form libraries contain forms of interest to a particular user.</span></span> <span data-ttu-id="ab5be-106">用户的个人窗体库是与默认的邮件存储中的用户配置文件; 标识关联的表单库每个工作站上安装的配置文件可以使用不同的默认存储区，因此，一个单独的个人窗体库。</span><span class="sxs-lookup"><span data-stu-id="ab5be-106">A user's personal form library is the form library associated with the default message store identified in the user's profile; each profile installed on a workstation can use a separate default store, and therefore, a separate personal form library.</span></span> <span data-ttu-id="ab5be-107">个人窗体库可以包含还包含其他除了其他窗体的窗体库中的窗体的副本。</span><span class="sxs-lookup"><span data-stu-id="ab5be-107">A personal form library can contain copies of forms that are also contained in other form libraries in addition to other forms.</span></span>
  
<span data-ttu-id="ab5be-108">在用户的默认邮件存储区中的根文件夹的相关内容表中实现的个人窗体库 — 的驻留在服务器或本地用户的工作站上并不重要。</span><span class="sxs-lookup"><span data-stu-id="ab5be-108">A personal form library is implemented in the associated-contents table of the root folder in a user's default message store — whether that resides on a server or locally on the user's workstation is immaterial.</span></span> <span data-ttu-id="ab5be-109">如果用户的工作站上存储用户的默认邮件存储区，个人窗体库使应用程序能够通过网络访问形式而不是本地提供增强的性能。</span><span class="sxs-lookup"><span data-stu-id="ab5be-109">If the user's default message store is stored on the user's workstation, personal form libraries offer enhanced performance by enabling applications to access forms locally instead of over the network.</span></span> <span data-ttu-id="ab5be-110">它还使窗体可供脱机工作时用户希望采用其与他们便携式计算机上的形式可能发生，同时无须访问网络的用户。</span><span class="sxs-lookup"><span data-stu-id="ab5be-110">It also makes forms available to users working offline, which can occur when users want to take their forms with them on portable computers and are without access to a network.</span></span>
  
<span data-ttu-id="ab5be-111">属性和基础实现个人窗体库项包括"容器 ID"属性，用于标识必须与同步本地条目的主容器。</span><span class="sxs-lookup"><span data-stu-id="ab5be-111">The properties and underlying implementation of personal form library entries include a "Container ID" property that identifies a master container that the local entry must be synchronized with.</span></span> <span data-ttu-id="ab5be-112">这可以是任意文件夹包含表单的标识符。</span><span class="sxs-lookup"><span data-stu-id="ab5be-112">This can be the identifier of an arbitrary folder that contains forms.</span></span> <span data-ttu-id="ab5be-113">这很有用，如果您使用的支持组织范围内表单库; 某种自定义窗体管理器窗体管理器将负责同步个人窗体库和组织范围内窗体库中存储的表单。</span><span class="sxs-lookup"><span data-stu-id="ab5be-113">This is useful if you are using a custom form manager that supports some sort of organization-wide form library; the form manager would take care of synchronizing the forms stored in the personal form library and the organization-wide form library.</span></span> <span data-ttu-id="ab5be-114">窗体管理器已加载，但无法在任何时候理论上发生时，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="ab5be-114">This would probably happen when the form manager was loaded, but could theoretically happen at any time.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ab5be-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab5be-115">See also</span></span>



[<span data-ttu-id="ab5be-116">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="ab5be-116">MAPI Forms</span></span>](mapi-forms.md)

