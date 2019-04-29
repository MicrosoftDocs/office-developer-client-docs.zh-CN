---
title: 使用自定义代码创建配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5632cd25-58f5-4b9c-906c-cd377abc3daf
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f3270528194b3cc3429d3afec153355349dabbff
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413302"
---
# <a name="creating-a-profile-by-using-custom-code"></a><span data-ttu-id="42781-103">使用自定义代码创建配置文件</span><span class="sxs-lookup"><span data-stu-id="42781-103">Creating a Profile by Using Custom Code</span></span>

  
  
<span data-ttu-id="42781-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="42781-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="42781-105">如果选择编写代码来创建配置文件, 请确保了解如何对配置文件条目进行排序, 以及每个条目所需的信息类型和数量。</span><span class="sxs-lookup"><span data-stu-id="42781-105">If you choose to write code to create a profile, make sure that you understand how to order profile entries and the type and amount of information that is needed for each entry.</span></span> <span data-ttu-id="42781-106">在配置文件中对条目进行排序的含义将在[MAPI 配置文件](mapi-profiles.md)中进行说明。</span><span class="sxs-lookup"><span data-stu-id="42781-106">The implications of ordering entries in a profile is explained in [MAPI Profiles](mapi-profiles.md).</span></span>
  
 <span data-ttu-id="42781-107">**使用 C 或 c + + 代码创建配置文件**</span><span class="sxs-lookup"><span data-stu-id="42781-107">**To create a profile with C or C++ code**</span></span>
  
1. <span data-ttu-id="42781-108">读取每个邮件服务的头文件。</span><span class="sxs-lookup"><span data-stu-id="42781-108">Read the header file for each message service.</span></span> <span data-ttu-id="42781-109">了解需要配置的属性以及将使用的值。</span><span class="sxs-lookup"><span data-stu-id="42781-109">Understand what properties you will need to configure and what values you will use.</span></span>
    
2. <span data-ttu-id="42781-110">调用[MAPIAdminProfiles](mapiadminprofiles.md)函数以检索**IProfAdmin**接口指针。</span><span class="sxs-lookup"><span data-stu-id="42781-110">Call the [MAPIAdminProfiles](mapiadminprofiles.md) function to retrieve an **IProfAdmin** interface pointer.</span></span> 
    
3. <span data-ttu-id="42781-111">调用[IProfAdmin:: CreateProfile](iprofadmin-createprofile.md)以创建您的配置文件。</span><span class="sxs-lookup"><span data-stu-id="42781-111">Call [IProfAdmin::CreateProfile](iprofadmin-createprofile.md) to create your profile.</span></span> <span data-ttu-id="42781-112">如果要使用 mapisvc.inf 的 **[默认服务]** 部分列出的邮件服务创建配置文件。INF 文件, 请设置 MAPI_DEFAULT_SERVICE 标志。</span><span class="sxs-lookup"><span data-stu-id="42781-112">If you want to create a profile with the message services listed in the **[Default Services]** section of the MAPISVC.INF file, set the MAPI_DEFAULT_SERVICE flag.</span></span> <span data-ttu-id="42781-113">如果要使用户能够输入配置信息, 请设置 MAPI_DIALOG 标志。</span><span class="sxs-lookup"><span data-stu-id="42781-113">If you want to enable the user to enter configuration information, set the MAPI_DIALOG flag.</span></span> <span data-ttu-id="42781-114">如果并非所有必需的信息都可通过 mapisvc.inf, 请确保您设置此标志。INF 文件。</span><span class="sxs-lookup"><span data-stu-id="42781-114">Make sure that you set this flag if not all of the necessary information is available through the MAPISVC.INF file.</span></span> <span data-ttu-id="42781-115">**CreateProfile**调用要添加到配置文件中的每个邮件服务的入口点函数, 并将 MSG_SERVICE_CREATE 设置为_ulContext_参数。</span><span class="sxs-lookup"><span data-stu-id="42781-115">**CreateProfile** calls the entry point function for each message service to be added to the profile with MSG_SERVICE_CREATE set as the  _ulContext_ parameter.</span></span> 
    
4. <span data-ttu-id="42781-116">调用[IProfAdmin:: AdminServices](iprofadmin-adminservices.md)以获取邮件服务管理对象。</span><span class="sxs-lookup"><span data-stu-id="42781-116">Call [IProfAdmin::AdminServices](iprofadmin-adminservices.md) to obtain a message service administration object.</span></span> 
    
5. <span data-ttu-id="42781-117">使用邮件服务管理对象将邮件服务添加到配置文件中。</span><span class="sxs-lookup"><span data-stu-id="42781-117">Use the message service administration object to add message services to the profile.</span></span> <span data-ttu-id="42781-118">对于要添加的每个邮件服务:</span><span class="sxs-lookup"><span data-stu-id="42781-118">For each message service that you want to add:</span></span>
    
1. <span data-ttu-id="42781-119">调用[IMsgServiceAdmin:: CreateMsgService](imsgserviceadmin-createmsgservice.md)方法以创建新的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="42781-119">Call the [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) method to create the new message service.</span></span> 
    
2. <span data-ttu-id="42781-120">调用[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md), 并将您刚创建的服务的**MAPIUID**结构和属性值数组与其配置属性进行传递。</span><span class="sxs-lookup"><span data-stu-id="42781-120">Call [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md), passing the **MAPIUID** structure of the service you just created and a property value array with its configuration properties.</span></span> 
    
6. <span data-ttu-id="42781-121">若要检索新添加的服务的标识符 (它是其**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性), 请调用[IMsgServiceAdmin:: GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)以访问邮件服务表, 并搜索表示的行邮件服务。</span><span class="sxs-lookup"><span data-stu-id="42781-121">To retrieve the identifier of a newly added service, which is its **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) property, call [IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) to access the message service table and search for the row that represents the message service.</span></span> <span data-ttu-id="42781-122">表中的最后一行表示最近添加的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="42781-122">The last row in the table will represent the most recently added message service.</span></span> 
    
<span data-ttu-id="42781-123">若要将新的配置文件设为临时, 请在登录后立即调用[IProfAdmin::D eleteprofile](iprofadmin-deleteprofile.md)方法。</span><span class="sxs-lookup"><span data-stu-id="42781-123">To make a new profile temporary, call the [IProfAdmin::DeleteProfile](iprofadmin-deleteprofile.md) method immediately after you log on.</span></span> <span data-ttu-id="42781-124">**DeleteProfile**会将新配置文件标记为已删除, 同时使其在会话期间可用。</span><span class="sxs-lookup"><span data-stu-id="42781-124">**DeleteProfile** will mark the new profile as deleted while making it usable for the duration of the session.</span></span> <span data-ttu-id="42781-125">由于它不会包含在会话的配置文件表中, 因此其他客户端将无法使用它。</span><span class="sxs-lookup"><span data-stu-id="42781-125">Because it will not be included in the session's profile table, other clients will be unable to use it.</span></span> 
  

