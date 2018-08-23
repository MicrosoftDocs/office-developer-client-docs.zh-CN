---
title: 传输提供程序的必需功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a0d9a3e0-a500-4d72-8859-ecfd1604fc5b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: dc1189df1b8ad8f8e613d6813681ed3f4148b122
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580493"
---
# <a name="required-functionality-for-transport-providers"></a><span data-ttu-id="af488-103">传输提供程序的必需功能</span><span class="sxs-lookup"><span data-stu-id="af488-103">Required Functionality for Transport Providers</span></span>

  
  
<span data-ttu-id="af488-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="af488-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="af488-105">每个 MAPI 传输提供程序必须：</span><span class="sxs-lookup"><span data-stu-id="af488-105">Every MAPI transport provider must:</span></span>
  
- <span data-ttu-id="af488-106">遵循使用 MAPI 和其他服务提供商的一般指南。</span><span class="sxs-lookup"><span data-stu-id="af488-106">Follow the general guidelines for working with MAPI and other service providers.</span></span> <span data-ttu-id="af488-107">有关详细信息，请参阅[MAPI 应用程序开发](mapi-application-development.md)和[MAPI 服务提供商](mapi-service-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="af488-107">For more information, see [MAPI Application Development](mapi-application-development.md) and [MAPI Service Providers](mapi-service-providers.md).</span></span>
    
- <span data-ttu-id="af488-108">具有其传输提供程序为 MAPI DLL 公开其[XPProviderInit](xpproviderinit.md)初始化函数。</span><span class="sxs-lookup"><span data-stu-id="af488-108">Have its transport provider DLL expose to MAPI its [XPProviderInit](xpproviderinit.md) initialization function.</span></span> 
    
- <span data-ttu-id="af488-109">为 MAPI 公开其实现[IXPProvider: IUnknown](ixpprovideriunknown.md)和[IXPLogon: IUnknown](ixplogoniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="af488-109">Expose to MAPI its implementation of the [IXPProvider : IUnknown](ixpprovideriunknown.md) and [IXPLogon : IUnknown](ixplogoniunknown.md) interfaces.</span></span> 
    
- <span data-ttu-id="af488-110">MAPI 和客户端应用程序公开其实现[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="af488-110">Expose to MAPI and client applications its implementation of the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface.</span></span> <span data-ttu-id="af488-111">有关实现**IMAPIStatus**的详细信息，请参阅[状态对象实现](status-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="af488-111">For more information about implementing **IMAPIStatus**, see [Status Object Implementation](status-object-implementation.md).</span></span> 
    
- <span data-ttu-id="af488-112">实现属性表对话框进行配置。</span><span class="sxs-lookup"><span data-stu-id="af488-112">Implement a property sheet dialog box for configuration.</span></span> <span data-ttu-id="af488-113">有关实现属性表的详细信息，请参阅[属性表实现](property-sheet-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="af488-113">For more information about implementing property sheets, see [Property Sheet Implementation](property-sheet-implementation.md).</span></span>
    

