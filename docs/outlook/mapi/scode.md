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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6cd9dfe8fabd1ae7a4389550c628fb7ceff09ea8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778696"
---
# <a name="scode"></a><span data-ttu-id="aaedf-103">SCODE</span><span class="sxs-lookup"><span data-stu-id="aaedf-103">SCODE</span></span>

<span data-ttu-id="aaedf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="aaedf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="aaedf-105">一个 32 位状态值，用来描述错误或警告。</span><span class="sxs-lookup"><span data-stu-id="aaedf-105">A 32-bit status value that is used to describe an error or warning.</span></span> 
  
```cpp
typedef ULONG SCODE;

```

## <a name="remarks"></a><span data-ttu-id="aaedf-106">说明</span><span class="sxs-lookup"><span data-stu-id="aaedf-106">Remarks</span></span>

<span data-ttu-id="aaedf-107">**SCODE**数据类型是[HRESULT](hresult.md)的数据类型相同。</span><span class="sxs-lookup"><span data-stu-id="aaedf-107">The **SCODE** data type is the same as the [HRESULT](hresult.md) data type.</span></span> 
  
<span data-ttu-id="aaedf-108">**SCODE**值分为四个字段：</span><span class="sxs-lookup"><span data-stu-id="aaedf-108">An **SCODE** value is divided into four fields:</span></span> 
  
- <span data-ttu-id="aaedf-109">一位严重性代码都设置为 0 以指示成功，1，以指示故障。</span><span class="sxs-lookup"><span data-stu-id="aaedf-109">A single-bit severity code which is set to 0 to indicate success and 1 to indicate failure.</span></span>
    
- <span data-ttu-id="aaedf-110">11 位保留的字段</span><span class="sxs-lookup"><span data-stu-id="aaedf-110">An 11-bit reserved field</span></span>
    
- <span data-ttu-id="aaedf-111">4 位设施代码指示负责错误或警告的区域。</span><span class="sxs-lookup"><span data-stu-id="aaedf-111">A 4-bit facility code which indicates the area responsible for the error or warning.</span></span>
    
- <span data-ttu-id="aaedf-112">一个 16 位错误或警告代码，其中介绍了将导致错误或警告的问题。</span><span class="sxs-lookup"><span data-stu-id="aaedf-112">A 16-bit error or warning code which describes the problem that is causing the error or warning.</span></span>
    
<span data-ttu-id="aaedf-113">许多 MAPI 函数和方法返回**SCODE**值定义为**HRESULT**数据类型，如执行 OLE 方法和函数。</span><span class="sxs-lookup"><span data-stu-id="aaedf-113">Many of the MAPI functions and methods return **SCODE** values defined as **HRESULT** data types as do the OLE methods and functions.</span></span> <span data-ttu-id="aaedf-114">OLE 定义几个可用于**SCODE**和**HRESULT**之间转换的宏。</span><span class="sxs-lookup"><span data-stu-id="aaedf-114">OLE defines several macros that can be used to convert between an **SCODE** and an **HRESULT**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aaedf-115">64 位 MAPI 中**SCODE**仍是 32 位值之一。</span><span class="sxs-lookup"><span data-stu-id="aaedf-115">In 64-bit MAPI, **SCODE** is still a 32-bit value.</span></span> 
  
<span data-ttu-id="aaedf-116">有关如何 MAPI 使用**SCODE**数据类型的详细信息，请参阅[错误处理](error-handling-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="aaedf-116">For more information about how MAPI uses the **SCODE** data type, see [Error Handling](error-handling-in-mapi.md).</span></span> <span data-ttu-id="aaedf-117">有关 OLE 和**SCODE**数据类型的详细信息，请参阅*OLE 程序员参考*。</span><span class="sxs-lookup"><span data-stu-id="aaedf-117">For more information about OLE and the **SCODE** data type, see the  *OLE Programmer's Reference*  .</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="aaedf-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aaedf-118">See also</span></span>



<span data-ttu-id="aaedf-119">[[HRESULT]](hresult.md)</span><span class="sxs-lookup"><span data-stu-id="aaedf-119">[HRESULT](hresult.md)</span></span>


[<span data-ttu-id="aaedf-120">MAPI 数据类型</span><span class="sxs-lookup"><span data-stu-id="aaedf-120">MAPI Data Types</span></span>](mapi-data-types.md)

