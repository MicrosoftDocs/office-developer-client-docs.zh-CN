---
title: TCHAR
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
api_name:
- MAPI.TCHAR
api_type:
- COM
ms.assetid: 7a92060b-4c30-4eba-993f-36f5f9231a4b
description: 上次修改时间：2011 年 7 月 23 日
localization_priority: Priority
ms.openlocfilehash: 2b04ebe6d05cd72a59fe6d44c9138468fd7ddec1
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710445"
---
# <a name="tchar"></a><span data-ttu-id="4a2d6-103">TCHAR</span><span class="sxs-lookup"><span data-stu-id="4a2d6-103">TCHAR</span></span>

  
  
<span data-ttu-id="4a2d6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4a2d6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4a2d6-105">可用于描述 ANSI、DBCS 或 Unicode 字符串的 Win32 字符字符串。</span><span class="sxs-lookup"><span data-stu-id="4a2d6-105">A Win32 character string that can be used to describe ANSI, DBCS, or Unicode strings.</span></span> <span data-ttu-id="4a2d6-106">对于 ANSI 和 DBCS 平台，TCHAR 定义如下：</span><span class="sxs-lookup"><span data-stu-id="4a2d6-106">For ANSI and DBCS platforms, TCHAR is defined as follows:</span></span>
  
```cpp
typedef char TCHAR;

```

## <a name="remarks"></a><span data-ttu-id="4a2d6-107">备注</span><span class="sxs-lookup"><span data-stu-id="4a2d6-107">Remarks</span></span>

<span data-ttu-id="4a2d6-108">对于 Unicode 平台，TCHAR 定义为与 WCHAR 类型同义。</span><span class="sxs-lookup"><span data-stu-id="4a2d6-108">For Unicode platforms, TCHAR is defined as synonymous with the WCHAR type.</span></span> 
  
<span data-ttu-id="4a2d6-109">MAPI 客户端可以使用 TCHAR 数据类型来表示 WCHAR 或 Char 类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="4a2d6-109">MAPI clients can use the TCHAR data type to represent a string of either the WCHAR or char type.</span></span> <span data-ttu-id="4a2d6-110">请务必定义符号常量 UNICODE 并在需要时对平台执行限制。</span><span class="sxs-lookup"><span data-stu-id="4a2d6-110">Be sure to define the symbolic constant UNICODE and limit the platform when it is required.</span></span> <span data-ttu-id="4a2d6-111">MAPI 将转译平台信息并在内部将 TCHAR 转换为相应的字符串。</span><span class="sxs-lookup"><span data-stu-id="4a2d6-111">MAPI will interpret the platform information and internally translate TCHAR to the appropriate string.</span></span> <span data-ttu-id="4a2d6-112">MAPI 属性类型 PT_TSTRING 的工作方式与 TCHAR 数据类型的工作方式类似。</span><span class="sxs-lookup"><span data-stu-id="4a2d6-112">The MAPI property type, PT_TSTRING, works just like the TCHAR data type.</span></span> <span data-ttu-id="4a2d6-113">当平台支持 Unicode 时，将在编译时向类型 PT_TSTRING 的属性分配类型 PT_UNICODE。</span><span class="sxs-lookup"><span data-stu-id="4a2d6-113">When the platform supports Unicode, properties of type PT_TSTRING are assigned the type PT_UNICODE at compile time.</span></span> <span data-ttu-id="4a2d6-114">当平台不支持 Unicode 时，将向这些属性分配类型 PT_STRING8。</span><span class="sxs-lookup"><span data-stu-id="4a2d6-114">When the platform does not support Unicode, these properties are assigned the type PT_STRING8.</span></span>
  
<span data-ttu-id="4a2d6-115">有关此功能的详细信息，请参阅[字符集](mapi-character-sets.md)和[属性类型的列表](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="4a2d6-115">For more information about this functionality, see [Character Sets](mapi-character-sets.md) and [List of Property Types](property-types.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4a2d6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a2d6-116">See also</span></span>



[<span data-ttu-id="4a2d6-117">MAPI 数据类型</span><span class="sxs-lookup"><span data-stu-id="4a2d6-117">MAPI Data Types</span></span>](mapi-data-types.md)

