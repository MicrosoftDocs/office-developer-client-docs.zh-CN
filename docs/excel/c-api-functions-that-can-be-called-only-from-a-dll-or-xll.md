---
title: 只能从 DLL 或 XLL 调用的 C API 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 函数 [excel 2007], c api 从 dll 或 xll 调用
localization_priority: Normal
ms.assetid: 87c9e75b-c364-4428-a169-010886313b85
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e6d2d3c824c482e3726cdaefa869393002a80f44
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301650"
---
# <a name="c-api-functions-that-can-be-called-only-from-a-dll-or-xll"></a><span data-ttu-id="d198a-104">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="d198a-104">C API Functions That Can Be Called Only from a DLL or XLL</span></span>

<span data-ttu-id="d198a-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d198a-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="d198a-106">C API 提供了15个 Microsoft Excel 回调函数, 只能通过使用**Excel4**、 **Excel4v**、 **Excel12**或**Excel12v**函数 (或通过使用框架函数 Excel 间接使用这些函数之一) 来调用\*\*\*\* 或**Excel12f**)。</span><span class="sxs-lookup"><span data-stu-id="d198a-106">The C API provides 15 Microsoft Excel callback functions that can only be called by using the **Excel4**, **Excel4v**, **Excel12**, or **Excel12v** functions (or by one of these functions indirectly using the Framework functions **Excel** or **Excel12f**).</span></span> <span data-ttu-id="d198a-107">这意味着只能从 DLL 或 XLL 调用它们。</span><span class="sxs-lookup"><span data-stu-id="d198a-107">This means they can only be called from a DLL or XLL.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="d198a-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="d198a-108">In this section</span></span>

[<span data-ttu-id="d198a-109">xlAbort</span><span class="sxs-lookup"><span data-stu-id="d198a-109">xlAbort</span></span>](xlabort.md)
  
[<span data-ttu-id="d198a-110">xlAsyncReturn</span><span class="sxs-lookup"><span data-stu-id="d198a-110">xlAsyncReturn</span></span>](xlasyncreturn.md)
  
[<span data-ttu-id="d198a-111">xlCoerce</span><span class="sxs-lookup"><span data-stu-id="d198a-111">xlCoerce</span></span>](xlcoerce.md)
  
[<span data-ttu-id="d198a-112">xlDefineBinaryName</span><span class="sxs-lookup"><span data-stu-id="d198a-112">xlDefineBinaryName</span></span>](xldefinebinaryname.md)
  
[<span data-ttu-id="d198a-113">xlDisableXLMsgs</span><span class="sxs-lookup"><span data-stu-id="d198a-113">xlDisableXLMsgs</span></span>](xldisablexlmsgs.md)
  
[<span data-ttu-id="d198a-114">xlEnableXLMsgs</span><span class="sxs-lookup"><span data-stu-id="d198a-114">xlEnableXLMsgs</span></span>](xlenablexlmsgs.md)
  
[<span data-ttu-id="d198a-115">xlEventRegister</span><span class="sxs-lookup"><span data-stu-id="d198a-115">xlEventRegister</span></span>](xleventregister.md)
  
[<span data-ttu-id="d198a-116">xlFree</span><span class="sxs-lookup"><span data-stu-id="d198a-116">xlFree</span></span>](xlfree.md)
  
[<span data-ttu-id="d198a-117">xlGetBinaryName</span><span class="sxs-lookup"><span data-stu-id="d198a-117">xlGetBinaryName</span></span>](xlgetbinaryname.md)
  
[<span data-ttu-id="d198a-118">xlGetHwnd</span><span class="sxs-lookup"><span data-stu-id="d198a-118">xlGetHwnd</span></span>](xlgethwnd.md)
  
[<span data-ttu-id="d198a-119">xlGetInst</span><span class="sxs-lookup"><span data-stu-id="d198a-119">xlGetInst</span></span>](xlgetinst.md)
  
[<span data-ttu-id="d198a-120">xlGetInstPtr</span><span class="sxs-lookup"><span data-stu-id="d198a-120">xlGetInstPtr</span></span>](xlgetinstptr.md)
  
[<span data-ttu-id="d198a-121">xlGetName</span><span class="sxs-lookup"><span data-stu-id="d198a-121">xlGetName</span></span>](xlgetname.md)
  
[<span data-ttu-id="d198a-122">xlRunningOnCluster</span><span class="sxs-lookup"><span data-stu-id="d198a-122">xlRunningOnCluster</span></span>](xlrunningoncluster.md)
  
[<span data-ttu-id="d198a-123">xlSet</span><span class="sxs-lookup"><span data-stu-id="d198a-123">xlSet</span></span>](xlset.md)
  
[<span data-ttu-id="d198a-124">xlSheetId</span><span class="sxs-lookup"><span data-stu-id="d198a-124">xlSheetId</span></span>](xlsheetid.md)
  
[<span data-ttu-id="d198a-125">xlSheetNm</span><span class="sxs-lookup"><span data-stu-id="d198a-125">xlSheetNm</span></span>](xlsheetnm.md)
  
[<span data-ttu-id="d198a-126">xlStack</span><span class="sxs-lookup"><span data-stu-id="d198a-126">xlStack</span></span>](xlstack.md)
  
[<span data-ttu-id="d198a-127">xlUDF</span><span class="sxs-lookup"><span data-stu-id="d198a-127">xlUDF</span></span>](xludf.md)
  
## <a name="see-also"></a><span data-ttu-id="d198a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d198a-128">See also</span></span>



[<span data-ttu-id="d198a-129">C API 回调函数 Excel4、Excel12</span><span class="sxs-lookup"><span data-stu-id="d198a-129">C API Callback Functions Excel4, Excel12</span></span>](c-api-callback-functions-excel4-excel12.md)

