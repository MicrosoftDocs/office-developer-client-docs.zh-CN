---
title: 设计的消息服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 32627ebb-547f-4fac-a406-e7243ec5521b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 04aa4348560396c8237811252fd96a2b461cd791
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774768"
---
# <a name="designing-a-message-service"></a><span data-ttu-id="bc1a9-103">设计的消息服务</span><span class="sxs-lookup"><span data-stu-id="bc1a9-103">Designing a message service</span></span>

<span data-ttu-id="bc1a9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bc1a9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bc1a9-105">在开始编写代码以支持邮件服务之前，务必创建设计。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-105">Before you begin to write code to support your message service, it is important to create a design.</span></span> <span data-ttu-id="bc1a9-106">解决设计过程中的以下问题：</span><span class="sxs-lookup"><span data-stu-id="bc1a9-106">Resolve the following issues in your design process:</span></span>
  
1. <span data-ttu-id="bc1a9-107">确定应消息服务中包括多少服务提供商。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-107">Determine how many service providers should be included in the message service.</span></span> <span data-ttu-id="bc1a9-108">在服务中包括仅相关的服务提供程序 （即，提供程序使用相同的消息系统的）。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-108">Include only related service providers (that is, providers that work with the same messaging system) in your service.</span></span> <span data-ttu-id="bc1a9-109">不相关的服务提供商不属于同一消息服务。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-109">Unrelated service providers do not belong in the same message service.</span></span> <span data-ttu-id="bc1a9-110">使用集成不相关的服务提供商和消息服务的配置文件。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-110">Use the profile for integrating unrelated service providers and message services.</span></span>
    
2. <span data-ttu-id="bc1a9-111">确定哪种类型的服务提供程序应包含在邮件服务。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-111">Determine what type of service providers should be included in the message service.</span></span> <span data-ttu-id="bc1a9-112">大多数消息服务包括一个提供程序的每种常见的类型。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-112">Most messge services include one provider of each of the common types.</span></span> <span data-ttu-id="bc1a9-113">即典型的消息服务都有一个通讯簿提供程序、 一个消息存储提供程序和一个传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-113">That is, the typical message service has one address book provider, one message store provider, and one transport provider.</span></span>
    
3. <span data-ttu-id="bc1a9-114">确定多少 Dll 应包含邮件服务。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-114">Determine how many DLLs should contain the message service.</span></span> <span data-ttu-id="bc1a9-115">消息服务使用的 Dll 的数量取决于以下因素：</span><span class="sxs-lookup"><span data-stu-id="bc1a9-115">The number of DLLs that a message service uses depends on the following:</span></span>
    
   - <span data-ttu-id="bc1a9-116">您的邮件服务编写器作为愿意处理的复杂性程度。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-116">The degree of complexity that you as the writer of the message service are willing to handle.</span></span>
    
   - <span data-ttu-id="bc1a9-117">在消息服务的服务提供商的类型。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-117">The type of service providers in the message service.</span></span>
    
   - <span data-ttu-id="bc1a9-118">邮件服务可能必须与其他消息服务的关系。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-118">The relationship that the message service might have with another message service.</span></span>
    
   <span data-ttu-id="bc1a9-119">因为 MAPI 存储每个提供程序类型的一个入口点，不包括多个提供程序类型相同的单个 DLL 中。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-119">Because MAPI stores only one entry point for each provider type, do not include multiple providers of the same type in a single DLL.</span></span> <span data-ttu-id="bc1a9-120">如果要包含的一种类型的多个提供程序意义，在单独的 Dll 中实现它们或者了这些共享入口点函数。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-120">If it makes sense to include multiple providers of one type, either implement them in separate DLLs or have them share an entry point function.</span></span> <span data-ttu-id="bc1a9-121">另一个选项是实现相关的消息服务或消息服务，可以使用相同的安装和配置代码和相同的 DLL 入口点一个 DLL 函数。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-121">Another option is to implement related message services, or message services that are able to use the same installation and configuration code and the same DLL entry point function, in one DLL.</span></span>
    
   <span data-ttu-id="bc1a9-122">如果可能，使其简单，并使用一个 DLL，其中包含消息服务中的所有服务提供程序和所有代码以安装和配置消息服务的实现。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-122">If possible, keep it simple and use one DLL that contains the implementation of all the service providers in the message service and all the code to install and configure the message service.</span></span> <span data-ttu-id="bc1a9-123">如果此方法不可行，您可以实现的安装和配置代码和是所有服务提供商的单个 DLL 的一个动态链接库或每个提供程序的一个 DLL。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-123">If this is not possible, you can implement one DLL for the installation and configuration code and either a single DLL for all of the service providers or one DLL for each provider.</span></span>
    
4. <span data-ttu-id="bc1a9-124">确定动态链接库或 Dll 的消息服务的名称。</span><span class="sxs-lookup"><span data-stu-id="bc1a9-124">Determine a name for the message service DLL or DLLs.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="bc1a9-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc1a9-125">See also</span></span>

- [<span data-ttu-id="bc1a9-126">邮件服务实现</span><span class="sxs-lookup"><span data-stu-id="bc1a9-126">Message Service Implementation</span></span>](message-service-implementation.md)

