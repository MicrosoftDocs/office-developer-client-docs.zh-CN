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
# <a name="working-with-unicode-columns"></a><span data-ttu-id="7e487-103">使用 Unicode 列</span><span class="sxs-lookup"><span data-stu-id="7e487-103">Working with Unicode Columns</span></span>

  
  
<span data-ttu-id="7e487-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7e487-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7e487-105">可以使用标准的8位字符 (即属性类型 PT_STRING8 或16位 Unicode 字符, 即属性类型 PT_UNICODE) 来表示表中的字符字符串。</span><span class="sxs-lookup"><span data-stu-id="7e487-105">Character strings in tables can be represented using standard 8-bit characters, which are property type PT_STRING8, or 16-bit Unicode characters, which are property type PT_UNICODE.</span></span> <span data-ttu-id="7e487-106">表实施者可以自由选择其表是否支持 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="7e487-106">Table implementers are free to choose whether or not their tables support Unicode strings.</span></span> <span data-ttu-id="7e487-107">由于 Unicode 通过扩展功能集为客户端和服务提供程序添加了值, 因此建议尽可能支持 unicode。</span><span class="sxs-lookup"><span data-stu-id="7e487-107">Because Unicode adds value for both clients and service providers by extending the feature set, supporting Unicode wherever possible is recommended.</span></span> 
  
<span data-ttu-id="7e487-108">许多表方法接受一个标志, 该标志指示字符串属性值是否应为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="7e487-108">Many table methods accept a flag that dictates whether or not string property values are expected to be Unicode.</span></span> <span data-ttu-id="7e487-109">在输入时, 指定 MAPI_UNICODE 标志将向表实施者指出, 与调用一起传递的所有字符串属性值都是 UNICODE 字符串, 并且属性类型为 PT_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="7e487-109">On input, specifying the MAPI_UNICODE flag indicates to the table implementer that all string property values passed in with the call are Unicode strings and have property types of PT_UNICODE.</span></span> <span data-ttu-id="7e487-110">在输出时, 此标志指示所有返回的字符串属性值都应为 Unicode 字符串 (如果可能)。</span><span class="sxs-lookup"><span data-stu-id="7e487-110">On output, this flag indicates that all returned string property values should be Unicode strings, if possible.</span></span> <span data-ttu-id="7e487-111">对于输入或输出, 该标志是否有意义取决于方法。</span><span class="sxs-lookup"><span data-stu-id="7e487-111">Whether the flag has a meaning for input or output depends on the method.</span></span> <span data-ttu-id="7e487-112">不支持 Unicode 并传递 MAPI_UNICODE 标志的表实施者将返回 MAPI_E_BAD_CHAR_WIDTH 值。</span><span class="sxs-lookup"><span data-stu-id="7e487-112">Table implementers that do not support Unicode and are passed the MAPI_UNICODE flag return the MAPI_E_BAD_CHAR_WIDTH value.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7e487-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e487-113">See also</span></span>



[<span data-ttu-id="7e487-114">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="7e487-114">MAPI Tables</span></span>](mapi-tables.md)

