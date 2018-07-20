---
title: IMsgServiceAdmin IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin
api_type:
- COM
ms.assetid: 5905b9e9-c462-451d-a49f-1f3a8aa506a6
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 21889bf626d7f9128d1e01b3e6a15b5fa0d2e696
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775889"
---
# <a name="imsgserviceadmin--iunknown"></a><span data-ttu-id="234e7-103">IMsgServiceAdmin: IUnknown</span><span class="sxs-lookup"><span data-stu-id="234e7-103">IMsgServiceAdmin : IUnknown</span></span>

  
  
<span data-ttu-id="234e7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="234e7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="234e7-105">对配置文件中的消息服务进行更改。</span><span class="sxs-lookup"><span data-stu-id="234e7-105">Makes changes to a message service in a profile.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="234e7-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="234e7-106">Header file:</span></span>  <br/> |<span data-ttu-id="234e7-107">MapiX.h</span><span class="sxs-lookup"><span data-stu-id="234e7-107">MapiX.h</span></span>  <br/> |
|<span data-ttu-id="234e7-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="234e7-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="234e7-109">消息服务管理对象</span><span class="sxs-lookup"><span data-stu-id="234e7-109">Message service administration objects</span></span>  <br/> |
|<span data-ttu-id="234e7-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="234e7-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="234e7-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="234e7-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="234e7-112">调用：</span><span class="sxs-lookup"><span data-stu-id="234e7-112">Called by:</span></span>  <br/> |<span data-ttu-id="234e7-113">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="234e7-113">Client applications</span></span>  <br/> |
|<span data-ttu-id="234e7-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="234e7-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="234e7-115">IID_IMsgServiceAdmin</span><span class="sxs-lookup"><span data-stu-id="234e7-115">IID_IMsgServiceAdmin</span></span>  <br/> |
|<span data-ttu-id="234e7-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="234e7-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="234e7-117">LPSERVICEADMIN</span><span class="sxs-lookup"><span data-stu-id="234e7-117">LPSERVICEADMIN</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="234e7-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="234e7-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="234e7-119">时出错</span><span class="sxs-lookup"><span data-stu-id="234e7-119">GetLastError</span></span>](imsgserviceadmin-getlasterror.md) <br/> |<span data-ttu-id="234e7-120">返回一个[MAPIERROR](mapierror.md)结构，其中包含信息由消息服务管理对象生成的最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="234e7-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the last error generated by a message service administration object.</span></span>  <br/> |
|[<span data-ttu-id="234e7-121">GetMsgServiceTable</span><span class="sxs-lookup"><span data-stu-id="234e7-121">GetMsgServiceTable</span></span>](imsgserviceadmin-getmsgservicetable.md) <br/> |<span data-ttu-id="234e7-122">提供对邮件服务表，该配置文件中的消息服务的列表的访问。</span><span class="sxs-lookup"><span data-stu-id="234e7-122">Provides access to the message service table, a list of the message services in the profile.</span></span>  <br/> |
|[<span data-ttu-id="234e7-123">CreateMsgService</span><span class="sxs-lookup"><span data-stu-id="234e7-123">CreateMsgService</span></span>](imsgserviceadmin-createmsgservice.md) <br/> |<span data-ttu-id="234e7-124">向当前配置文件的消息服务。</span><span class="sxs-lookup"><span data-stu-id="234e7-124">Adds a message service to the current profile.</span></span>  <br/> <br/><span data-ttu-id="234e7-125">**注意**： 此方法已被弃用。</span><span class="sxs-lookup"><span data-stu-id="234e7-125">**NOTE**: This method is deprecated.</span></span> <span data-ttu-id="234e7-126">请改用[IMsgServiceAdmin2::CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md) 。</span><span class="sxs-lookup"><span data-stu-id="234e7-126">Use [IMsgServiceAdmin2::CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md) instead.</span></span>           |
|[<span data-ttu-id="234e7-127">DeleteMsgService</span><span class="sxs-lookup"><span data-stu-id="234e7-127">DeleteMsgService</span></span>](imsgserviceadmin-deletemsgservice.md) <br/> |<span data-ttu-id="234e7-128">从配置文件中删除的消息服务。</span><span class="sxs-lookup"><span data-stu-id="234e7-128">Deletes a message service from a profile.</span></span>  <br/> |
|[<span data-ttu-id="234e7-129">CopyMsgService</span><span class="sxs-lookup"><span data-stu-id="234e7-129">CopyMsgService</span></span>](imsgserviceadmin-copymsgservice.md) <br/> |<span data-ttu-id="234e7-130">将邮件服务复制到一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="234e7-130">Copies a message service into a profile.</span></span>  <br/> |
|[<span data-ttu-id="234e7-131">RenameMsgService</span><span class="sxs-lookup"><span data-stu-id="234e7-131">RenameMsgService</span></span>](imsgserviceadmin-renamemsgservice.md) <br/> |<span data-ttu-id="234e7-132">已弃用。</span><span class="sxs-lookup"><span data-stu-id="234e7-132">Deprecated.</span></span> <span data-ttu-id="234e7-133">将新的名称分配给邮件服务。</span><span class="sxs-lookup"><span data-stu-id="234e7-133">Assigns a new name to a message service.</span></span>  <br/> |
|[<span data-ttu-id="234e7-134">ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="234e7-134">ConfigureMsgService</span></span>](imsgserviceadmin-configuremsgservice.md) <br/> |<span data-ttu-id="234e7-135">重新配置的消息服务。</span><span class="sxs-lookup"><span data-stu-id="234e7-135">Reconfigures a message service.</span></span>  <br/> |
|[<span data-ttu-id="234e7-136">OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="234e7-136">OpenProfileSection</span></span>](imsgserviceadmin-openprofilesection.md) <br/> |<span data-ttu-id="234e7-137">打开当前配置文件的节并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针。</span><span class="sxs-lookup"><span data-stu-id="234e7-137">Opens a section of the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="234e7-138">MsgServiceTransportOrder</span><span class="sxs-lookup"><span data-stu-id="234e7-138">MsgServiceTransportOrder</span></span>](imsgserviceadmin-msgservicetransportorder.md) <br/> |<span data-ttu-id="234e7-139">设置中的传输提供程序调用将邮件传递的顺序。</span><span class="sxs-lookup"><span data-stu-id="234e7-139">Sets the order in which transport providers are called to deliver a message.</span></span>  <br/> |
|[<span data-ttu-id="234e7-140">AdminProviders</span><span class="sxs-lookup"><span data-stu-id="234e7-140">AdminProviders</span></span>](imsgserviceadmin-adminproviders.md) <br/> |<span data-ttu-id="234e7-141">返回提供访问提供程序管理对象的指针。</span><span class="sxs-lookup"><span data-stu-id="234e7-141">Returns a pointer that provides access to a provider administration object.</span></span>  <br/> |
|[<span data-ttu-id="234e7-142">SetPrimaryIdentity</span><span class="sxs-lookup"><span data-stu-id="234e7-142">SetPrimaryIdentity</span></span>](imsgserviceadmin-setprimaryidentity.md) <br/> |<span data-ttu-id="234e7-143">指定要配置文件的主标识的供应商的消息服务。</span><span class="sxs-lookup"><span data-stu-id="234e7-143">Designates a message service to be the supplier of the primary identity for the profile.</span></span>  <br/> |
|[<span data-ttu-id="234e7-144">GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="234e7-144">GetProviderTable</span></span>](imsgserviceadmin-getprovidertable.md) <br/> |<span data-ttu-id="234e7-145">提供对提供程序表中，在配置文件中的服务提供商的列表的访问。</span><span class="sxs-lookup"><span data-stu-id="234e7-145">Provides access to the provider table, a listing of the service providers in the profile.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="234e7-146">备注</span><span class="sxs-lookup"><span data-stu-id="234e7-146">Remarks</span></span>

<span data-ttu-id="234e7-147">实现可以通过以下两种**IMsgServiceAdmin**界面得到指针： 通过调用[IMAPISession::AdminServices](imapisession-adminservices.md)方法或通过调用[IProfAdmin::AdminServices](iprofadmin-adminservices.md)方法。</span><span class="sxs-lookup"><span data-stu-id="234e7-147">An implementation can get a pointer to an **IMsgServiceAdmin** interface in two ways: by calling the [IMAPISession::AdminServices](imapisession-adminservices.md) method or by calling the [IProfAdmin::AdminServices](iprofadmin-adminservices.md) method.</span></span> <span data-ttu-id="234e7-148">对于主要关心配置文件配置的客户端， **IProfAdmin::AdminServices**是首选的方式获取**IMsgServiceAdmin**接口，因为未登录到 MAPI 会话的提供程序。</span><span class="sxs-lookup"><span data-stu-id="234e7-148">For clients primarily concerned with profile configuration, **IProfAdmin::AdminServices** is the preferred way to get the **IMsgServiceAdmin** interface, because it does not log on providers to the MAPI session.</span></span> <span data-ttu-id="234e7-149">如果客户端需要能够对活动配置文件进行更改，然后应该调用**IMAPISession::AdminServices**获取**IMsgServiceAdmin**指针。</span><span class="sxs-lookup"><span data-stu-id="234e7-149">If a client requires the ability to make changes to the active profile, then **IMAPISession::AdminServices** should be called to get the **IMsgServiceAdmin** pointer.</span></span> <span data-ttu-id="234e7-150">注意虽然 MAPI 不允许使用要删除的配置文件，没有任何安全措施，以防止客户端配置文件中删除所有邮件服务。</span><span class="sxs-lookup"><span data-stu-id="234e7-150">Be aware that although MAPI does not allow a profile that is in use to be deleted, there are no safeguards to prevent a client from removing all the message services in the profile.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="234e7-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="234e7-151">See also</span></span>



[<span data-ttu-id="234e7-152">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="234e7-152">MAPI Interfaces</span></span>](mapi-interfaces.md)
