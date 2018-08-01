---
title: 处理 Unicode 列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2cd55464-263f-4f83-b874-524271773934
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9f1fd2d4e4bfdc9ccbbb771fedf1141769c8c8ca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779090"
---
# <a name="working-with-unicode-columns"></a><span data-ttu-id="96786-103">处理 Unicode 列</span><span class="sxs-lookup"><span data-stu-id="96786-103">Working with Unicode Columns</span></span>

  
  
<span data-ttu-id="96786-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="96786-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="96786-105">可以使用标准的 8 位字符，这些属性类型 PT_STRING8 或 16 位 Unicode 字符，它们是属性类型 PT_UNICODE 表示表中的字符串。</span><span class="sxs-lookup"><span data-stu-id="96786-105">Character strings in tables can be represented using standard 8-bit characters, which are property type PT_STRING8, or 16-bit Unicode characters, which are property type PT_UNICODE.</span></span> <span data-ttu-id="96786-106">表实施可以自由选择其表支持 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="96786-106">Table implementers are free to choose whether or not their tables support Unicode strings.</span></span> <span data-ttu-id="96786-107">因为 Unicode 添加值为客户端和服务提供程序通过扩展的功能集，请尽可能支持 Unicode 建议。</span><span class="sxs-lookup"><span data-stu-id="96786-107">Because Unicode adds value for both clients and service providers by extending the feature set, supporting Unicode wherever possible is recommended.</span></span> 
  
<span data-ttu-id="96786-108">许多表方法接受一个指示应为 Unicode 字符串属性值的标志。</span><span class="sxs-lookup"><span data-stu-id="96786-108">Many table methods accept a flag that dictates whether or not string property values are expected to be Unicode.</span></span> <span data-ttu-id="96786-109">在输入 MAPI_UNICODE 标志指定表示表实施，传入呼叫的所有字符串属性值的 Unicode 字符串并且具有 PT_UNICODE 属性类型。</span><span class="sxs-lookup"><span data-stu-id="96786-109">On input, specifying the MAPI_UNICODE flag indicates to the table implementer that all string property values passed in with the call are Unicode strings and have property types of PT_UNICODE.</span></span> <span data-ttu-id="96786-110">输出，此标志指示返回的字符串的所有属性值应尽可能都为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="96786-110">On output, this flag indicates that all returned string property values should be Unicode strings, if possible.</span></span> <span data-ttu-id="96786-111">标志是否具有输入或输出的含义取决于的方法。</span><span class="sxs-lookup"><span data-stu-id="96786-111">Whether the flag has a meaning for input or output depends on the method.</span></span> <span data-ttu-id="96786-112">不支持 Unicode 和传递 MAPI_UNICODE 标志表实施返回 MAPI_E_BAD_CHAR_WIDTH 值。</span><span class="sxs-lookup"><span data-stu-id="96786-112">Table implementers that do not support Unicode and are passed the MAPI_UNICODE flag return the MAPI_E_BAD_CHAR_WIDTH value.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="96786-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96786-113">See also</span></span>



[<span data-ttu-id="96786-114">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="96786-114">MAPI Tables</span></span>](mapi-tables.md)

