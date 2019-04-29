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
# <a name="hresult"></a><span data-ttu-id="78560-103">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78560-103">HRESULT</span></span>

  
  
<span data-ttu-id="78560-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="78560-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="78560-105">一个用于描述错误或警告的32位值。</span><span class="sxs-lookup"><span data-stu-id="78560-105">A 32-bit value that is used to describe an error or warning.</span></span>
  
```cpp
typedef LONG HRESULT;
```

## <a name="remarks"></a><span data-ttu-id="78560-106">说明</span><span class="sxs-lookup"><span data-stu-id="78560-106">Remarks</span></span>

<span data-ttu-id="78560-107">**HRESULT**数据类型与[SCODE](scode.md)数据类型相同。</span><span class="sxs-lookup"><span data-stu-id="78560-107">The **HRESULT** data type is the same as the [SCODE](scode.md) data type.</span></span> 
  
<span data-ttu-id="78560-108">**HRESULT**值包含以下字段:</span><span class="sxs-lookup"><span data-stu-id="78560-108">An **HRESULT** value consists of the following fields:</span></span> 
  
- <span data-ttu-id="78560-109">表示严重度的1位代码, 其中0表示成功, 1 表示失败。</span><span class="sxs-lookup"><span data-stu-id="78560-109">A 1-bit code indicating severity, where zero represents success and 1 represents failure.</span></span>
    
- <span data-ttu-id="78560-110">一个4位保留值。</span><span class="sxs-lookup"><span data-stu-id="78560-110">A 4-bit reserved value.</span></span>
    
- <span data-ttu-id="78560-111">11位代码, 用于指示对错误或警告 (也称为设施代码) 的责任。</span><span class="sxs-lookup"><span data-stu-id="78560-111">An 11-bit code indicating responsibility for the error or warning, also known as a facility code.</span></span>
    
- <span data-ttu-id="78560-112">一个用于描述错误或警告的16位代码。</span><span class="sxs-lookup"><span data-stu-id="78560-112">A 16-bit code describing the error or warning.</span></span>
    
<span data-ttu-id="78560-113">大多数 MAPI 接口方法和函数返回**HRESULT**值, 以提供详细的原因构成。</span><span class="sxs-lookup"><span data-stu-id="78560-113">Most MAPI interface methods and functions return **HRESULT** values to provide detailed cause formation.</span></span> <span data-ttu-id="78560-114">**HRESULT**值也在 OLE 接口方法中广泛使用。</span><span class="sxs-lookup"><span data-stu-id="78560-114">**HRESULT** values are also used widely in OLE interface methods.</span></span> <span data-ttu-id="78560-115">OLE 提供了几个用于在**HRESULT**值和**SCODE**值之间进行转换的宏, 这是用于错误处理的另一种常见数据类型。</span><span class="sxs-lookup"><span data-stu-id="78560-115">OLE provides several macros for converting between **HRESULT** values and **SCODE** values, another common data type for error handling.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="78560-116">在64位 MAPI 中, **HRESULT**仍为32位值。</span><span class="sxs-lookup"><span data-stu-id="78560-116">In 64-bit MAPI, **HRESULT** is still a 32-bit value.</span></span> 
  
<span data-ttu-id="78560-117">若要了解有关**HRESULT**值的 OLE 用法的信息, 请参阅*ole 程序员参考*。</span><span class="sxs-lookup"><span data-stu-id="78560-117">For information about the OLE use of **HRESULT** values, see the  *OLE Programmer's Reference*  .</span></span> <span data-ttu-id="78560-118">有关在 MAPI 中使用这些值的详细信息, 请参阅[错误处理](error-handling-in-mapi.md)和以下任何接口方法:</span><span class="sxs-lookup"><span data-stu-id="78560-118">For more information about the use of these values in MAPI, see [Error Handling](error-handling-in-mapi.md) and any of the following interface methods:</span></span> 
  
[<span data-ttu-id="78560-119">IABLogon::GetLastError</span><span class="sxs-lookup"><span data-stu-id="78560-119">IABLogon::GetLastError</span></span>](iablogon-getlasterror.md)
  
[<span data-ttu-id="78560-120">IMAPISupport::GetLastError</span><span class="sxs-lookup"><span data-stu-id="78560-120">IMAPISupport::GetLastError</span></span>](imapisupport-getlasterror.md)
  
[<span data-ttu-id="78560-121">IMAPIControl::GetLastError</span><span class="sxs-lookup"><span data-stu-id="78560-121">IMAPIControl::GetLastError</span></span>](imapicontrol-getlasterror.md)
  
[<span data-ttu-id="78560-122">IMAPITable::GetLastError</span><span class="sxs-lookup"><span data-stu-id="78560-122">IMAPITable::GetLastError</span></span>](imapitable-getlasterror.md)
  
[<span data-ttu-id="78560-123">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="78560-123">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="78560-124">IMAPIViewAdviseSink::OnPrint</span><span class="sxs-lookup"><span data-stu-id="78560-124">IMAPIViewAdviseSink::OnPrint</span></span>](imapiviewadvisesink-onprint.md)
  
## <a name="see-also"></a><span data-ttu-id="78560-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78560-125">See also</span></span>



[<span data-ttu-id="78560-126">SCODE</span><span class="sxs-lookup"><span data-stu-id="78560-126">SCODE</span></span>](scode.md)


[<span data-ttu-id="78560-127">MAPI 数据类型</span><span class="sxs-lookup"><span data-stu-id="78560-127">MAPI Data Types</span></span>](mapi-data-types.md)

