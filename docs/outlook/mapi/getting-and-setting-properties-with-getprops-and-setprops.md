---
title: 使用 GetProps 和 SetProps 获取并设置属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 309d2b3d-dc71-4222-b293-4bfc467b5429
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7d11f69c6da8560f5879ebc38498d852486bed8b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299396"
---
# <a name="getting-and-setting-properties-with-getprops-and-setprops"></a><span data-ttu-id="d0ab5-103">使用 GetProps 和 SetProps 获取并设置属性</span><span class="sxs-lookup"><span data-stu-id="d0ab5-103">Getting and setting properties with GetProps and SetProps</span></span>
 
<span data-ttu-id="d0ab5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d0ab5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d0ab5-105">只要有可能, 请尝试使用[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPIProp:: SetProps](imapiprop-setprops.md)方法检索或修改属性。</span><span class="sxs-lookup"><span data-stu-id="d0ab5-105">Whenever possible, try to retrieve or modify a property with the [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPIProp::SetProps](imapiprop-setprops.md) methods.</span></span> <span data-ttu-id="d0ab5-106">除非您使用的属性非常大, 否则这些方法应足够。</span><span class="sxs-lookup"><span data-stu-id="d0ab5-106">Unless the property you are working with is very large, these methods should be adequate.</span></span> <span data-ttu-id="d0ab5-107">另一种方法是使用[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口对流进行读取或写入。</span><span class="sxs-lookup"><span data-stu-id="d0ab5-107">The other alternative is to read from or write to a stream with the [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface.</span></span> <span data-ttu-id="d0ab5-108">流可以成功处理非常大的属性, 但由于它们需要 COM 库, 因此它们会更大的消耗资源。</span><span class="sxs-lookup"><span data-stu-id="d0ab5-108">Streams can handle very large properties successfully, but they are a greater drain on resources because they require the COM libraries.</span></span> <span data-ttu-id="d0ab5-109">仅在调用**IMAPIProp:: GetProps**或**IMAPIProp:: SetProps**失败之后, 才使用**IStream**接口。</span><span class="sxs-lookup"><span data-stu-id="d0ab5-109">Use the **IStream** interface only after your call to **IMAPIProp::GetProps** or **IMAPIProp::SetProps** fails.</span></span> 
  

