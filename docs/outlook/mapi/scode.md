---
title: SCODE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HRESULT
api_type:
- COM
ms.assetid: 2348cce1-07c3-49ed-ae03-79e477d3c6c2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4208f51af44055b03c65b51c9b3d94e947dc9b68
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430131"
---
# <a name="scode"></a><span data-ttu-id="1e67f-103">SCODE</span><span class="sxs-lookup"><span data-stu-id="1e67f-103">SCODE</span></span>

<span data-ttu-id="1e67f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1e67f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1e67f-105">一个用于描述错误或警告的32位状态值。</span><span class="sxs-lookup"><span data-stu-id="1e67f-105">A 32-bit status value that is used to describe an error or warning.</span></span> 
  
```cpp
typedef ULONG SCODE;

```

## <a name="remarks"></a><span data-ttu-id="1e67f-106">说明</span><span class="sxs-lookup"><span data-stu-id="1e67f-106">Remarks</span></span>

<span data-ttu-id="1e67f-107">**SCODE**数据类型与[HRESULT](hresult.md)数据类型相同。</span><span class="sxs-lookup"><span data-stu-id="1e67f-107">The **SCODE** data type is the same as the [HRESULT](hresult.md) data type.</span></span> 
  
<span data-ttu-id="1e67f-108">**SCODE**值分为四个字段:</span><span class="sxs-lookup"><span data-stu-id="1e67f-108">An **SCODE** value is divided into four fields:</span></span> 
  
- <span data-ttu-id="1e67f-109">一个将设置为0以指示成功和1以指示失败的单一位严重性代码。</span><span class="sxs-lookup"><span data-stu-id="1e67f-109">A single-bit severity code which is set to 0 to indicate success and 1 to indicate failure.</span></span>
    
- <span data-ttu-id="1e67f-110">11位保留字段</span><span class="sxs-lookup"><span data-stu-id="1e67f-110">An 11-bit reserved field</span></span>
    
- <span data-ttu-id="1e67f-111">4位设施代码, 指示负责错误或警告的区域。</span><span class="sxs-lookup"><span data-stu-id="1e67f-111">A 4-bit facility code which indicates the area responsible for the error or warning.</span></span>
    
- <span data-ttu-id="1e67f-112">一个16位错误或警告代码, 用于描述导致错误或警告的问题。</span><span class="sxs-lookup"><span data-stu-id="1e67f-112">A 16-bit error or warning code which describes the problem that is causing the error or warning.</span></span>
    
<span data-ttu-id="1e67f-113">许多 MAPI 函数和方法返回的**SCODE**值定义为**HRESULT**数据类型, 就像 OLE 方法和函数一样。</span><span class="sxs-lookup"><span data-stu-id="1e67f-113">Many of the MAPI functions and methods return **SCODE** values defined as **HRESULT** data types as do the OLE methods and functions.</span></span> <span data-ttu-id="1e67f-114">OLE 定义了几个可用于在**SCODE**和**HRESULT**之间进行转换的宏。</span><span class="sxs-lookup"><span data-stu-id="1e67f-114">OLE defines several macros that can be used to convert between an **SCODE** and an **HRESULT**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e67f-115">在64位 MAPI 中, **SCODE**仍为32位值。</span><span class="sxs-lookup"><span data-stu-id="1e67f-115">In 64-bit MAPI, **SCODE** is still a 32-bit value.</span></span> 
  
<span data-ttu-id="1e67f-116">有关 MAPI 如何使用**SCODE**数据类型的详细信息, 请参阅[错误处理](error-handling-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="1e67f-116">For more information about how MAPI uses the **SCODE** data type, see [Error Handling](error-handling-in-mapi.md).</span></span> <span data-ttu-id="1e67f-117">有关 ole 和**SCODE**数据类型的详细信息, 请参阅*OLE 程序员参考*。</span><span class="sxs-lookup"><span data-stu-id="1e67f-117">For more information about OLE and the **SCODE** data type, see the  *OLE Programmer's Reference*  .</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1e67f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e67f-118">See also</span></span>



<span data-ttu-id="1e67f-119">[[HRESULT]](hresult.md)</span><span class="sxs-lookup"><span data-stu-id="1e67f-119">[HRESULT](hresult.md)</span></span>


[<span data-ttu-id="1e67f-120">MAPI 数据类型</span><span class="sxs-lookup"><span data-stu-id="1e67f-120">MAPI Data Types</span></span>](mapi-data-types.md)

