---
title: 获取和设置与 GetProps SetProps 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 309d2b3d-dc71-4222-b293-4bfc467b5429
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7d11f69c6da8560f5879ebc38498d852486bed8b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395005"
---
# <a name="getting-and-setting-properties-with-getprops-and-setprops"></a><span data-ttu-id="da9f9-103">获取和设置与 GetProps SetProps 属性</span><span class="sxs-lookup"><span data-stu-id="da9f9-103">Getting and setting properties with GetProps and SetProps</span></span>
 
<span data-ttu-id="da9f9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="da9f9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="da9f9-105">只要有可能，尝试检索或使用[IMAPIProp::GetProps](imapiprop-getprops.md)和[IMAPIProp::SetProps](imapiprop-setprops.md)方法修改的属性。</span><span class="sxs-lookup"><span data-stu-id="da9f9-105">Whenever possible, try to retrieve or modify a property with the [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPIProp::SetProps](imapiprop-setprops.md) methods.</span></span> <span data-ttu-id="da9f9-106">除非您正在使用该属性是非常大，这些方法应已足够。</span><span class="sxs-lookup"><span data-stu-id="da9f9-106">Unless the property you are working with is very large, these methods should be adequate.</span></span> <span data-ttu-id="da9f9-107">其他替代方法是从读取或写入到[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口的流。</span><span class="sxs-lookup"><span data-stu-id="da9f9-107">The other alternative is to read from or write to a stream with the [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface.</span></span> <span data-ttu-id="da9f9-108">流可以成功处理非常大的属性，但它们是更高版本耗尽资源，因为它们需要的 COM 库。</span><span class="sxs-lookup"><span data-stu-id="da9f9-108">Streams can handle very large properties successfully, but they are a greater drain on resources because they require the COM libraries.</span></span> <span data-ttu-id="da9f9-109">仅在您调用**IMAPIProp::GetProps**或**IMAPIProp::SetProps**失败后，请使用**IStream**接口。</span><span class="sxs-lookup"><span data-stu-id="da9f9-109">Use the **IStream** interface only after your call to **IMAPIProp::GetProps** or **IMAPIProp::SetProps** fails.</span></span> 
  

