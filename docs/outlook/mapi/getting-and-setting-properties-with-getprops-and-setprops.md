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
ms.openlocfilehash: 5751dc8b06d40b9f07a39f05868c328d64c27762
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775045"
---
# <a name="getting-and-setting-properties-with-getprops-and-setprops"></a><span data-ttu-id="962d6-103">获取和设置与 GetProps SetProps 属性</span><span class="sxs-lookup"><span data-stu-id="962d6-103">Getting and setting properties with GetProps and SetProps</span></span>
 
<span data-ttu-id="962d6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="962d6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="962d6-105">只要有可能，尝试检索或使用[IMAPIProp::GetProps](imapiprop-getprops.md)和[IMAPIProp::SetProps](imapiprop-setprops.md)方法修改的属性。</span><span class="sxs-lookup"><span data-stu-id="962d6-105">Whenever possible, try to retrieve or modify a property with the [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPIProp::SetProps](imapiprop-setprops.md) methods.</span></span> <span data-ttu-id="962d6-106">除非您正在使用该属性是非常大，这些方法应已足够。</span><span class="sxs-lookup"><span data-stu-id="962d6-106">Unless the property you are working with is very large, these methods should be adequate.</span></span> <span data-ttu-id="962d6-107">其他替代方法是从读取或写入到[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)接口的流。</span><span class="sxs-lookup"><span data-stu-id="962d6-107">The other alternative is to read from or write to a stream with the [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx) interface.</span></span> <span data-ttu-id="962d6-108">流可以成功处理非常大的属性，但它们是更高版本耗尽资源，因为它们需要的 COM 库。</span><span class="sxs-lookup"><span data-stu-id="962d6-108">Streams can handle very large properties successfully, but they are a greater drain on resources because they require the COM libraries.</span></span> <span data-ttu-id="962d6-109">仅在您调用**IMAPIProp::GetProps**或**IMAPIProp::SetProps**失败后，请使用**IStream**接口。</span><span class="sxs-lookup"><span data-stu-id="962d6-109">Use the **IStream** interface only after your call to **IMAPIProp::GetProps** or **IMAPIProp::SetProps** fails.</span></span> 
  

