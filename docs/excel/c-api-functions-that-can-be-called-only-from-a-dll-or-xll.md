---
title: 只能从 DLL 或 XLL 调用的 C API 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- '[excel 2007] 的函数，从 dll 或 xll 调用的 c api'
localization_priority: Normal
ms.assetid: 87c9e75b-c364-4428-a169-010886313b85
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 7935d86d1c0a460bcbec85157429d99242a73620
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773643"
---
# <a name="c-api-functions-that-can-be-called-only-from-a-dll-or-xll"></a><span data-ttu-id="89f39-104">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="89f39-104">C API Functions That Can Be Called Only from a DLL or XLL</span></span>

<span data-ttu-id="89f39-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="89f39-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="89f39-106">C API 提供只能通过使用**Excel4**、 **Excel4v**、 **Excel12**或**Excel12v**函数 （或使用框架函数**Excel 间接这些函数之一调用的 15 Microsoft Excel 的回调函数**或**Excel12f**)。</span><span class="sxs-lookup"><span data-stu-id="89f39-106">The C API provides 15 Microsoft Excel callback functions that can only be called by using the **Excel4**, **Excel4v**, **Excel12**, or **Excel12v** functions (or by one of these functions indirectly using the Framework functions **Excel** or **Excel12f**).</span></span> <span data-ttu-id="89f39-107">这意味着它们可从 DLL 或 XLL 进行调用。</span><span class="sxs-lookup"><span data-stu-id="89f39-107">This means they can only be called from a DLL or XLL.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="89f39-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="89f39-108">In this section</span></span>

[<span data-ttu-id="89f39-109">xlAbort</span><span class="sxs-lookup"><span data-stu-id="89f39-109">xlAbort</span></span>](xlabort.md)
  
[<span data-ttu-id="89f39-110">xlAsyncReturn</span><span class="sxs-lookup"><span data-stu-id="89f39-110">xlAsyncReturn</span></span>](xlasyncreturn.md)
  
[<span data-ttu-id="89f39-111">xlCoerce</span><span class="sxs-lookup"><span data-stu-id="89f39-111">xlCoerce</span></span>](xlcoerce.md)
  
[<span data-ttu-id="89f39-112">xlDefineBinaryName</span><span class="sxs-lookup"><span data-stu-id="89f39-112">xlDefineBinaryName</span></span>](xldefinebinaryname.md)
  
[<span data-ttu-id="89f39-113">xlDisableXLMsgs</span><span class="sxs-lookup"><span data-stu-id="89f39-113">xlDisableXLMsgs</span></span>](xldisablexlmsgs.md)
  
[<span data-ttu-id="89f39-114">xlEnableXLMsgs</span><span class="sxs-lookup"><span data-stu-id="89f39-114">xlEnableXLMsgs</span></span>](xlenablexlmsgs.md)
  
[<span data-ttu-id="89f39-115">xlEventRegister</span><span class="sxs-lookup"><span data-stu-id="89f39-115">xlEventRegister</span></span>](xleventregister.md)
  
[<span data-ttu-id="89f39-116">xlFree</span><span class="sxs-lookup"><span data-stu-id="89f39-116">xlFree</span></span>](xlfree.md)
  
[<span data-ttu-id="89f39-117">xlGetBinaryName</span><span class="sxs-lookup"><span data-stu-id="89f39-117">xlGetBinaryName</span></span>](xlgetbinaryname.md)
  
[<span data-ttu-id="89f39-118">xlGetHwnd</span><span class="sxs-lookup"><span data-stu-id="89f39-118">xlGetHwnd</span></span>](xlgethwnd.md)
  
[<span data-ttu-id="89f39-119">xlGetInst</span><span class="sxs-lookup"><span data-stu-id="89f39-119">xlGetInst</span></span>](xlgetinst.md)
  
[<span data-ttu-id="89f39-120">xlGetInstPtr</span><span class="sxs-lookup"><span data-stu-id="89f39-120">xlGetInstPtr</span></span>](xlgetinstptr.md)
  
[<span data-ttu-id="89f39-121">xlGetName</span><span class="sxs-lookup"><span data-stu-id="89f39-121">xlGetName</span></span>](xlgetname.md)
  
[<span data-ttu-id="89f39-122">xlRunningOnCluster</span><span class="sxs-lookup"><span data-stu-id="89f39-122">xlRunningOnCluster</span></span>](xlrunningoncluster.md)
  
[<span data-ttu-id="89f39-123">xlSet</span><span class="sxs-lookup"><span data-stu-id="89f39-123">xlSet</span></span>](xlset.md)
  
[<span data-ttu-id="89f39-124">xlSheetId</span><span class="sxs-lookup"><span data-stu-id="89f39-124">xlSheetId</span></span>](xlsheetid.md)
  
[<span data-ttu-id="89f39-125">xlSheetNm</span><span class="sxs-lookup"><span data-stu-id="89f39-125">xlSheetNm</span></span>](xlsheetnm.md)
  
[<span data-ttu-id="89f39-126">xlStack</span><span class="sxs-lookup"><span data-stu-id="89f39-126">xlStack</span></span>](xlstack.md)
  
[<span data-ttu-id="89f39-127">xlUDF</span><span class="sxs-lookup"><span data-stu-id="89f39-127">xlUDF</span></span>](xludf.md)
  
## <a name="see-also"></a><span data-ttu-id="89f39-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89f39-128">See also</span></span>



[<span data-ttu-id="89f39-129">C API 回调函数 Excel4、Excel12</span><span class="sxs-lookup"><span data-stu-id="89f39-129">C API Callback Functions Excel4, Excel12</span></span>](c-api-callback-functions-excel4-excel12.md)

