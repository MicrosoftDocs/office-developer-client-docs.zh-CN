---
title: 只能从 DLL 或 XLL 调用的 C API 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- functions [excel 2007]， c api called from dll or xll
localization_priority: Normal
ms.assetid: 87c9e75b-c364-4428-a169-010886313b85
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e6d2d3c824c482e3726cdaefa869393002a80f44
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423116"
---
# <a name="c-api-functions-that-can-be-called-only-from-a-dll-or-xll"></a><span data-ttu-id="3a06e-104">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="3a06e-104">C API Functions That Can Be Called Only from a DLL or XLL</span></span>

<span data-ttu-id="3a06e-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3a06e-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="3a06e-106">C API 提供 15 Microsoft Excel 回调函数，这些回调函数只能使用 Excel4、Excel4v、Excel12 或 **Excel12v** 函数 (或这些函数之一间接使用 Framework 函数 Excel 或 **Excel12f**) 调用。  </span><span class="sxs-lookup"><span data-stu-id="3a06e-106">The C API provides 15 Microsoft Excel callback functions that can only be called by using the **Excel4**, **Excel4v**, **Excel12**, or **Excel12v** functions (or by one of these functions indirectly using the Framework functions **Excel** or **Excel12f**).</span></span> <span data-ttu-id="3a06e-107">这意味着只能从 DLL 或 XLL 调用它们。</span><span class="sxs-lookup"><span data-stu-id="3a06e-107">This means they can only be called from a DLL or XLL.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="3a06e-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="3a06e-108">In this section</span></span>

[<span data-ttu-id="3a06e-109">xlAbort</span><span class="sxs-lookup"><span data-stu-id="3a06e-109">xlAbort</span></span>](xlabort.md)
  
[<span data-ttu-id="3a06e-110">xlAsyncReturn</span><span class="sxs-lookup"><span data-stu-id="3a06e-110">xlAsyncReturn</span></span>](xlasyncreturn.md)
  
[<span data-ttu-id="3a06e-111">xlCoerce</span><span class="sxs-lookup"><span data-stu-id="3a06e-111">xlCoerce</span></span>](xlcoerce.md)
  
[<span data-ttu-id="3a06e-112">xlDefineBinaryName</span><span class="sxs-lookup"><span data-stu-id="3a06e-112">xlDefineBinaryName</span></span>](xldefinebinaryname.md)
  
[<span data-ttu-id="3a06e-113">xlDisableXLMsgs</span><span class="sxs-lookup"><span data-stu-id="3a06e-113">xlDisableXLMsgs</span></span>](xldisablexlmsgs.md)
  
[<span data-ttu-id="3a06e-114">xlEnableXLMsgs</span><span class="sxs-lookup"><span data-stu-id="3a06e-114">xlEnableXLMsgs</span></span>](xlenablexlmsgs.md)
  
[<span data-ttu-id="3a06e-115">xlEventRegister</span><span class="sxs-lookup"><span data-stu-id="3a06e-115">xlEventRegister</span></span>](xleventregister.md)
  
[<span data-ttu-id="3a06e-116">xlFree</span><span class="sxs-lookup"><span data-stu-id="3a06e-116">xlFree</span></span>](xlfree.md)
  
[<span data-ttu-id="3a06e-117">xlGetBinaryName</span><span class="sxs-lookup"><span data-stu-id="3a06e-117">xlGetBinaryName</span></span>](xlgetbinaryname.md)
  
[<span data-ttu-id="3a06e-118">xlGetHwnd</span><span class="sxs-lookup"><span data-stu-id="3a06e-118">xlGetHwnd</span></span>](xlgethwnd.md)
  
[<span data-ttu-id="3a06e-119">xlGetInst</span><span class="sxs-lookup"><span data-stu-id="3a06e-119">xlGetInst</span></span>](xlgetinst.md)
  
[<span data-ttu-id="3a06e-120">xlGetInstPtr</span><span class="sxs-lookup"><span data-stu-id="3a06e-120">xlGetInstPtr</span></span>](xlgetinstptr.md)
  
[<span data-ttu-id="3a06e-121">xlGetName</span><span class="sxs-lookup"><span data-stu-id="3a06e-121">xlGetName</span></span>](xlgetname.md)
  
[<span data-ttu-id="3a06e-122">xlRunningOnCluster</span><span class="sxs-lookup"><span data-stu-id="3a06e-122">xlRunningOnCluster</span></span>](xlrunningoncluster.md)
  
[<span data-ttu-id="3a06e-123">xlSet</span><span class="sxs-lookup"><span data-stu-id="3a06e-123">xlSet</span></span>](xlset.md)
  
[<span data-ttu-id="3a06e-124">xlSheetId</span><span class="sxs-lookup"><span data-stu-id="3a06e-124">xlSheetId</span></span>](xlsheetid.md)
  
[<span data-ttu-id="3a06e-125">xlSheetNm</span><span class="sxs-lookup"><span data-stu-id="3a06e-125">xlSheetNm</span></span>](xlsheetnm.md)
  
[<span data-ttu-id="3a06e-126">xlStack</span><span class="sxs-lookup"><span data-stu-id="3a06e-126">xlStack</span></span>](xlstack.md)
  
[<span data-ttu-id="3a06e-127">xlUDF</span><span class="sxs-lookup"><span data-stu-id="3a06e-127">xlUDF</span></span>](xludf.md)
  
## <a name="see-also"></a><span data-ttu-id="3a06e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a06e-128">See also</span></span>



[<span data-ttu-id="3a06e-129">C API 回调函数 Excel4、Excel12</span><span class="sxs-lookup"><span data-stu-id="3a06e-129">C API Callback Functions Excel4, Excel12</span></span>](c-api-callback-functions-excel4-excel12.md)

