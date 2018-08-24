---
title: 验证服务提供程序配置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: dc23dc61-7b51-43ab-a184-ce0bdac91d03
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f6190b2860e227b24b34e31a4ee9741468383460
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589635"
---
# <a name="verifying-service-provider-configuration"></a><span data-ttu-id="31afa-103">验证服务提供程序配置</span><span class="sxs-lookup"><span data-stu-id="31afa-103">Verifying service provider configuration</span></span>
  
<span data-ttu-id="31afa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="31afa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="31afa-105">您的登录方法 （[IABProvider::Logon](iabprovider-logon.md)、 [IMSProvider::Logon](imsprovider-logon.md)或[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)） 必须验证提供程序的配置。</span><span class="sxs-lookup"><span data-stu-id="31afa-105">Your logon method ([IABProvider::Logon](iabprovider-logon.md), [IMSProvider::Logon](imsprovider-logon.md), or [IXPProvider::TransportLogon](ixpprovider-transportlogon.md)) must verify your provider's configuration.</span></span> <span data-ttu-id="31afa-106">此步骤需要检查正确设置的所有属性所需的完整的操作。</span><span class="sxs-lookup"><span data-stu-id="31afa-106">This involves checking that all of the properties needed for full operation are set correctly.</span></span> <span data-ttu-id="31afa-107">每个提供程序需要大量不同的属性。配置取决于您的提供商和允许的用户交互程度。</span><span class="sxs-lookup"><span data-stu-id="31afa-107">Every provider requires a different number of properties; configuration depends on your provider and the degree of user interaction you allow.</span></span> <span data-ttu-id="31afa-108">某些服务提供程序将保留所有必要的属性配置文件中。</span><span class="sxs-lookup"><span data-stu-id="31afa-108">Some service providers keep all of the necessary properties in the profile.</span></span> 

<span data-ttu-id="31afa-109">其他服务提供程序配置文件中保留一组部分属性，并提示用户输入缺少的值。</span><span class="sxs-lookup"><span data-stu-id="31afa-109">Other service providers keep a partial set of properties in the profile and prompt the user for missing values.</span></span> <span data-ttu-id="31afa-110">仍其他提供程序不存储属性配置文件中，所有依赖于用户提供所有所需的配置信息。</span><span class="sxs-lookup"><span data-stu-id="31afa-110">Still other providers do not store properties in the profile at all, relying on the user to supply all of the information needed for configuration.</span></span>
  
### <a name="to-retrieve-properties-stored-in-the-profile"></a><span data-ttu-id="31afa-111">若要检索存储在配置文件属性</span><span class="sxs-lookup"><span data-stu-id="31afa-111">To retrieve properties stored in the profile</span></span>
  
1. <span data-ttu-id="31afa-112">调用[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)，将您的提供商[MAPIUID](mapiuid.md)作为输入参数传递。</span><span class="sxs-lookup"><span data-stu-id="31afa-112">Call [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md), passing the [MAPIUID](mapiuid.md) of your provider as an input parameter.</span></span> 
    
2. <span data-ttu-id="31afa-113">调用配置文件部分的[IMAPIProp::GetProps](imapiprop-getprops.md)或[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法来检索单个属性或属性列表。</span><span class="sxs-lookup"><span data-stu-id="31afa-113">Call the profile section's [IMAPIProp::GetProps](imapiprop-getprops.md) or [IMAPIProp::GetPropList](imapiprop-getproplist.md) methods to retrieve individual properties or a property list.</span></span> 
    
### <a name="to-set-properties-from-user-information"></a><span data-ttu-id="31afa-114">若要从用户信息设置属性</span><span class="sxs-lookup"><span data-stu-id="31afa-114">To set properties from user information</span></span>
  
<span data-ttu-id="31afa-115">如果 MAPI 还没有设置禁止显示一个标志，显示属性表、。</span><span class="sxs-lookup"><span data-stu-id="31afa-115">Display a property sheet, if MAPI has not set a flag prohibiting the display.</span></span> <span data-ttu-id="31afa-116">以下标志指示无法看到一个用户界面。</span><span class="sxs-lookup"><span data-stu-id="31afa-116">The following flags indicate that a user interface cannot be presented.</span></span>
  
|<span data-ttu-id="31afa-117">**Flag**</span><span class="sxs-lookup"><span data-stu-id="31afa-117">**Flag**</span></span>|<span data-ttu-id="31afa-118">**服务提供商**</span><span class="sxs-lookup"><span data-stu-id="31afa-118">**Service provider**</span></span>|
|:-----|:-----|
|<span data-ttu-id="31afa-119">AB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="31afa-119">AB_NO_DIALOG</span></span>  <br/> |<span data-ttu-id="31afa-120">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="31afa-120">Address book provider</span></span>  <br/> |
|<span data-ttu-id="31afa-121">LOGON_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="31afa-121">LOGON_NO_DIALOG</span></span>  <br/> |<span data-ttu-id="31afa-122">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="31afa-122">Transport provider</span></span>  <br/> |
|<span data-ttu-id="31afa-123">MDB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="31afa-123">MDB_NO_DIALOG</span></span>  <br/> |<span data-ttu-id="31afa-124">消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="31afa-124">Message store provider</span></span>  <br/> |
   
<span data-ttu-id="31afa-125">如果您的提供商不会存储其配置属性的所有配置文件中, 需要用户交互，并 MAPI 将将其中一个对话框中禁止显示标志传递给 logon 方法，则返回 MAPI_E_UNCONFIGURED。</span><span class="sxs-lookup"><span data-stu-id="31afa-125">If your provider does not store all of its configuration properties in the profile, requiring user interaction, and MAPI passes one of the dialog box suppression flags to your logon method, return MAPI_E_UNCONFIGURED.</span></span> <span data-ttu-id="31afa-126">未设置对话框禁止显示标志，但用户不会提供所有所需的信息时，还返回此错误。</span><span class="sxs-lookup"><span data-stu-id="31afa-126">Also return this error when the dialog suppression flag is not set, but the user does not supply all of the required information.</span></span>
  
<span data-ttu-id="31afa-127">服务提供商失败时其登录方法与 MAPI_E_UNCONFIGURED，MAPI 再次调用您入口点函数。</span><span class="sxs-lookup"><span data-stu-id="31afa-127">When your service provider fails its logon method with MAPI_E_UNCONFIGURED, MAPI calls your entry point function again.</span></span> <span data-ttu-id="31afa-128">如果信息不能位于与第二个呼叫，可能终止会话，具体取决于是如何重要服务提供商。</span><span class="sxs-lookup"><span data-stu-id="31afa-128">If the information cannot be located with the second call, the session might terminate, depending on how important your service provider is.</span></span> 
  
<span data-ttu-id="31afa-129">下图显示了您的服务提供登录方法中的配置所需的逻辑。</span><span class="sxs-lookup"><span data-stu-id="31afa-129">The following illustration shows the logic required for configuration in your service provider logon method.</span></span> 
  
<span data-ttu-id="31afa-130">**配置验证流程图**</span><span class="sxs-lookup"><span data-stu-id="31afa-130">**Configuration verification flowchart**</span></span>
  
<span data-ttu-id="31afa-131">![配置验证流程图](media/amapi_62.gif "配置验证流程图")</span><span class="sxs-lookup"><span data-stu-id="31afa-131">![Configuration verification flowchart](media/amapi_62.gif "Configuration verification flowchart")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="31afa-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31afa-132">See also</span></span>

- [<span data-ttu-id="31afa-133">实现服务提供程序登录</span><span class="sxs-lookup"><span data-stu-id="31afa-133">Implementing Service Provider Logon</span></span>](implementing-service-provider-logon.md)

