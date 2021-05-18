---
title: 使用 Unicode 列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2cd55464-263f-4f83-b874-524271773934
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 76d1afb750dc81b889ca8e5eb3639145c061bfc2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408381"
---
# <a name="working-with-unicode-columns"></a><span data-ttu-id="faa15-103">使用 Unicode 列</span><span class="sxs-lookup"><span data-stu-id="faa15-103">Working with Unicode Columns</span></span>

  
  
<span data-ttu-id="faa15-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="faa15-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="faa15-105">可以使用标准 8 位字符（属性类型 PT_STRING8）或 16 位 Unicode 字符（属性类型为 PT_UNICODE）来表示表中的字符串。</span><span class="sxs-lookup"><span data-stu-id="faa15-105">Character strings in tables can be represented using standard 8-bit characters, which are property type PT_STRING8, or 16-bit Unicode characters, which are property type PT_UNICODE.</span></span> <span data-ttu-id="faa15-106">表实施者可以选择其表是否支持 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="faa15-106">Table implementers are free to choose whether or not their tables support Unicode strings.</span></span> <span data-ttu-id="faa15-107">由于 Unicode 通过扩展功能集为客户端和服务提供商增加了价值，因此建议尽可能支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="faa15-107">Because Unicode adds value for both clients and service providers by extending the feature set, supporting Unicode wherever possible is recommended.</span></span> 
  
<span data-ttu-id="faa15-108">许多表方法接受一个标志，指示字符串属性值预期是否是 Unicode。</span><span class="sxs-lookup"><span data-stu-id="faa15-108">Many table methods accept a flag that dictates whether or not string property values are expected to be Unicode.</span></span> <span data-ttu-id="faa15-109">在输入时，指定 MAPI_UNICODE 标志将指示表实现程序，调用传入的所有字符串属性值都是 Unicode 字符串，并且其属性类型为 PT_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="faa15-109">On input, specifying the MAPI_UNICODE flag indicates to the table implementer that all string property values passed in with the call are Unicode strings and have property types of PT_UNICODE.</span></span> <span data-ttu-id="faa15-110">在输出时，此标志指示所有返回的字符串属性值应为 Unicode 字符串（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="faa15-110">On output, this flag indicates that all returned string property values should be Unicode strings, if possible.</span></span> <span data-ttu-id="faa15-111">标志是否具有输入或输出的含义取决于 方法。</span><span class="sxs-lookup"><span data-stu-id="faa15-111">Whether the flag has a meaning for input or output depends on the method.</span></span> <span data-ttu-id="faa15-112">不支持 Unicode 且传递给 MAPI_UNICODE 的表实现器将返回MAPI_E_BAD_CHAR_WIDTH值。</span><span class="sxs-lookup"><span data-stu-id="faa15-112">Table implementers that do not support Unicode and are passed the MAPI_UNICODE flag return the MAPI_E_BAD_CHAR_WIDTH value.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="faa15-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="faa15-113">See also</span></span>



[<span data-ttu-id="faa15-114">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="faa15-114">MAPI Tables</span></span>](mapi-tables.md)

