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
ms.openlocfilehash: 381e2c9ec84811b69d666017a568e7b9cca21755
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418846"
---
# <a name="verifying-service-provider-configuration"></a><span data-ttu-id="a35ed-103">验证服务提供程序配置</span><span class="sxs-lookup"><span data-stu-id="a35ed-103">Verifying service provider configuration</span></span>
  
<span data-ttu-id="a35ed-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a35ed-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a35ed-105">您的登录 ([IABProvider：：Logon、IMSProvider：：Logon](iabprovider-logon.md)或[IXPProvider：：TransportLogon](ixpprovider-transportlogon.md)) 必须验证提供程序的配置。 [](imsprovider-logon.md)</span><span class="sxs-lookup"><span data-stu-id="a35ed-105">Your logon method ([IABProvider::Logon](iabprovider-logon.md), [IMSProvider::Logon](imsprovider-logon.md), or [IXPProvider::TransportLogon](ixpprovider-transportlogon.md)) must verify your provider's configuration.</span></span> <span data-ttu-id="a35ed-106">这包括检查完整操作所需的所有属性是否设置正确。</span><span class="sxs-lookup"><span data-stu-id="a35ed-106">This involves checking that all of the properties needed for full operation are set correctly.</span></span> <span data-ttu-id="a35ed-107">每个提供程序都需要不同数量的属性;配置取决于你的提供程序以及你允许的用户交互程度。</span><span class="sxs-lookup"><span data-stu-id="a35ed-107">Every provider requires a different number of properties; configuration depends on your provider and the degree of user interaction you allow.</span></span> <span data-ttu-id="a35ed-108">某些服务提供商在配置文件中保留所有必需的属性。</span><span class="sxs-lookup"><span data-stu-id="a35ed-108">Some service providers keep all of the necessary properties in the profile.</span></span> 

<span data-ttu-id="a35ed-109">其他服务提供商在配置文件中保留部分属性集，并提示用户输入缺失值。</span><span class="sxs-lookup"><span data-stu-id="a35ed-109">Other service providers keep a partial set of properties in the profile and prompt the user for missing values.</span></span> <span data-ttu-id="a35ed-110">此外，其他提供程序完全不会在配置文件中存储属性，而依赖用户提供配置所需的全部信息。</span><span class="sxs-lookup"><span data-stu-id="a35ed-110">Still other providers do not store properties in the profile at all, relying on the user to supply all of the information needed for configuration.</span></span>
  
### <a name="to-retrieve-properties-stored-in-the-profile"></a><span data-ttu-id="a35ed-111">检索配置文件中存储的属性</span><span class="sxs-lookup"><span data-stu-id="a35ed-111">To retrieve properties stored in the profile</span></span>
  
1. <span data-ttu-id="a35ed-112">调用 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md)，将提供程序的 [MAPIUID](mapiuid.md) 作为输入参数传递。</span><span class="sxs-lookup"><span data-stu-id="a35ed-112">Call [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md), passing the [MAPIUID](mapiuid.md) of your provider as an input parameter.</span></span> 
    
2. <span data-ttu-id="a35ed-113">调用配置文件节的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 或 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法来检索单个属性或属性列表。</span><span class="sxs-lookup"><span data-stu-id="a35ed-113">Call the profile section's [IMAPIProp::GetProps](imapiprop-getprops.md) or [IMAPIProp::GetPropList](imapiprop-getproplist.md) methods to retrieve individual properties or a property list.</span></span> 
    
### <a name="to-set-properties-from-user-information"></a><span data-ttu-id="a35ed-114">从用户信息设置属性</span><span class="sxs-lookup"><span data-stu-id="a35ed-114">To set properties from user information</span></span>
  
<span data-ttu-id="a35ed-115">显示属性表，如果 MAPI 尚未设置禁止显示的标志。</span><span class="sxs-lookup"><span data-stu-id="a35ed-115">Display a property sheet, if MAPI has not set a flag prohibiting the display.</span></span> <span data-ttu-id="a35ed-116">以下标志指示无法显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="a35ed-116">The following flags indicate that a user interface cannot be presented.</span></span>
  
|<span data-ttu-id="a35ed-117">**Flag**</span><span class="sxs-lookup"><span data-stu-id="a35ed-117">**Flag**</span></span>|<span data-ttu-id="a35ed-118">**服务提供程序**</span><span class="sxs-lookup"><span data-stu-id="a35ed-118">**Service provider**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a35ed-119">AB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="a35ed-119">AB_NO_DIALOG</span></span>  <br/> |<span data-ttu-id="a35ed-120">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="a35ed-120">Address book provider</span></span>  <br/> |
|<span data-ttu-id="a35ed-121">LOGON_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="a35ed-121">LOGON_NO_DIALOG</span></span>  <br/> |<span data-ttu-id="a35ed-122">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="a35ed-122">Transport provider</span></span>  <br/> |
|<span data-ttu-id="a35ed-123">MDB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="a35ed-123">MDB_NO_DIALOG</span></span>  <br/> |<span data-ttu-id="a35ed-124">邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="a35ed-124">Message store provider</span></span>  <br/> |
   
<span data-ttu-id="a35ed-125">如果你的提供程序未在配置文件中存储其所有配置属性，因此需要用户交互，并且 MAPI 将其中一个对话框抑制标志传递给你的登录方法，则返回MAPI_E_UNCONFIGURED。</span><span class="sxs-lookup"><span data-stu-id="a35ed-125">If your provider does not store all of its configuration properties in the profile, requiring user interaction, and MAPI passes one of the dialog box suppression flags to your logon method, return MAPI_E_UNCONFIGURED.</span></span> <span data-ttu-id="a35ed-126">此外，在未设置对话框抑制标志，但用户未提供所有所需信息时，也返回此错误。</span><span class="sxs-lookup"><span data-stu-id="a35ed-126">Also return this error when the dialog suppression flag is not set, but the user does not supply all of the required information.</span></span>
  
<span data-ttu-id="a35ed-127">当服务提供程序在其登录方法失败时MAPI_E_UNCONFIGURED MAPI 将再次调用入口点函数。</span><span class="sxs-lookup"><span data-stu-id="a35ed-127">When your service provider fails its logon method with MAPI_E_UNCONFIGURED, MAPI calls your entry point function again.</span></span> <span data-ttu-id="a35ed-128">如果无法通过第二次调用找到该信息，则会话可能会终止，具体取决于您的服务提供商非常重要。</span><span class="sxs-lookup"><span data-stu-id="a35ed-128">If the information cannot be located with the second call, the session might terminate, depending on how important your service provider is.</span></span> 
  
<span data-ttu-id="a35ed-129">下图显示了在服务提供程序登录方法中配置所需的逻辑。</span><span class="sxs-lookup"><span data-stu-id="a35ed-129">The following illustration shows the logic required for configuration in your service provider logon method.</span></span> 
  
<span data-ttu-id="a35ed-130">**配置验证流程图**</span><span class="sxs-lookup"><span data-stu-id="a35ed-130">**Configuration verification flowchart**</span></span>
  
<span data-ttu-id="a35ed-131">![配置验证流程图](media/amapi_62.gif "配置验证流程图")</span><span class="sxs-lookup"><span data-stu-id="a35ed-131">![Configuration verification flowchart](media/amapi_62.gif "Configuration verification flowchart")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a35ed-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a35ed-132">See also</span></span>

- [<span data-ttu-id="a35ed-133">实现服务提供程序登录</span><span class="sxs-lookup"><span data-stu-id="a35ed-133">Implementing Service Provider Logon</span></span>](implementing-service-provider-logon.md)

