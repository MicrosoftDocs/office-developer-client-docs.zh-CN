---
title: TCHAR
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.TCHAR
api_type:
- COM
ms.assetid: 7a92060b-4c30-4eba-993f-36f5f9231a4b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 357ace3267f22d751a20a12c96f108ee2f8ae1e8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595200"
---
# <a name="tchar"></a><span data-ttu-id="c468e-103">TCHAR</span><span class="sxs-lookup"><span data-stu-id="c468e-103">TCHAR</span></span>

  
  
<span data-ttu-id="c468e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c468e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c468e-105">Win32 字符的字符串的可以用来描述 ANSI、 DBCS 或 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="c468e-105">A Win32 character string that can be used to describe ANSI, DBCS, or Unicode strings.</span></span> <span data-ttu-id="c468e-106">ANSI 和 DBCS 平台 TCHAR 定义，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c468e-106">For ANSI and DBCS platforms, TCHAR is defined as follows:</span></span>
  
```cpp
typedef char TCHAR;

```

## <a name="remarks"></a><span data-ttu-id="c468e-107">注解</span><span class="sxs-lookup"><span data-stu-id="c468e-107">Remarks</span></span>

<span data-ttu-id="c468e-108">对于 Unicode 平台，TCHAR 被定义为同义 WCHAR 类型。</span><span class="sxs-lookup"><span data-stu-id="c468e-108">For Unicode platforms, TCHAR is defined as synonymous with the WCHAR type.</span></span> 
  
<span data-ttu-id="c468e-109">MAPI 客户端可以使用 TCHAR 数据类型表示 WCHAR 或 char 类型字符串。</span><span class="sxs-lookup"><span data-stu-id="c468e-109">MAPI clients can use the TCHAR data type to represent a string of either the WCHAR or char type.</span></span> <span data-ttu-id="c468e-110">请务必定义符号常量 UNICODE 和需要时限制平台。</span><span class="sxs-lookup"><span data-stu-id="c468e-110">Be sure to define the symbolic constant UNICODE and limit the platform when it is required.</span></span> <span data-ttu-id="c468e-111">MAPI 将解释平台信息和内部到适当的字符串翻译 TCHAR。</span><span class="sxs-lookup"><span data-stu-id="c468e-111">MAPI will interpret the platform information and internally translate TCHAR to the appropriate string.</span></span> <span data-ttu-id="c468e-112">MAPI 属性类型，PT_TSTRING，适用于一样 TCHAR 数据类型。</span><span class="sxs-lookup"><span data-stu-id="c468e-112">The MAPI property type, PT_TSTRING, works just like the TCHAR data type.</span></span> <span data-ttu-id="c468e-113">当该平台支持 Unicode 时，PT_TSTRING 类型的属性分配类型 PT_UNICODE 编译时。</span><span class="sxs-lookup"><span data-stu-id="c468e-113">When the platform supports Unicode, properties of type PT_TSTRING are assigned the type PT_UNICODE at compile time.</span></span> <span data-ttu-id="c468e-114">当平台不支持 Unicode 时，这些属性分配 PT_STRING8 的类型。</span><span class="sxs-lookup"><span data-stu-id="c468e-114">When the platform does not support Unicode, these properties are assigned the type PT_STRING8.</span></span>
  
<span data-ttu-id="c468e-115">有关此功能的详细信息，请参阅[字符集](mapi-character-sets.md)和[列表的属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="c468e-115">For more information about this functionality, see [Character Sets](mapi-character-sets.md) and [List of Property Types](property-types.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c468e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c468e-116">See also</span></span>



[<span data-ttu-id="c468e-117">MAPI 数据类型</span><span class="sxs-lookup"><span data-stu-id="c468e-117">MAPI Data Types</span></span>](mapi-data-types.md)

