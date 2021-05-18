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
# <a name="creating-a-profile-by-using-custom-code"></a><span data-ttu-id="797ad-103">使用自定义代码创建配置文件</span><span class="sxs-lookup"><span data-stu-id="797ad-103">Creating a Profile by Using Custom Code</span></span>

  
  
<span data-ttu-id="797ad-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="797ad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="797ad-105">如果您选择编写代码来创建配置文件，请确保您了解如何对配置文件条目排序以及每个条目所需的类型和信息量。</span><span class="sxs-lookup"><span data-stu-id="797ad-105">If you choose to write code to create a profile, make sure that you understand how to order profile entries and the type and amount of information that is needed for each entry.</span></span> <span data-ttu-id="797ad-106">MAPI Profiles 中介绍了对配置文件中的条目 [排序的含义](mapi-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="797ad-106">The implications of ordering entries in a profile is explained in [MAPI Profiles](mapi-profiles.md).</span></span>
  
 <span data-ttu-id="797ad-107">**使用 C 或 C++ 代码创建配置文件**</span><span class="sxs-lookup"><span data-stu-id="797ad-107">**To create a profile with C or C++ code**</span></span>
  
1. <span data-ttu-id="797ad-108">读取每个邮件服务的标题文件。</span><span class="sxs-lookup"><span data-stu-id="797ad-108">Read the header file for each message service.</span></span> <span data-ttu-id="797ad-109">了解需要配置的属性以及将使用的值。</span><span class="sxs-lookup"><span data-stu-id="797ad-109">Understand what properties you will need to configure and what values you will use.</span></span>
    
2. <span data-ttu-id="797ad-110">调用 [MAPIAdminProfiles](mapiadminprofiles.md) 函数以检索 **IProfAdmin** 接口指针。</span><span class="sxs-lookup"><span data-stu-id="797ad-110">Call the [MAPIAdminProfiles](mapiadminprofiles.md) function to retrieve an **IProfAdmin** interface pointer.</span></span> 
    
3. <span data-ttu-id="797ad-111">调用 [IProfAdmin：：CreateProfile](iprofadmin-createprofile.md) 以创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="797ad-111">Call [IProfAdmin::CreateProfile](iprofadmin-createprofile.md) to create your profile.</span></span> <span data-ttu-id="797ad-112">如果要使用 MAPISVC **的 [默认服务]** 部分中列出的邮件服务创建配置文件。INF 文件，设置MAPI_DEFAULT_SERVICE标记。</span><span class="sxs-lookup"><span data-stu-id="797ad-112">If you want to create a profile with the message services listed in the **[Default Services]** section of the MAPISVC.INF file, set the MAPI_DEFAULT_SERVICE flag.</span></span> <span data-ttu-id="797ad-113">如果要允许用户输入配置信息，请设置MAPI_DIALOG标记。</span><span class="sxs-lookup"><span data-stu-id="797ad-113">If you want to enable the user to enter configuration information, set the MAPI_DIALOG flag.</span></span> <span data-ttu-id="797ad-114">如果并非所有必要信息都可以通过 MAPISVC 获取，请确保设置此标志。INF 文件。</span><span class="sxs-lookup"><span data-stu-id="797ad-114">Make sure that you set this flag if not all of the necessary information is available through the MAPISVC.INF file.</span></span> <span data-ttu-id="797ad-115">**CreateProfile** 调用要添加到配置文件（将 MSG_SERVICE_CREATE  _ulContext_ 参数）的每个邮件服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="797ad-115">**CreateProfile** calls the entry point function for each message service to be added to the profile with MSG_SERVICE_CREATE set as the  _ulContext_ parameter.</span></span> 
    
4. <span data-ttu-id="797ad-116">调用 [IProfAdmin：：AdminServices](iprofadmin-adminservices.md) 以获取邮件服务管理对象。</span><span class="sxs-lookup"><span data-stu-id="797ad-116">Call [IProfAdmin::AdminServices](iprofadmin-adminservices.md) to obtain a message service administration object.</span></span> 
    
5. <span data-ttu-id="797ad-117">使用邮件服务管理对象将邮件服务添加到配置文件。</span><span class="sxs-lookup"><span data-stu-id="797ad-117">Use the message service administration object to add message services to the profile.</span></span> <span data-ttu-id="797ad-118">对于要添加的每个邮件服务：</span><span class="sxs-lookup"><span data-stu-id="797ad-118">For each message service that you want to add:</span></span>
    
1. <span data-ttu-id="797ad-119">调用 [IMsgServiceAdmin：：CreateMsgService](imsgserviceadmin-createmsgservice.md) 方法来创建新的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="797ad-119">Call the [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) method to create the new message service.</span></span> 
    
2. <span data-ttu-id="797ad-120">调用 [IMsgServiceAdmin：：ConfigureMsgService，](imsgserviceadmin-configuremsgservice.md)传递刚创建的服务的 **MAPIUID** 结构以及一个属性值数组及其配置属性。</span><span class="sxs-lookup"><span data-stu-id="797ad-120">Call [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md), passing the **MAPIUID** structure of the service you just created and a property value array with its configuration properties.</span></span> 
    
6. <span data-ttu-id="797ad-121">若要检索新添加的服务（即 **其 PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性）的标识符，请调用 [IMsgServiceAdmin：：GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) 以访问邮件服务表并搜索表示邮件服务的行。</span><span class="sxs-lookup"><span data-stu-id="797ad-121">To retrieve the identifier of a newly added service, which is its **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) property, call [IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) to access the message service table and search for the row that represents the message service.</span></span> <span data-ttu-id="797ad-122">表中的最后一行将表示最近添加的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="797ad-122">The last row in the table will represent the most recently added message service.</span></span> 
    
<span data-ttu-id="797ad-123">若要使新配置文件成为临时配置文件，请在您登录后立即调用 [IProfAdmin：:D eleteProfile](iprofadmin-deleteprofile.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="797ad-123">To make a new profile temporary, call the [IProfAdmin::DeleteProfile](iprofadmin-deleteprofile.md) method immediately after you log on.</span></span> <span data-ttu-id="797ad-124">**DeleteProfile** 将新配置文件标记为已删除，同时使其在会话期间可用。</span><span class="sxs-lookup"><span data-stu-id="797ad-124">**DeleteProfile** will mark the new profile as deleted while making it usable for the duration of the session.</span></span> <span data-ttu-id="797ad-125">因为它不会包含在会话的配置文件表中，所以其他客户端将无法使用它。</span><span class="sxs-lookup"><span data-stu-id="797ad-125">Because it will not be included in the session's profile table, other clients will be unable to use it.</span></span> 
  

