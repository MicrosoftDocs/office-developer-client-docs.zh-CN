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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 64fcbebbd71bc3f478f36c711e49db9a3518ef9a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435017"
---
# <a name="hresult"></a><span data-ttu-id="6960b-103">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6960b-103">HRESULT</span></span>

  
  
<span data-ttu-id="6960b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6960b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6960b-105">用于描述错误或警告的 32 位值。</span><span class="sxs-lookup"><span data-stu-id="6960b-105">A 32-bit value that is used to describe an error or warning.</span></span>
  
```cpp
typedef LONG HRESULT;
```

## <a name="remarks"></a><span data-ttu-id="6960b-106">备注</span><span class="sxs-lookup"><span data-stu-id="6960b-106">Remarks</span></span>

<span data-ttu-id="6960b-107">**HRESULT** 数据类型与 [SCODE](scode.md)代码数据类型。</span><span class="sxs-lookup"><span data-stu-id="6960b-107">The **HRESULT** data type is the same as the [SCODE](scode.md) data type.</span></span> 
  
<span data-ttu-id="6960b-108">**HRESULT** 值由以下字段组成：</span><span class="sxs-lookup"><span data-stu-id="6960b-108">An **HRESULT** value consists of the following fields:</span></span> 
  
- <span data-ttu-id="6960b-109">指示严重性的 1 位代码，其中 0 表示成功，1 表示失败。</span><span class="sxs-lookup"><span data-stu-id="6960b-109">A 1-bit code indicating severity, where zero represents success and 1 represents failure.</span></span>
    
- <span data-ttu-id="6960b-110">4 位保留值。</span><span class="sxs-lookup"><span data-stu-id="6960b-110">A 4-bit reserved value.</span></span>
    
- <span data-ttu-id="6960b-111">指示错误或警告责任的 11 位代码，也称为设备代码。</span><span class="sxs-lookup"><span data-stu-id="6960b-111">An 11-bit code indicating responsibility for the error or warning, also known as a facility code.</span></span>
    
- <span data-ttu-id="6960b-112">描述错误或警告的 16 位代码。</span><span class="sxs-lookup"><span data-stu-id="6960b-112">A 16-bit code describing the error or warning.</span></span>
    
<span data-ttu-id="6960b-113">大多数 MAPI 接口方法和函数都返回 **HRESULT** 值以提供详细的原因形成。</span><span class="sxs-lookup"><span data-stu-id="6960b-113">Most MAPI interface methods and functions return **HRESULT** values to provide detailed cause formation.</span></span> <span data-ttu-id="6960b-114">**HRESULT** 值也广泛使用在 OLE 接口方法中。</span><span class="sxs-lookup"><span data-stu-id="6960b-114">**HRESULT** values are also used widely in OLE interface methods.</span></span> <span data-ttu-id="6960b-115">OLE 提供了多个宏，用于在 **HRESULT** 值和 **SCODE** 值之间转换，这是另一种数据类型错误处理的常用方法。</span><span class="sxs-lookup"><span data-stu-id="6960b-115">OLE provides several macros for converting between **HRESULT** values and **SCODE** values, another common data type for error handling.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6960b-116">在 64 位 MAPI 中 **，HRESULT** 仍是 32 位值。</span><span class="sxs-lookup"><span data-stu-id="6960b-116">In 64-bit MAPI, **HRESULT** is still a 32-bit value.</span></span> 
  
<span data-ttu-id="6960b-117">有关 OLE 使用 **HRESULT** 值的信息，请参阅 *《OLE 程序员参考》。*</span><span class="sxs-lookup"><span data-stu-id="6960b-117">For information about the OLE use of **HRESULT** values, see the  *OLE Programmer's Reference*  .</span></span> <span data-ttu-id="6960b-118">有关在 MAPI 中使用这些值的详细信息，请参阅 [错误处理](error-handling-in-mapi.md) 和以下任一接口方法：</span><span class="sxs-lookup"><span data-stu-id="6960b-118">For more information about the use of these values in MAPI, see [Error Handling](error-handling-in-mapi.md) and any of the following interface methods:</span></span> 
  
[<span data-ttu-id="6960b-119">IABLogon::GetLastError</span><span class="sxs-lookup"><span data-stu-id="6960b-119">IABLogon::GetLastError</span></span>](iablogon-getlasterror.md)
  
[<span data-ttu-id="6960b-120">IMAPISupport::GetLastError</span><span class="sxs-lookup"><span data-stu-id="6960b-120">IMAPISupport::GetLastError</span></span>](imapisupport-getlasterror.md)
  
[<span data-ttu-id="6960b-121">IMAPIControl::GetLastError</span><span class="sxs-lookup"><span data-stu-id="6960b-121">IMAPIControl::GetLastError</span></span>](imapicontrol-getlasterror.md)
  
[<span data-ttu-id="6960b-122">IMAPITable::GetLastError</span><span class="sxs-lookup"><span data-stu-id="6960b-122">IMAPITable::GetLastError</span></span>](imapitable-getlasterror.md)
  
[<span data-ttu-id="6960b-123">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="6960b-123">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="6960b-124">IMAPIViewAdviseSink::OnPrint</span><span class="sxs-lookup"><span data-stu-id="6960b-124">IMAPIViewAdviseSink::OnPrint</span></span>](imapiviewadvisesink-onprint.md)
  
## <a name="see-also"></a><span data-ttu-id="6960b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6960b-125">See also</span></span>



[<span data-ttu-id="6960b-126">SCODE</span><span class="sxs-lookup"><span data-stu-id="6960b-126">SCODE</span></span>](scode.md)


[<span data-ttu-id="6960b-127">MAPI 数据类型</span><span class="sxs-lookup"><span data-stu-id="6960b-127">MAPI Data Types</span></span>](mapi-data-types.md)

