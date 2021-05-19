---
title: OutlookSocial Connector 提供程序错误代码
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0799243e-ba92-44c4-b687-182e50b57cb7
description: 提供程序应该使用下表中所示的错误代码之一将错误返回给调用方。
ms.openlocfilehash: 22a6e8d4ebf87157eaee630cc47f9f363150e839
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425349"
---
# <a name="outlook-social-connector-provider-error-codes"></a><span data-ttu-id="d1b72-103">OutlookSocial Connector 提供程序错误代码</span><span class="sxs-lookup"><span data-stu-id="d1b72-103">Outlook Social Connector provider error codes</span></span>

<span data-ttu-id="d1b72-104">提供程序应该使用下表中所示的错误代码之一将错误返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="d1b72-104">Providers should return errors to the caller by using one of the error codes shown in the following table.</span></span> 
  
|<span data-ttu-id="d1b72-105">**错误**</span><span class="sxs-lookup"><span data-stu-id="d1b72-105">**Error**</span></span>|<span data-ttu-id="d1b72-106">**错误代码 (十六进制)**</span><span class="sxs-lookup"><span data-stu-id="d1b72-106">**Error code (hexadecimal)**</span></span>|<span data-ttu-id="d1b72-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1b72-107">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d1b72-108">OSC_E_AUTH_ERROR</span><span class="sxs-lookup"><span data-stu-id="d1b72-108">OSC_E_AUTH_ERROR</span></span>  <br/> |<span data-ttu-id="d1b72-109">0x80041404</span><span class="sxs-lookup"><span data-stu-id="d1b72-109">0x80041404</span></span>  <br/> |<span data-ttu-id="d1b72-110">社交网络网站的网络身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="d1b72-110">Authentication failed on the network of the social network site.</span></span>  <br/> |
|<span data-ttu-id="d1b72-111">OSC_E_COULDNOTCONNECT</span><span class="sxs-lookup"><span data-stu-id="d1b72-111">OSC_E_COULDNOTCONNECT</span></span>  <br/> |<span data-ttu-id="d1b72-112">0x80041402</span><span class="sxs-lookup"><span data-stu-id="d1b72-112">0x80041402</span></span>  <br/> |<span data-ttu-id="d1b72-113">无法连接到社交网络网站。</span><span class="sxs-lookup"><span data-stu-id="d1b72-113">No connection is available to connect to the social network site.</span></span>  <br/> |
|<span data-ttu-id="d1b72-114">OSC_E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d1b72-114">OSC_E_FAIL</span></span>  <br/> |<span data-ttu-id="d1b72-115">0x80004005</span><span class="sxs-lookup"><span data-stu-id="d1b72-115">0x80004005</span></span>  <br/> |<span data-ttu-id="d1b72-116">常规失败错误。</span><span class="sxs-lookup"><span data-stu-id="d1b72-116">General failure error.</span></span>  <br/> |
|<span data-ttu-id="d1b72-117">OSC_E_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="d1b72-117">OSC_E_INTERNAL_ERROR</span></span>  <br/> |<span data-ttu-id="d1b72-118">0x80041400</span><span class="sxs-lookup"><span data-stu-id="d1b72-118">0x80041400</span></span>  <br/> |<span data-ttu-id="d1b72-119">由于操作无效而发生了内部错误。</span><span class="sxs-lookup"><span data-stu-id="d1b72-119">An internal error occurred because of an invalid operation.</span></span>  <br/> |
|<span data-ttu-id="d1b72-120">OSC_E_INVALIDARG (E_INVALIDARG) </span><span class="sxs-lookup"><span data-stu-id="d1b72-120">OSC_E_INVALIDARG (E_INVALIDARG)</span></span>  <br/> |<span data-ttu-id="d1b72-121">0x80070057</span><span class="sxs-lookup"><span data-stu-id="d1b72-121">0x80070057</span></span>  <br/> |<span data-ttu-id="d1b72-122">向函数传递了无效参数。</span><span class="sxs-lookup"><span data-stu-id="d1b72-122">An invalid argument was passed to a function.</span></span>  <br/> |
|<span data-ttu-id="d1b72-123">OSC_E_NO_CHANGES</span><span class="sxs-lookup"><span data-stu-id="d1b72-123">OSC_E_NO_CHANGES</span></span>  <br/> |<span data-ttu-id="d1b72-124">0x80041406</span><span class="sxs-lookup"><span data-stu-id="d1b72-124">0x80041406</span></span>  <br/> |<span data-ttu-id="d1b72-125">自上次同步以来未发生任何更改。</span><span class="sxs-lookup"><span data-stu-id="d1b72-125">No changes have occurred since the last synchronization.</span></span>  <br/> |
|<span data-ttu-id="d1b72-126">OSC_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="d1b72-126">OSC_E_NOT_FOUND</span></span>  <br/> |<span data-ttu-id="d1b72-127">0x80041405</span><span class="sxs-lookup"><span data-stu-id="d1b72-127">0x80041405</span></span>  <br/> |<span data-ttu-id="d1b72-128">找不到资源。</span><span class="sxs-lookup"><span data-stu-id="d1b72-128">A resource cannot be found.</span></span>  <br/> |
|<span data-ttu-id="d1b72-129">OSC_E_NOT_IMPLEMENTED (E_NOTIMPL) </span><span class="sxs-lookup"><span data-stu-id="d1b72-129">OSC_E_NOT_IMPLEMENTED (E_NOTIMPL)</span></span>  <br/> |<span data-ttu-id="d1b72-130">0x80004001</span><span class="sxs-lookup"><span data-stu-id="d1b72-130">0x80004001</span></span>  <br/> |<span data-ttu-id="d1b72-131">对社交网络网站的请求有效，但社交网络网站尚未实现。</span><span class="sxs-lookup"><span data-stu-id="d1b72-131">The request to the social network site is valid but has not been implemented by the social network site.</span></span>  <br/> |
|<span data-ttu-id="d1b72-132">OSC_E_OUT_OF_MEMORY (E_OUTOFMEMORY) </span><span class="sxs-lookup"><span data-stu-id="d1b72-132">OSC_E_OUT_OF_MEMORY (E_OUTOFMEMORY)</span></span>  <br/> |<span data-ttu-id="d1b72-133">0x8007000E</span><span class="sxs-lookup"><span data-stu-id="d1b72-133">0x8007000E</span></span>  <br/> |<span data-ttu-id="d1b72-134">发生内存不足错误。</span><span class="sxs-lookup"><span data-stu-id="d1b72-134">An out-of-memory error occurred.</span></span>  <br/> |
|<span data-ttu-id="d1b72-135">OSC_E_PERMISSION_DENIED</span><span class="sxs-lookup"><span data-stu-id="d1b72-135">OSC_E_PERMISSION_DENIED</span></span>  <br/> |<span data-ttu-id="d1b72-136">0x80041403</span><span class="sxs-lookup"><span data-stu-id="d1b72-136">0x80041403</span></span>  <br/> |<span data-ttu-id="d1b72-137">OSC 提供程序拒绝对资源的权限。</span><span class="sxs-lookup"><span data-stu-id="d1b72-137">The OSC provider denied permission for the resource.</span></span>  <br/> |
|<span data-ttu-id="d1b72-138">OSC_E_SERVER_VERSION_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="d1b72-138">OSC_E_SERVER_VERSION_NOT_SUPPORTED</span></span>  <br/> |<span data-ttu-id="d1b72-139">0x80041406</span><span class="sxs-lookup"><span data-stu-id="d1b72-139">0x80041406</span></span>  <br/> |<span data-ttu-id="d1b72-140">不支持用于配置社交网络帐户的服务器版本。</span><span class="sxs-lookup"><span data-stu-id="d1b72-140">The version of the server to configure the social network account is not supported.</span></span>  <br/> |
|<span data-ttu-id="d1b72-141">OSC_E_VERSION</span><span class="sxs-lookup"><span data-stu-id="d1b72-141">OSC_E_VERSION</span></span>  <br/> |<span data-ttu-id="d1b72-142">0x80041401</span><span class="sxs-lookup"><span data-stu-id="d1b72-142">0x80041401</span></span>  <br/> |<span data-ttu-id="d1b72-143">提供程序不支持此版本的 OSC 提供程序扩展性。</span><span class="sxs-lookup"><span data-stu-id="d1b72-143">The provider does not support this version of OSC provider extensibility.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d1b72-144">备注</span><span class="sxs-lookup"><span data-stu-id="d1b72-144">Remarks</span></span>

<span data-ttu-id="d1b72-145">通过使用称为结果句柄的 32 位数字或 **HRESULT** 返回成功、警告和错误值。</span><span class="sxs-lookup"><span data-stu-id="d1b72-145">Success, warning, and error values are returned by using a 32-bit number that is called a result handle, or **HRESULT**.</span></span> <span data-ttu-id="d1b72-146">**HRESULT** 不是任何句柄;它只是一个 32 位值，该值中已编码多个字段。</span><span class="sxs-lookup"><span data-stu-id="d1b72-146">An **HRESULT** is not a handle to anything; it is merely a 32-bit value that has several fields encoded in the value.</span></span> <span data-ttu-id="d1b72-147">正结果表示状态成功，零结果表示成功，状态 (S_OK) ，负结果表示失败。</span><span class="sxs-lookup"><span data-stu-id="d1b72-147">A positive result indicates success with status, a zero result indicates success without status (S_OK), and a negative result indicates failure.</span></span> 
  

