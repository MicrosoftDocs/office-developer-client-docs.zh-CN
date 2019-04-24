---
title: 实现安全性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 62db34a0-887c-4607-94ad-d8cae68b35c2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c430160ee508a86f36d840c7916c0516cfc10fbd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310057"
---
# <a name="implementing-security"></a><span data-ttu-id="7f6cd-103">实现安全性</span><span class="sxs-lookup"><span data-stu-id="7f6cd-103">Implementing Security</span></span>

  
  
<span data-ttu-id="7f6cd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7f6cd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7f6cd-105">如果邮件系统需要它, 则传输提供程序负责实现相应的安全级别, 以访问邮件系统。</span><span class="sxs-lookup"><span data-stu-id="7f6cd-105">If the messaging system requires it, the transport provider is responsible for implementing an appropriate level of security for access to the messaging system.</span></span> <span data-ttu-id="7f6cd-106">MAPI 后台处理程序通过传输提供程序发送的每封传入或传出邮件在提供程序登录会话的上下文中进行处理。</span><span class="sxs-lookup"><span data-stu-id="7f6cd-106">Each incoming or outgoing message sent through a transport provider by the MAPI spooler is handled in the context of a provider logon session.</span></span> <span data-ttu-id="7f6cd-107">在建立此类连接之前, 传输提供程序可以向用户显示登录对话框, 以提示输入用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="7f6cd-107">The transport provider can display a logon dialog box to the user that prompts for a user's credentials before establishing such a connection.</span></span> <span data-ttu-id="7f6cd-108">或者, 传输提供程序可以将用户以前输入的凭据存储在 profile 节内的安全属性范围中, 并将其用于 access, 而无需提示。</span><span class="sxs-lookup"><span data-stu-id="7f6cd-108">Alternatively, the transport provider can store the user's previously entered credentials in the secure property range within a profile section and use them for access without prompting.</span></span>
  
<span data-ttu-id="7f6cd-109">在实现传输提供程序的安全性时, 请考虑以下事项:</span><span class="sxs-lookup"><span data-stu-id="7f6cd-109">When implementing your transport provider's security, consider the following:</span></span>
  
- <span data-ttu-id="7f6cd-110">在安装了多个服务提供程序的情况下, 可能会有许多与用户相关联的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="7f6cd-110">With multiple installed service providers, there can be a multitude of names and passwords associated with a user.</span></span>
    
- <span data-ttu-id="7f6cd-111">MAPI 允许多个会话具有多个标识。</span><span class="sxs-lookup"><span data-stu-id="7f6cd-111">MAPI allows multiple sessions with multiple identities.</span></span> <span data-ttu-id="7f6cd-112">鼓励提供商支持多个会话, 但这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="7f6cd-112">Providers are encouraged to support multiple sessions but are not required to do so.</span></span>
    
- <span data-ttu-id="7f6cd-113">与传输提供程序的每个会话都与用户配置文件中的离散部分的 MAPI 关联。</span><span class="sxs-lookup"><span data-stu-id="7f6cd-113">Each session with a transport provider is associated by MAPI with a discrete section in the user's profile.</span></span> <span data-ttu-id="7f6cd-114">传输提供程序可以使用[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)方法获取对此部分的访问权限, 这可用于存储与此会话相关联的任何信息, 包括凭据。</span><span class="sxs-lookup"><span data-stu-id="7f6cd-114">The transport provider can use the [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method to gain access to this section, which can be used to store any information associated with this session, including credentials.</span></span> 
    
- <span data-ttu-id="7f6cd-115">如果有多个已安装的传输提供程序, 则不一定是用户只能有一个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7f6cd-115">With multiple installed transport providers, it is not necessarily true that the user only has a single email address.</span></span> <span data-ttu-id="7f6cd-116">用户可以为每个已安装的传输提供程序提供单独的电子邮件地址, 也可以为单个提供程序上的每个会话提供不同的地址。</span><span class="sxs-lookup"><span data-stu-id="7f6cd-116">A user can have a separate email address for each installed transport provider or can have a different address for each session on a single provider.</span></span>
    
<span data-ttu-id="7f6cd-117">有关在 profile 节中存储凭据的详细信息, 请参阅[Message Services and](message-services-and-profiles.md) profile and [IProfSect: IMAPIProp](iprofsectimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="7f6cd-117">For more information about storing credentials in profile sections, see [Message Services and Profiles](message-services-and-profiles.md) and [IProfSect : IMAPIProp](iprofsectimapiprop.md).</span></span>
  

