---
title: 使对象无效
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7d601cee-ffc4-4c7c-8006-40b717dee247
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bf7ef15ccfd9cd015771785bda9d6ad79415736b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317197"
---
# <a name="invalidating-an-object"></a><span data-ttu-id="da7c7-103">使对象无效</span><span class="sxs-lookup"><span data-stu-id="da7c7-103">Invalidating an Object</span></span>

  
  
<span data-ttu-id="da7c7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="da7c7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="da7c7-105">作为提供程序关闭过程的一部分, 您可能需要使对象无效。</span><span class="sxs-lookup"><span data-stu-id="da7c7-105">As part of your provider's shutdown process, you might want to invalidate an object.</span></span> <span data-ttu-id="da7c7-106">使对象失效的操作涉及将其 vtable 替换为包含三个**IUnknown**方法的实现的 vtable: **AddRef**、 **Release**和**QueryInterface**。</span><span class="sxs-lookup"><span data-stu-id="da7c7-106">Invalidating an object involves replacing its vtable with a vtable that contains implementations for the three **IUnknown** methods: **AddRef**, **Release**, and **QueryInterface**.</span></span> <span data-ttu-id="da7c7-107">通过调用[IMAPISupport:: MakeInvalid](imapisupport-makeinvalid.md), 可通过以下三种常见提供程序类型的每个支持对象中包含的方法使对象无效。</span><span class="sxs-lookup"><span data-stu-id="da7c7-107">Invalidate an object by calling [IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md), a method that is included in the support object of each of the three common provider types.</span></span> <span data-ttu-id="da7c7-108">提供程序通常会在其登录对象的**注销**方法的实现中进行此调用。</span><span class="sxs-lookup"><span data-stu-id="da7c7-108">Providers typically make this call in the implementation of their logon object's **Logoff** method.</span></span> 
  
<span data-ttu-id="da7c7-109">使对象无效的方式使 MAPI 成为释放与对象关联的内存的最终责任。</span><span class="sxs-lookup"><span data-stu-id="da7c7-109">Invalidating an object gives MAPI the ultimate responsibility for freeing the memory associated with an object.</span></span> <span data-ttu-id="da7c7-110">您可以释放与某个对象连接的所有资源, 然后调用**MakeInvalid**以使其继承的接口中的所有方法无效。</span><span class="sxs-lookup"><span data-stu-id="da7c7-110">You can free all of the resources connected with an object and then call **MakeInvalid** to invalidate all of the methods in its inherited interfaces.</span></span> <span data-ttu-id="da7c7-111">对上述任一方法的调用将返回 MAPI_E_INVALID_OBJECT。</span><span class="sxs-lookup"><span data-stu-id="da7c7-111">Calls to any of these methods will return MAPI_E_INVALID_OBJECT.</span></span> <span data-ttu-id="da7c7-112">使用**MakeInvalid**是许多服务提供商选择忽略的一个选项。</span><span class="sxs-lookup"><span data-stu-id="da7c7-112">Using **MakeInvalid** is an option that many service providers choose to ignore.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="da7c7-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da7c7-113">See also</span></span>



[<span data-ttu-id="da7c7-114">关闭服务提供程序</span><span class="sxs-lookup"><span data-stu-id="da7c7-114">Shutting Down a Service Provider</span></span>](shutting-down-a-service-provider.md)

