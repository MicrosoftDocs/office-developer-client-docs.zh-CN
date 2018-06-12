---
title: 传输提供程序所需的功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a0d9a3e0-a500-4d72-8859-ecfd1604fc5b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: eb5d70c31f28df16593fb020f13124ea217476ca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778642"
---
# <a name="required-functionality-for-transport-providers"></a><span data-ttu-id="a9c3f-103">传输提供程序所需的功能</span><span class="sxs-lookup"><span data-stu-id="a9c3f-103">Required Functionality for Transport Providers</span></span>

  
  
<span data-ttu-id="a9c3f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a9c3f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a9c3f-105">每个 MAPI 传输提供程序必须：</span><span class="sxs-lookup"><span data-stu-id="a9c3f-105">Every MAPI transport provider must:</span></span>
  
- <span data-ttu-id="a9c3f-106">遵循使用 MAPI 和其他服务提供商的一般指南。</span><span class="sxs-lookup"><span data-stu-id="a9c3f-106">Follow the general guidelines for working with MAPI and other service providers.</span></span> <span data-ttu-id="a9c3f-107">有关详细信息，请参阅[MAPI 应用程序开发](mapi-application-development.md)和[MAPI 服务提供商](mapi-service-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="a9c3f-107">For more information, see [MAPI Application Development](mapi-application-development.md) and [MAPI Service Providers](mapi-service-providers.md).</span></span>
    
- <span data-ttu-id="a9c3f-108">具有其传输提供程序为 MAPI DLL 公开其[XPProviderInit](xpproviderinit.md)初始化函数。</span><span class="sxs-lookup"><span data-stu-id="a9c3f-108">Have its transport provider DLL expose to MAPI its [XPProviderInit](xpproviderinit.md) initialization function.</span></span> 
    
- <span data-ttu-id="a9c3f-109">为 MAPI 公开其实现[IXPProvider: IUnknown](ixpprovideriunknown.md)和[IXPLogon: IUnknown](ixplogoniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="a9c3f-109">Expose to MAPI its implementation of the [IXPProvider : IUnknown](ixpprovideriunknown.md) and [IXPLogon : IUnknown](ixplogoniunknown.md) interfaces.</span></span> 
    
- <span data-ttu-id="a9c3f-110">MAPI 和客户端应用程序公开其实现[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="a9c3f-110">Expose to MAPI and client applications its implementation of the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface.</span></span> <span data-ttu-id="a9c3f-111">有关实现**IMAPIStatus**的详细信息，请参阅[状态对象实现](status-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="a9c3f-111">For more information about implementing **IMAPIStatus**, see [Status Object Implementation](status-object-implementation.md).</span></span> 
    
- <span data-ttu-id="a9c3f-112">实现属性表对话框进行配置。</span><span class="sxs-lookup"><span data-stu-id="a9c3f-112">Implement a property sheet dialog box for configuration.</span></span> <span data-ttu-id="a9c3f-113">有关实现属性表的详细信息，请参阅[属性表实现](property-sheet-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="a9c3f-113">For more information about implementing property sheets, see [Property Sheet Implementation](property-sheet-implementation.md).</span></span>
    

