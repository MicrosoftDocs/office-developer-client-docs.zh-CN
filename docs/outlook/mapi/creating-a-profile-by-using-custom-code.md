---
title: 使用自定义代码创建配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5632cd25-58f5-4b9c-906c-cd377abc3daf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 74869293215b86c69ab4e0b1337be6014419fa3e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774734"
---
# <a name="creating-a-profile-by-using-custom-code"></a><span data-ttu-id="b803a-103">使用自定义代码创建配置文件</span><span class="sxs-lookup"><span data-stu-id="b803a-103">Creating a Profile by Using Custom Code</span></span>

  
  
<span data-ttu-id="b803a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b803a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b803a-105">如果您选择编写代码来创建一个配置文件，请确保您了解如何进行排序的配置文件条目的类型和数量的所需的每个项的信息。</span><span class="sxs-lookup"><span data-stu-id="b803a-105">If you choose to write code to create a profile, make sure that you understand how to order profile entries and the type and amount of information that is needed for each entry.</span></span> <span data-ttu-id="b803a-106">排序配置文件中的条目的含义是[MAPI 配置文件](mapi-profiles.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="b803a-106">The implications of ordering entries in a profile is explained in [MAPI Profiles](mapi-profiles.md).</span></span>
  
 <span data-ttu-id="b803a-107">**使用 C 或 c + + 代码创建一个配置文件**</span><span class="sxs-lookup"><span data-stu-id="b803a-107">**To create a profile with C or C++ code**</span></span>
  
1. <span data-ttu-id="b803a-108">读取每个消息服务的标头文件。</span><span class="sxs-lookup"><span data-stu-id="b803a-108">Read the header file for each message service.</span></span> <span data-ttu-id="b803a-109">了解您需要配置的属性和您值将使用什么。</span><span class="sxs-lookup"><span data-stu-id="b803a-109">Understand what properties you will need to configure and what values you will use.</span></span>
    
2. <span data-ttu-id="b803a-110">调用[MAPIAdminProfiles](mapiadminprofiles.md)函数以检索**IProfAdmin**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b803a-110">Call the [MAPIAdminProfiles](mapiadminprofiles.md) function to retrieve an **IProfAdmin** interface pointer.</span></span> 
    
3. <span data-ttu-id="b803a-111">调用[IProfAdmin::CreateProfile](iprofadmin-createprofile.md)创建您的配置文件。</span><span class="sxs-lookup"><span data-stu-id="b803a-111">Call [IProfAdmin::CreateProfile](iprofadmin-createprofile.md) to create your profile.</span></span> <span data-ttu-id="b803a-112">如果您想要创建一个具有 MAPISVC **[默认服务]** 节中列出的消息服务配置。INF 文件设置 MAPI_DEFAULT_SERVICE 标志。</span><span class="sxs-lookup"><span data-stu-id="b803a-112">If you want to create a profile with the message services listed in the **[Default Services]** section of the MAPISVC.INF file, set the MAPI_DEFAULT_SERVICE flag.</span></span> <span data-ttu-id="b803a-113">如果您想要让用户能够输入配置信息，设置 MAPI_DIALOG 标志。</span><span class="sxs-lookup"><span data-stu-id="b803a-113">If you want to enable the user to enter configuration information, set the MAPI_DIALOG flag.</span></span> <span data-ttu-id="b803a-114">请确保您设置此标志，如果不是所有必要信息都可通过 MAPISVC。INF 文件。</span><span class="sxs-lookup"><span data-stu-id="b803a-114">Make sure that you set this flag if not all of the necessary information is available through the MAPISVC.INF file.</span></span> <span data-ttu-id="b803a-115">**CreateProfile**调用入口点函数添加到配置文件与 MSG_SERVICE_CREATE 作为_ulContext_参数设置每个邮件服务。</span><span class="sxs-lookup"><span data-stu-id="b803a-115">**CreateProfile** calls the entry point function for each message service to be added to the profile with MSG_SERVICE_CREATE set as the  _ulContext_ parameter.</span></span> 
    
4. <span data-ttu-id="b803a-116">调用[IProfAdmin::AdminServices](iprofadmin-adminservices.md)获取消息服务管理对象。</span><span class="sxs-lookup"><span data-stu-id="b803a-116">Call [IProfAdmin::AdminServices](iprofadmin-adminservices.md) to obtain a message service administration object.</span></span> 
    
5. <span data-ttu-id="b803a-117">使用消息服务管理对象添加到配置文件的消息服务。</span><span class="sxs-lookup"><span data-stu-id="b803a-117">Use the message service administration object to add message services to the profile.</span></span> <span data-ttu-id="b803a-118">为每个要添加的消息服务：</span><span class="sxs-lookup"><span data-stu-id="b803a-118">For each message service that you want to add:</span></span>
    
1. <span data-ttu-id="b803a-119">调用[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)方法以创建新的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="b803a-119">Call the [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) method to create the new message service.</span></span> 
    
2. <span data-ttu-id="b803a-120">调用[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)，传递的您刚才创建的服务**MAPIUID**结构和配置属性的属性值数组。</span><span class="sxs-lookup"><span data-stu-id="b803a-120">Call [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md), passing the **MAPIUID** structure of the service you just created and a property value array with its configuration properties.</span></span> 
    
6. <span data-ttu-id="b803a-121">若要检索的一个新添加的服务，它是其**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性，标识符调用[IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)访问邮件服务表和行值，该值代表搜索邮件服务。</span><span class="sxs-lookup"><span data-stu-id="b803a-121">To retrieve the identifier of a newly added service, which is its **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) property, call [IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) to access the message service table and search for the row that represents the message service.</span></span> <span data-ttu-id="b803a-122">表中的最后一行将表示最近添加的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="b803a-122">The last row in the table will represent the most recently added message service.</span></span> 
    
<span data-ttu-id="b803a-123">将使新的配置文件设置为临时，可在登录后立即调用[IProfAdmin::DeleteProfile](iprofadmin-deleteprofile.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b803a-123">To make a new profile temporary, call the [IProfAdmin::DeleteProfile](iprofadmin-deleteprofile.md) method immediately after you log on.</span></span> <span data-ttu-id="b803a-124">为使其会话的持续时间内可用时已删除， **DeleteProfile**将标记新配置文件。</span><span class="sxs-lookup"><span data-stu-id="b803a-124">**DeleteProfile** will mark the new profile as deleted while making it usable for the duration of the session.</span></span> <span data-ttu-id="b803a-125">因为它不会将会话的配置文件表中，其他客户端将无法使用它。</span><span class="sxs-lookup"><span data-stu-id="b803a-125">Because it will not be included in the session's profile table, other clients will be unable to use it.</span></span> 
  

