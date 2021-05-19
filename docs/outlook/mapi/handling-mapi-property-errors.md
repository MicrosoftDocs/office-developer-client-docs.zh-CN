---
title: 处理 MAPI 属性错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 23d68d8b-b0b6-4c32-8404-6acd23802db0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1dc676101d4c39544c9dd1fae94000db9963ea02
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419077"
---
# <a name="handling-mapi-property-errors"></a><span data-ttu-id="3b5fe-103">处理 MAPI 属性错误</span><span class="sxs-lookup"><span data-stu-id="3b5fe-103">Handling MAPI property errors</span></span>

<span data-ttu-id="3b5fe-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b5fe-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3b5fe-105">以下 **IMAPIProp** 方法报告部分成功，而不是完全失败或成功：</span><span class="sxs-lookup"><span data-stu-id="3b5fe-105">Instead of complete failure or success, the following **IMAPIProp** methods report partial success:</span></span> 
  
[<span data-ttu-id="3b5fe-106">GetProps</span><span class="sxs-lookup"><span data-stu-id="3b5fe-106">GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="3b5fe-107">SetProps</span><span class="sxs-lookup"><span data-stu-id="3b5fe-107">SetProps</span></span>](imapiprop-setprops.md)
  
[<span data-ttu-id="3b5fe-108">DeleteProps</span><span class="sxs-lookup"><span data-stu-id="3b5fe-108">DeleteProps</span></span>](imapiprop-deleteprops.md)
  
[<span data-ttu-id="3b5fe-109">CopyTo</span><span class="sxs-lookup"><span data-stu-id="3b5fe-109">CopyTo</span></span>](imapiprop-copyto.md)
  
[<span data-ttu-id="3b5fe-110">CopyProps</span><span class="sxs-lookup"><span data-stu-id="3b5fe-110">CopyProps</span></span>](imapiprop-copyprops.md)
  
<span data-ttu-id="3b5fe-111">**GetProps** 报告在可以检索对象的至少一个请求的属性时部分成功。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-111">**GetProps** reports partial success when it can retrieve at least one of the requested properties for an object.</span></span> <span data-ttu-id="3b5fe-112">**GetProps** 指示部分成功，方法为返回警告MAPI_W_ERRORS_RETURNED将有关不可用属性的信息放在 **lppPropArray** 参数指向的属性值数组中。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-112">**GetProps** indicates partial success by returning the warning MAPI_W_ERRORS_RETURNED and placing information about the unavailable properties in the property value array pointed to by the **lppPropArray** parameter.</span></span> <span data-ttu-id="3b5fe-113">此数组中不可用属性的条目包含 **PT_ERROR ulPropTag** 成员中的属性类型的值，MAPI_E_NOT_FOUND Value 成员的另一个相应 **错误** 值。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-113">An unavailable property's entry in this array contains PT_ERROR for the property type in the **ulPropTag** member and MAPI_E_NOT_FOUND or another appropriate error value for the **Value** member.</span></span> <span data-ttu-id="3b5fe-114">例如，如果客户端调用文件夹 **的 GetProps** 方法来检索三个属性，而第三个属性不可用，则邮件存储提供程序将 PT_ERROR 作为属性值数组的第三个属性类型，而将 MAPI_E_NOT_FOUND 第三个属性值。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-114">For example, if a client calls a folder's **GetProps** method to retrieve three properties and the third is unavailable, the message store provider places PT_ERROR in the third property type in the property value array and MAPI_E_NOT_FOUND in the third property value.</span></span> 
  
<span data-ttu-id="3b5fe-115">其他 **IMAPIProp 方法** 报告部分成功的方式有所不同。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-115">The other **IMAPIProp** methods report partial success differently.</span></span> <span data-ttu-id="3b5fe-116">这些方法通过返回错误值S_OK将错误信息置于 [SPropProblemArray](spropproblemarray.md) 结构中来报告部分成功。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-116">These methods report partial success by returning S_OK and placing error information in an [SPropProblemArray](spropproblemarray.md) structure.</span></span> <span data-ttu-id="3b5fe-117">与包含数据的 **GetProps** 中的属性值数组不同，无论该方法是成功还是失败，这些方法中的属性问题数组仅在存在错误且调用方已注册有兴趣了解错误时存在。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-117">Unlike the property value array in **GetProps** that contains data regardless of whether the method succeeded or failed, the property problem array in these methods exists only if there are errors and only if the caller has registered interest in learning about the errors.</span></span> <span data-ttu-id="3b5fe-118">调用方必须指定有效的 **SPropProblemArray** 指针以注册错误信息。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-118">Callers must specify a valid **SPropProblemArray** pointer to register for error information.</span></span> 
  
<span data-ttu-id="3b5fe-119">从 **SetProps、DeleteProps、CopyTo** 或 **CopyProps** 返回错误值时，这表示失败而不是部分成功。 </span><span class="sxs-lookup"><span data-stu-id="3b5fe-119">When an error value is returned from **SetProps**, **DeleteProps**, **CopyTo**, or **CopyProps**, this indicates failure instead of partial success.</span></span> <span data-ttu-id="3b5fe-120">属性问题数组（如果可用）无效。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-120">The property problem array, if available, is not valid.</span></span> <span data-ttu-id="3b5fe-121">客户端不应尝试访问结构中存储的数据，也不应尝试释放结构本身。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-121">Clients should not try to access data held in the structure nor should they try to free the structure itself.</span></span> <span data-ttu-id="3b5fe-122">相应的响应是调用 [IMAPIProp：：GetLastError](imapiprop-getlasterror.md)。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-122">The appropriate response is to call [IMAPIProp::GetLastError](imapiprop-getlasterror.md).</span></span> 
  
<span data-ttu-id="3b5fe-123">**GetLastError** 与 Windows SDK 中提供的相同名称的函数类似。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-123">**GetLastError** is similar to the function of the same name provided in the Windows SDK.</span></span> <span data-ttu-id="3b5fe-124">与返回值一样，二者都提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-124">Both provide more detailed information about an error than is available with the return value.</span></span> <span data-ttu-id="3b5fe-125">它们都返回有关之前发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-125">They both return information about the previous error that has occurred.</span></span> <span data-ttu-id="3b5fe-126">区别在于 Win32 **GetLastError** 函数报告调用线程生成的错误 **，IMAPIProp：：GetLastError** 方法报告当前对象生成的错误。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-126">The difference is that the Win32 **GetLastError** function reports on an error generated by the calling thread and the **IMAPIProp::GetLastError** method reports on an error generated by the current object.</span></span> <span data-ttu-id="3b5fe-127">也就是说，如果客户端对邮件调用 **DeleteProps** 并返回 MAPI_E_NO_ACCESS以指示邮件是只读的， **则 GetLastError** 将返回邮件提供的数据。</span><span class="sxs-lookup"><span data-stu-id="3b5fe-127">That is, if a client calls **DeleteProps** on a message and MAPI_E_NO_ACCESS is returned to indicate that the message is read-only, **GetLastError** returns data provided by the message.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3b5fe-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b5fe-128">See also</span></span>

- [<span data-ttu-id="3b5fe-129">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="3b5fe-129">MAPI Property Overview</span></span>](mapi-property-overview.md)

