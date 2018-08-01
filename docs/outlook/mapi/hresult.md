---
title: HRESULT
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
ms.assetid: b248ed11-3d8a-4d4c-9b84-fa5bee7979c7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5bacf3c73ba7f9a7720586c77ee520d289c40e11
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775151"
---
# <a name="hresult"></a><span data-ttu-id="45b78-103">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45b78-103">HRESULT</span></span>

  
  
<span data-ttu-id="45b78-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="45b78-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="45b78-105">一个 32 位值，用来描述错误或警告。</span><span class="sxs-lookup"><span data-stu-id="45b78-105">A 32-bit value that is used to describe an error or warning.</span></span>
  
```cpp
typedef LONG HRESULT;
```

## <a name="remarks"></a><span data-ttu-id="45b78-106">说明</span><span class="sxs-lookup"><span data-stu-id="45b78-106">Remarks</span></span>

<span data-ttu-id="45b78-107">[SCODE](scode.md)数据类型相同的**HRESULT**数据类型。</span><span class="sxs-lookup"><span data-stu-id="45b78-107">The **HRESULT** data type is the same as the [SCODE](scode.md) data type.</span></span> 
  
<span data-ttu-id="45b78-108">**HRESULT**值包含以下字段：</span><span class="sxs-lookup"><span data-stu-id="45b78-108">An **HRESULT** value consists of the following fields:</span></span> 
  
- <span data-ttu-id="45b78-109">指示严重级别 1 位代码，其中零表示成功，1 代表失败。</span><span class="sxs-lookup"><span data-stu-id="45b78-109">A 1-bit code indicating severity, where zero represents success and 1 represents failure.</span></span>
    
- <span data-ttu-id="45b78-110">4 位保留的值。</span><span class="sxs-lookup"><span data-stu-id="45b78-110">A 4-bit reserved value.</span></span>
    
- <span data-ttu-id="45b78-111">11 位代码，指示错误或警告，也称为设施代码的责任。</span><span class="sxs-lookup"><span data-stu-id="45b78-111">An 11-bit code indicating responsibility for the error or warning, also known as a facility code.</span></span>
    
- <span data-ttu-id="45b78-112">一个 16 位代码描述该错误或警告。</span><span class="sxs-lookup"><span data-stu-id="45b78-112">A 16-bit code describing the error or warning.</span></span>
    
<span data-ttu-id="45b78-113">大多数 MAPI 接口方法和函数返回可提供详细的原因构成的**HRESULT**值。</span><span class="sxs-lookup"><span data-stu-id="45b78-113">Most MAPI interface methods and functions return **HRESULT** values to provide detailed cause formation.</span></span> <span data-ttu-id="45b78-114">在 OLE 接口方法还广泛使用**HRESULT**值。</span><span class="sxs-lookup"><span data-stu-id="45b78-114">**HRESULT** values are also used widely in OLE interface methods.</span></span> <span data-ttu-id="45b78-115">OLE 提供几个宏的**HRESULT**值和**SCODE**值之间进行转换的错误处理其他常见的数据类型。</span><span class="sxs-lookup"><span data-stu-id="45b78-115">OLE provides several macros for converting between **HRESULT** values and **SCODE** values, another common data type for error handling.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="45b78-116">64 位 MAPI 中**HRESULT**仍是 32 位值之一。</span><span class="sxs-lookup"><span data-stu-id="45b78-116">In 64-bit MAPI, **HRESULT** is still a 32-bit value.</span></span> 
  
<span data-ttu-id="45b78-117">有关 OLE 使用的**HRESULT**值的信息，请参阅*OLE 程序员参考*。</span><span class="sxs-lookup"><span data-stu-id="45b78-117">For information about the OLE use of **HRESULT** values, see the  *OLE Programmer's Reference*  .</span></span> <span data-ttu-id="45b78-118">有关使用 MAPI 中的这些值的详细信息，请参阅[错误处理](error-handling-in-mapi.md)及任何以下接口方法：</span><span class="sxs-lookup"><span data-stu-id="45b78-118">For more information about the use of these values in MAPI, see [Error Handling](error-handling-in-mapi.md) and any of the following interface methods:</span></span> 
  
[<span data-ttu-id="45b78-119">IABLogon::GetLastError</span><span class="sxs-lookup"><span data-stu-id="45b78-119">IABLogon::GetLastError</span></span>](iablogon-getlasterror.md)
  
[<span data-ttu-id="45b78-120">IMAPISupport::GetLastError</span><span class="sxs-lookup"><span data-stu-id="45b78-120">IMAPISupport::GetLastError</span></span>](imapisupport-getlasterror.md)
  
[<span data-ttu-id="45b78-121">IMAPIControl::GetLastError</span><span class="sxs-lookup"><span data-stu-id="45b78-121">IMAPIControl::GetLastError</span></span>](imapicontrol-getlasterror.md)
  
[<span data-ttu-id="45b78-122">IMAPITable::GetLastError</span><span class="sxs-lookup"><span data-stu-id="45b78-122">IMAPITable::GetLastError</span></span>](imapitable-getlasterror.md)
  
[<span data-ttu-id="45b78-123">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="45b78-123">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="45b78-124">IMAPIViewAdviseSink::OnPrint</span><span class="sxs-lookup"><span data-stu-id="45b78-124">IMAPIViewAdviseSink::OnPrint</span></span>](imapiviewadvisesink-onprint.md)
  
## <a name="see-also"></a><span data-ttu-id="45b78-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45b78-125">See also</span></span>



[<span data-ttu-id="45b78-126">SCODE</span><span class="sxs-lookup"><span data-stu-id="45b78-126">SCODE</span></span>](scode.md)


[<span data-ttu-id="45b78-127">MAPI 数据类型</span><span class="sxs-lookup"><span data-stu-id="45b78-127">MAPI Data Types</span></span>](mapi-data-types.md)

