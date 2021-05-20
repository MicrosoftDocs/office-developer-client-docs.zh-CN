---
title: '常量 (忙/闲 API) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: ff756bf1-9395-5e50-4f55-1eb0365a84ed
description: 本主题包含常量定义、类标识符和忙/闲 API 的接口标识符。
ms.openlocfilehash: 13578617eaab45e7194d7a0d4d6995ef925e7f20
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431531"
---
# <a name="constants-freebusy-api"></a><span data-ttu-id="61ee6-103">常量 (忙/闲 API) </span><span class="sxs-lookup"><span data-stu-id="61ee6-103">Constants (Free/busy API)</span></span>

<span data-ttu-id="61ee6-104">本主题包含常量定义、类标识符和忙/闲 API 的接口标识符。</span><span class="sxs-lookup"><span data-stu-id="61ee6-104">This topic contains constant definitions, class identifiers, and interface identifiers for the Free/Busy API.</span></span>
  
## <a name="constants"></a><span data-ttu-id="61ee6-105">常量</span><span class="sxs-lookup"><span data-stu-id="61ee6-105">Constants</span></span>

|<span data-ttu-id="61ee6-106">**常量**</span><span class="sxs-lookup"><span data-stu-id="61ee6-106">**Constant**</span></span>|<span data-ttu-id="61ee6-107">**定义**</span><span class="sxs-lookup"><span data-stu-id="61ee6-107">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61ee6-108">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="61ee6-108">E_NOTIMPL</span></span>  <br/> | <span data-ttu-id="61ee6-109">*如 Microsoft Windows Software Development Kit (SDK) 头文件 winerror.h 中定义。*</span><span class="sxs-lookup"><span data-stu-id="61ee6-109">*As defined in the Microsoft Windows Software Development Kit (SDK) header file winerror.h.*</span></span>  <br/> |
|<span data-ttu-id="61ee6-110">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="61ee6-110">E_OUTOFMEMORY</span></span>  <br/> | <span data-ttu-id="61ee6-111">*如 Windows SDK 头文件 winerror.h 中的定义。*</span><span class="sxs-lookup"><span data-stu-id="61ee6-111">*As defined in the Windows SDK header file winerror.h.*</span></span>  <br/> |
|<span data-ttu-id="61ee6-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="61ee6-112">S_FALSE</span></span>  <br/> | <span data-ttu-id="61ee6-113">*如 Windows SDK 头文件 winerror.h 中的定义。*</span><span class="sxs-lookup"><span data-stu-id="61ee6-113">*As defined in the Windows SDK header file winerror.h.*</span></span>  <br/> |
|<span data-ttu-id="61ee6-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="61ee6-114">S_OK</span></span>  <br/> | <span data-ttu-id="61ee6-115">*如 Windows SDK 头文件 winerror.h 中的定义。*</span><span class="sxs-lookup"><span data-stu-id="61ee6-115">*As defined in the Windows SDK header file winerror.h.*</span></span>  <br/> |
   
## <a name="interface-identifiers"></a><span data-ttu-id="61ee6-116">接口标识符</span><span class="sxs-lookup"><span data-stu-id="61ee6-116">Interface identifiers</span></span>

<span data-ttu-id="61ee6-117">对于以下接口标识符，假定 DEFINE_GUID Windows SDK 头文件 guiddef.h 中定义的 DEFINE_GUID 宏将 GUID 符号名称与它的值关联。</span><span class="sxs-lookup"><span data-stu-id="61ee6-117">For the following interface identifiers, assume the DEFINE_GUID macro defined in the Windows SDK header file guiddef.h to associate the GUID symbolic name with its value.</span></span>
  
<span data-ttu-id="61ee6-118">{00067064-0000-0000-C000-000000000046}</span><span class="sxs-lookup"><span data-stu-id="61ee6-118">//{00067064-0000-0000-C000-000000000046}</span></span>
  
<span data-ttu-id="61ee6-119">DEFINE_GUID (IID_IEnumFBBlock、0x00067064、0x0、0x0、0xc0、0x0、0x0、0x0、0x0、0x0、0x0、0x46) ;</span><span class="sxs-lookup"><span data-stu-id="61ee6-119">DEFINE_GUID(IID_IEnumFBBlock, 0x00067064, 0x0, 0x0, 0xc0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x46);</span></span>
  
<span data-ttu-id="61ee6-120">{00067066-0000-0000-C000-000000000046}</span><span class="sxs-lookup"><span data-stu-id="61ee6-120">//{00067066-0000-0000-C000-000000000046}</span></span>
  
<span data-ttu-id="61ee6-121">DEFINE_GUID (IID_IFreeBusyData、0x00067066、0x0、0x0、0xc0、0x0、0x0、0x0、0x0、0x0、0x0、0x46) ;</span><span class="sxs-lookup"><span data-stu-id="61ee6-121">DEFINE_GUID(IID_IFreeBusyData, 0x00067066, 0x0, 0x0, 0xc0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x46);</span></span>
  
<span data-ttu-id="61ee6-122">{00067067-0000-0000-C000-000000000046}</span><span class="sxs-lookup"><span data-stu-id="61ee6-122">//{00067067-0000-0000-C000-000000000046}</span></span>
  
<span data-ttu-id="61ee6-123">DEFINE_GUID (IID_IFreeBusySupport、0x00067067、0x0、0x0、0xc0、0x0、0x0、0x0、0x0、0x0、0x0、0x46) ;</span><span class="sxs-lookup"><span data-stu-id="61ee6-123">DEFINE_GUID(IID_IFreeBusySupport, 0x00067067, 0x0, 0x0, 0xc0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x46);</span></span>
  

