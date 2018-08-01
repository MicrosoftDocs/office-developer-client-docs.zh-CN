---
title: 使对象无效
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7d601cee-ffc4-4c7c-8006-40b717dee247
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9c0ba8f1f0bf31bb892f380df310cd9fa7a8a24f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775962"
---
# <a name="invalidating-an-object"></a><span data-ttu-id="492a7-103">使对象无效</span><span class="sxs-lookup"><span data-stu-id="492a7-103">Invalidating an Object</span></span>

  
  
<span data-ttu-id="492a7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="492a7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="492a7-105">为您提供商的关闭过程的一部分，您可能想要使无效对象。</span><span class="sxs-lookup"><span data-stu-id="492a7-105">As part of your provider's shutdown process, you might want to invalidate an object.</span></span> <span data-ttu-id="492a7-106">使无效对象涉及将包含的三种**IUnknown**方法的实现 vtable 替换为其 vtable: **AddRef**和**Release**， **QueryInterface**。</span><span class="sxs-lookup"><span data-stu-id="492a7-106">Invalidating an object involves replacing its vtable with a vtable that contains implementations for the three **IUnknown** methods: **AddRef**, **Release**, and **QueryInterface**.</span></span> <span data-ttu-id="492a7-107">使对象无效通过调用[IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md)，每个三个公共提供程序类型的支持对象中包含的方法。</span><span class="sxs-lookup"><span data-stu-id="492a7-107">Invalidate an object by calling [IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md), a method that is included in the support object of each of the three common provider types.</span></span> <span data-ttu-id="492a7-108">提供程序通常在其登录对象**注销**方法的实现中进行此呼叫。</span><span class="sxs-lookup"><span data-stu-id="492a7-108">Providers typically make this call in the implementation of their logon object's **Logoff** method.</span></span> 
  
<span data-ttu-id="492a7-109">使无效对象提供了 MAPI 最终负责释放与对象关联的内存。</span><span class="sxs-lookup"><span data-stu-id="492a7-109">Invalidating an object gives MAPI the ultimate responsibility for freeing the memory associated with an object.</span></span> <span data-ttu-id="492a7-110">您可以释放所有连接与对象的资源，然后调用**MakeInvalid**使所有其继承接口中的方法无效。</span><span class="sxs-lookup"><span data-stu-id="492a7-110">You can free all of the resources connected with an object and then call **MakeInvalid** to invalidate all of the methods in its inherited interfaces.</span></span> <span data-ttu-id="492a7-111">调用下列任一方法将返回 MAPI_E_INVALID_OBJECT。</span><span class="sxs-lookup"><span data-stu-id="492a7-111">Calls to any of these methods will return MAPI_E_INVALID_OBJECT.</span></span> <span data-ttu-id="492a7-112">使用**MakeInvalid**是许多服务提供商忽略选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="492a7-112">Using **MakeInvalid** is an option that many service providers choose to ignore.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="492a7-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="492a7-113">See also</span></span>



[<span data-ttu-id="492a7-114">关闭服务提供程序</span><span class="sxs-lookup"><span data-stu-id="492a7-114">Shutting Down a Service Provider</span></span>](shutting-down-a-service-provider.md)

