---
title: 实现安全性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 62db34a0-887c-4607-94ad-d8cae68b35c2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f09d96fd8b35df6cafa81b3830642cf6d67806e7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775822"
---
# <a name="implementing-security"></a><span data-ttu-id="cce46-103">实现安全性</span><span class="sxs-lookup"><span data-stu-id="cce46-103">Implementing Security</span></span>

  
  
<span data-ttu-id="cce46-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cce46-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cce46-105">如果消息的系统要求，传输提供程序负责为实现适当的访问邮件系统的安全级别。</span><span class="sxs-lookup"><span data-stu-id="cce46-105">If the messaging system requires it, the transport provider is responsible for implementing an appropriate level of security for access to the messaging system.</span></span> <span data-ttu-id="cce46-106">通过传输提供程序通过 MAPI 后台处理程序发送的每个传入或传出邮件处理提供程序的登录会话的上下文中。</span><span class="sxs-lookup"><span data-stu-id="cce46-106">Each incoming or outgoing message sent through a transport provider by the MAPI spooler is handled in the context of a provider logon session.</span></span> <span data-ttu-id="cce46-107">传输提供程序可以向建立此类连接前提示用户的凭据的用户显示的登录对话框。</span><span class="sxs-lookup"><span data-stu-id="cce46-107">The transport provider can display a logon dialog box to the user that prompts for a user's credentials before establishing such a connection.</span></span> <span data-ttu-id="cce46-108">此外，传输提供程序可以存储安全属性范围内配置文件一节中的用户的以前输入的凭据，并使用它们的访问而不提示。</span><span class="sxs-lookup"><span data-stu-id="cce46-108">Alternatively, the transport provider can store the user's previously entered credentials in the secure property range within a profile section and use them for access without prompting.</span></span>
  
<span data-ttu-id="cce46-109">实现传输提供程序的安全时, 考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="cce46-109">When implementing your transport provider's security, consider the following:</span></span>
  
- <span data-ttu-id="cce46-110">与多个安装的服务提供程序，可以有大量的用户名和密码与用户关联。</span><span class="sxs-lookup"><span data-stu-id="cce46-110">With multiple installed service providers, there can be a multitude of names and passwords associated with a user.</span></span>
    
- <span data-ttu-id="cce46-111">MAPI 允许与多个身份的多个会话。</span><span class="sxs-lookup"><span data-stu-id="cce46-111">MAPI allows multiple sessions with multiple identities.</span></span> <span data-ttu-id="cce46-112">提供程序鼓励支持多个会话，但不是需要这样做。</span><span class="sxs-lookup"><span data-stu-id="cce46-112">Providers are encouraged to support multiple sessions but are not required to do so.</span></span>
    
- <span data-ttu-id="cce46-113">与用户的配置文件中的离散节，每个会话与传输提供程序相关联 MAPI。</span><span class="sxs-lookup"><span data-stu-id="cce46-113">Each session with a transport provider is associated by MAPI with a discrete section in the user's profile.</span></span> <span data-ttu-id="cce46-114">传输提供程序可以使用[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)方法可访问此部分中，可用于存储与此会话，包括凭据关联的任何信息。</span><span class="sxs-lookup"><span data-stu-id="cce46-114">The transport provider can use the [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method to gain access to this section, which can be used to store any information associated with this session, including credentials.</span></span> 
    
- <span data-ttu-id="cce46-115">与多个已安装的传输提供程序，就不一定是 true 用户仅有单个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="cce46-115">With multiple installed transport providers, it is not necessarily true that the user only has a single email address.</span></span> <span data-ttu-id="cce46-116">用户可以为每个已安装的传输提供程序具有单独的电子邮件地址，或为每个会话在单个提供程序可以具有不同的地址。</span><span class="sxs-lookup"><span data-stu-id="cce46-116">A user can have a separate email address for each installed transport provider or can have a different address for each session on a single provider.</span></span>
    
<span data-ttu-id="cce46-117">有关将凭据存储在配置文件部分的详细信息，请参阅[消息服务和配置文件](message-services-and-profiles.md)和[IProfSect: IMAPIProp](iprofsectimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="cce46-117">For more information about storing credentials in profile sections, see [Message Services and Profiles](message-services-and-profiles.md) and [IProfSect : IMAPIProp](iprofsectimapiprop.md).</span></span>
  

