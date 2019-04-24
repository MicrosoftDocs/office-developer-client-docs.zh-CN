---
title: 传输提供程序所需的功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a0d9a3e0-a500-4d72-8859-ecfd1604fc5b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7f9768d47cf740bdf50b439ee3af4b0d2a191602
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328684"
---
# <a name="required-functionality-for-transport-providers"></a><span data-ttu-id="ecae4-103">传输提供程序所需的功能</span><span class="sxs-lookup"><span data-stu-id="ecae4-103">Required Functionality for Transport Providers</span></span>

  
  
<span data-ttu-id="ecae4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ecae4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ecae4-105">每个 MAPI 传输提供程序都必须:</span><span class="sxs-lookup"><span data-stu-id="ecae4-105">Every MAPI transport provider must:</span></span>
  
- <span data-ttu-id="ecae4-106">遵循有关使用 MAPI 和其他服务提供商的一般准则。</span><span class="sxs-lookup"><span data-stu-id="ecae4-106">Follow the general guidelines for working with MAPI and other service providers.</span></span> <span data-ttu-id="ecae4-107">有关详细信息, 请参阅[MAPI 应用程序开发](mapi-application-development.md)和[MAPI 服务提供程序](mapi-service-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="ecae4-107">For more information, see [MAPI Application Development](mapi-application-development.md) and [MAPI Service Providers](mapi-service-providers.md).</span></span>
    
- <span data-ttu-id="ecae4-108">让其传输提供程序 DLL 向 MAPI 公开其[XPProviderInit](xpproviderinit.md)初始化功能。</span><span class="sxs-lookup"><span data-stu-id="ecae4-108">Have its transport provider DLL expose to MAPI its [XPProviderInit](xpproviderinit.md) initialization function.</span></span> 
    
- <span data-ttu-id="ecae4-109">向 MAPI 公开其[IXPProvider: iunknown](ixpprovideriunknown.md)和[IXPLogon: iunknown](ixplogoniunknown.md)接口的实现。</span><span class="sxs-lookup"><span data-stu-id="ecae4-109">Expose to MAPI its implementation of the [IXPProvider : IUnknown](ixpprovideriunknown.md) and [IXPLogon : IUnknown](ixplogoniunknown.md) interfaces.</span></span> 
    
- <span data-ttu-id="ecae4-110">向 MAPI 和客户端应用程序公开[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口的实现。</span><span class="sxs-lookup"><span data-stu-id="ecae4-110">Expose to MAPI and client applications its implementation of the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface.</span></span> <span data-ttu-id="ecae4-111">有关实现**IMAPIStatus**的详细信息, 请参阅[Status Object 实现](status-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="ecae4-111">For more information about implementing **IMAPIStatus**, see [Status Object Implementation](status-object-implementation.md).</span></span> 
    
- <span data-ttu-id="ecae4-112">为配置实现 "属性表" 对话框。</span><span class="sxs-lookup"><span data-stu-id="ecae4-112">Implement a property sheet dialog box for configuration.</span></span> <span data-ttu-id="ecae4-113">有关实现属性表的详细信息, 请参阅[property Sheet 实现](property-sheet-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="ecae4-113">For more information about implementing property sheets, see [Property Sheet Implementation](property-sheet-implementation.md).</span></span>
    

