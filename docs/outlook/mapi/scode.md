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
# <a name="scode"></a><span data-ttu-id="19640-103">SCODE</span><span class="sxs-lookup"><span data-stu-id="19640-103">SCODE</span></span>

<span data-ttu-id="19640-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="19640-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="19640-105">用于描述错误或警告的 32 位状态值。</span><span class="sxs-lookup"><span data-stu-id="19640-105">A 32-bit status value that is used to describe an error or warning.</span></span> 
  
```cpp
typedef ULONG SCODE;

```

## <a name="remarks"></a><span data-ttu-id="19640-106">备注</span><span class="sxs-lookup"><span data-stu-id="19640-106">Remarks</span></span>

<span data-ttu-id="19640-107">**SCODE** 数据类型与 [HRESULT](hresult.md)属性数据类型。</span><span class="sxs-lookup"><span data-stu-id="19640-107">The **SCODE** data type is the same as the [HRESULT](hresult.md) data type.</span></span> 
  
<span data-ttu-id="19640-108">**SCODE** 值分为四个字段：</span><span class="sxs-lookup"><span data-stu-id="19640-108">An **SCODE** value is divided into four fields:</span></span> 
  
- <span data-ttu-id="19640-109">单位严重性代码，设置为 0 表示成功，1 表示失败。</span><span class="sxs-lookup"><span data-stu-id="19640-109">A single-bit severity code which is set to 0 to indicate success and 1 to indicate failure.</span></span>
    
- <span data-ttu-id="19640-110">11 位保留字段</span><span class="sxs-lookup"><span data-stu-id="19640-110">An 11-bit reserved field</span></span>
    
- <span data-ttu-id="19640-111">指示负责错误或警告的区域的 4 位设备代码。</span><span class="sxs-lookup"><span data-stu-id="19640-111">A 4-bit facility code which indicates the area responsible for the error or warning.</span></span>
    
- <span data-ttu-id="19640-112">描述导致错误或警告的问题的 16 位错误或警告代码。</span><span class="sxs-lookup"><span data-stu-id="19640-112">A 16-bit error or warning code which describes the problem that is causing the error or warning.</span></span>
    
<span data-ttu-id="19640-113">许多 MAPI 函数和方法都返回定义为 **HRESULT** 数据类型的 **SCODE** 值，就像 OLE 方法和函数一样。</span><span class="sxs-lookup"><span data-stu-id="19640-113">Many of the MAPI functions and methods return **SCODE** values defined as **HRESULT** data types as do the OLE methods and functions.</span></span> <span data-ttu-id="19640-114">OLE 定义多个宏，这些宏可用于在 **SCODE 和** **HRESULT** 之间转换。</span><span class="sxs-lookup"><span data-stu-id="19640-114">OLE defines several macros that can be used to convert between an **SCODE** and an **HRESULT**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19640-115">在 64 位 MAPI 中 **，SCODE** 仍是 32 位值。</span><span class="sxs-lookup"><span data-stu-id="19640-115">In 64-bit MAPI, **SCODE** is still a 32-bit value.</span></span> 
  
<span data-ttu-id="19640-116">有关 MAPI 如何使用 **SCODE** 代码的详细信息数据类型，请参阅 [错误处理](error-handling-in-mapi.md)。</span><span class="sxs-lookup"><span data-stu-id="19640-116">For more information about how MAPI uses the **SCODE** data type, see [Error Handling](error-handling-in-mapi.md).</span></span> <span data-ttu-id="19640-117">有关 OLE 和 **SCODE** 数据类型，请参阅 *《OLE 程序员参考》。*</span><span class="sxs-lookup"><span data-stu-id="19640-117">For more information about OLE and the **SCODE** data type, see the  *OLE Programmer's Reference*  .</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="19640-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19640-118">See also</span></span>



<span data-ttu-id="19640-119">[[HRESULT]](hresult.md)</span><span class="sxs-lookup"><span data-stu-id="19640-119">[HRESULT](hresult.md)</span></span>


[<span data-ttu-id="19640-120">MAPI 数据类型</span><span class="sxs-lookup"><span data-stu-id="19640-120">MAPI Data Types</span></span>](mapi-data-types.md)

