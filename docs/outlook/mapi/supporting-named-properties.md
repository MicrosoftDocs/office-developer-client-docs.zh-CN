---
title: 支持命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2e742ecd-2dcd-46a8-9d4e-2cec2c6f795e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 27625e913f06e858295351ed62de840ae7789915
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349628"
---
# <a name="supporting-named-properties"></a><span data-ttu-id="f2a76-103">支持命名属性</span><span class="sxs-lookup"><span data-stu-id="f2a76-103">Supporting Named Properties</span></span>

  
  
<span data-ttu-id="f2a76-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f2a76-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f2a76-105">实现 [IMAPIProp: IUnknown](imapipropiunknown.md) 界面的任何对象可支持命名属性。</span><span class="sxs-lookup"><span data-stu-id="f2a76-105">Any object that implements the [IMAPIProp : IUnknown](imapipropiunknown.md) interface can support named properties.</span></span> <span data-ttu-id="f2a76-106">对命名属性的支持是必需的:</span><span class="sxs-lookup"><span data-stu-id="f2a76-106">Support for named properties is required for:</span></span> 
  
- <span data-ttu-id="f2a76-107">允许将其他提供程序中的条目复制到其容器中的通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="f2a76-107">Address book providers that allow entries from other providers to be copied into their containers.</span></span>
    
- <span data-ttu-id="f2a76-108">可用于创建任意邮件类型的邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="f2a76-108">Message store providers that can be used to create arbitrary message types.</span></span>
    
<span data-ttu-id="f2a76-109">命名属性支持对于所有其他服务提供程序都是可选的。</span><span class="sxs-lookup"><span data-stu-id="f2a76-109">Named property support is optional for all other service providers.</span></span> <span data-ttu-id="f2a76-110">支持命名属性的服务提供程序必须在[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)和[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法中实现名称到标识符的映射。</span><span class="sxs-lookup"><span data-stu-id="f2a76-110">Service providers that do support named properties must implement name-to-identifier mapping in the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) and [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) methods.</span></span> <span data-ttu-id="f2a76-111">客户端调用**GetNamesFromIDs**以检索 over 0x8000 范围和**GetIDsFromNames**中的一个或多个属性标识符对应的名称, 以创建或检索一个或多个名称的标识符。</span><span class="sxs-lookup"><span data-stu-id="f2a76-111">Clients call **GetNamesFromIDs** to retrieve the corresponding names for one or more property identifiers in the over 0x8000 range and **GetIDsFromNames** to either create or retrieve the identifiers for one or more names.</span></span> 
  
<span data-ttu-id="f2a76-112">不支持命名属性的服务提供程序必须:</span><span class="sxs-lookup"><span data-stu-id="f2a76-112">Service providers that do not support named properties must:</span></span>
  
- <span data-ttu-id="f2a76-113">通过在[SPropProblem](spropproblem.md)数组中返回 MAPI_E_UNEXPECTED_ID, 对[IMAPIProp:: SetProps](imapiprop-setprops.md)的调用失败, 以设置具有0x8000 或更高的标识符的属性。</span><span class="sxs-lookup"><span data-stu-id="f2a76-113">Fail calls to [IMAPIProp::SetProps](imapiprop-setprops.md) to set properties with identifiers of 0x8000 or greater by returning MAPI_E_UNEXPECTED_ID in the [SPropProblem](spropproblem.md) array.</span></span> 
    
- <span data-ttu-id="f2a76-114">从[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)和[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="f2a76-114">Return MAPI_E_NO_SUPPORT from the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) and [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) methods .</span></span> 
    

