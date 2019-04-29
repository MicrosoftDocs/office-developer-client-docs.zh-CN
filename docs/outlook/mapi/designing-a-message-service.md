---
title: 设计邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 32627ebb-547f-4fac-a406-e7243ec5521b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 19a8a939685c440901f3f57d72baf673a579e590
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404293"
---
# <a name="designing-a-message-service"></a><span data-ttu-id="0136d-103">设计邮件服务</span><span class="sxs-lookup"><span data-stu-id="0136d-103">Designing a message service</span></span>

<span data-ttu-id="0136d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0136d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0136d-105">在开始编写代码以支持邮件服务之前, 一定要创建设计。</span><span class="sxs-lookup"><span data-stu-id="0136d-105">Before you begin to write code to support your message service, it is important to create a design.</span></span> <span data-ttu-id="0136d-106">在设计过程中解决以下问题:</span><span class="sxs-lookup"><span data-stu-id="0136d-106">Resolve the following issues in your design process:</span></span>
  
1. <span data-ttu-id="0136d-107">确定邮件服务中应包含多少个服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="0136d-107">Determine how many service providers should be included in the message service.</span></span> <span data-ttu-id="0136d-108">在服务中仅包括相关的服务提供程序 (即, 适用于同一邮件系统的提供程序)。</span><span class="sxs-lookup"><span data-stu-id="0136d-108">Include only related service providers (that is, providers that work with the same messaging system) in your service.</span></span> <span data-ttu-id="0136d-109">不相关的服务提供程序不属于同一邮件服务。</span><span class="sxs-lookup"><span data-stu-id="0136d-109">Unrelated service providers do not belong in the same message service.</span></span> <span data-ttu-id="0136d-110">使用用于集成不相关服务提供程序和邮件服务的配置文件。</span><span class="sxs-lookup"><span data-stu-id="0136d-110">Use the profile for integrating unrelated service providers and message services.</span></span>
    
2. <span data-ttu-id="0136d-111">确定邮件服务中应包含哪种类型的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="0136d-111">Determine what type of service providers should be included in the message service.</span></span> <span data-ttu-id="0136d-112">大多数 messge 服务包括每个通用类型的一个提供程序。</span><span class="sxs-lookup"><span data-stu-id="0136d-112">Most messge services include one provider of each of the common types.</span></span> <span data-ttu-id="0136d-113">也就是说, 典型的邮件服务有一个通讯簿提供程序、一个邮件存储提供程序和一个传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="0136d-113">That is, the typical message service has one address book provider, one message store provider, and one transport provider.</span></span>
    
3. <span data-ttu-id="0136d-114">确定应包含邮件服务的 dll 的数目。</span><span class="sxs-lookup"><span data-stu-id="0136d-114">Determine how many DLLs should contain the message service.</span></span> <span data-ttu-id="0136d-115">邮件服务使用的 dll 数取决于以下各项:</span><span class="sxs-lookup"><span data-stu-id="0136d-115">The number of DLLs that a message service uses depends on the following:</span></span>
    
   - <span data-ttu-id="0136d-116">您作为邮件服务编写者的复杂程度愿意处理。</span><span class="sxs-lookup"><span data-stu-id="0136d-116">The degree of complexity that you as the writer of the message service are willing to handle.</span></span>
    
   - <span data-ttu-id="0136d-117">邮件服务中的服务提供程序的类型。</span><span class="sxs-lookup"><span data-stu-id="0136d-117">The type of service providers in the message service.</span></span>
    
   - <span data-ttu-id="0136d-118">邮件服务可能与另一邮件服务之间的关系。</span><span class="sxs-lookup"><span data-stu-id="0136d-118">The relationship that the message service might have with another message service.</span></span>
    
   <span data-ttu-id="0136d-119">由于 MAPI 仅存储每个提供程序类型的一个入口点, 因此在一个 DLL 中不包含同一类型的多个提供程序。</span><span class="sxs-lookup"><span data-stu-id="0136d-119">Because MAPI stores only one entry point for each provider type, do not include multiple providers of the same type in a single DLL.</span></span> <span data-ttu-id="0136d-120">如果有必要包含一种类型的多个提供程序, 可以在单独的 dll 中实现它们, 也可以让它们共享入口点函数。</span><span class="sxs-lookup"><span data-stu-id="0136d-120">If it makes sense to include multiple providers of one type, either implement them in separate DLLs or have them share an entry point function.</span></span> <span data-ttu-id="0136d-121">另一种方法是在一个 DLL 中实现相关的邮件服务, 或者可以使用相同的安装和配置代码和同一个 dll 入口点函数的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="0136d-121">Another option is to implement related message services, or message services that are able to use the same installation and configuration code and the same DLL entry point function, in one DLL.</span></span>
    
   <span data-ttu-id="0136d-122">如果可能, 请将其简化并使用一个 DLL, 其中包含邮件服务中所有服务提供程序的实现以及要安装和配置邮件服务的所有代码。</span><span class="sxs-lookup"><span data-stu-id="0136d-122">If possible, keep it simple and use one DLL that contains the implementation of all the service providers in the message service and all the code to install and configure the message service.</span></span> <span data-ttu-id="0136d-123">如果不能这样做, 则可以为安装和配置代码实现一个 dll, 为所有服务提供程序实现一个 dll, 为每个提供程序实现一个 dll。</span><span class="sxs-lookup"><span data-stu-id="0136d-123">If this is not possible, you can implement one DLL for the installation and configuration code and either a single DLL for all of the service providers or one DLL for each provider.</span></span>
    
4. <span data-ttu-id="0136d-124">确定邮件服务 DLL 或 dll 的名称。</span><span class="sxs-lookup"><span data-stu-id="0136d-124">Determine a name for the message service DLL or DLLs.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="0136d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0136d-125">See also</span></span>

- [<span data-ttu-id="0136d-126">邮件服务实现</span><span class="sxs-lookup"><span data-stu-id="0136d-126">Message Service Implementation</span></span>](message-service-implementation.md)

