---
title: 常量 (忙/闲 API)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: ff756bf1-9395-5e50-4f55-1eb0365a84ed
description: 本主题包含常量定义、类标识符和用于闲/忙 API 的接口标识符。
ms.openlocfilehash: 13578617eaab45e7194d7a0d4d6995ef925e7f20
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317715"
---
# <a name="constants-freebusy-api"></a><span data-ttu-id="89acb-103">常量 (忙/闲 API)</span><span class="sxs-lookup"><span data-stu-id="89acb-103">Constants (Free/busy API)</span></span>

<span data-ttu-id="89acb-104">本主题包含常量定义、类标识符和用于闲/忙 API 的接口标识符。</span><span class="sxs-lookup"><span data-stu-id="89acb-104">This topic contains constant definitions, class identifiers, and interface identifiers for the Free/Busy API.</span></span>
  
## <a name="constants"></a><span data-ttu-id="89acb-105">常量</span><span class="sxs-lookup"><span data-stu-id="89acb-105">Constants</span></span>

|<span data-ttu-id="89acb-106">**常量**</span><span class="sxs-lookup"><span data-stu-id="89acb-106">**Constant**</span></span>|<span data-ttu-id="89acb-107">**定义**</span><span class="sxs-lookup"><span data-stu-id="89acb-107">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89acb-108">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="89acb-108">E_NOTIMPL</span></span>  <br/> | <span data-ttu-id="89acb-109">*如 Microsoft Windows 软件开发工具包 (SDK) 头文件 winerror.h 中所定义。*</span><span class="sxs-lookup"><span data-stu-id="89acb-109">*As defined in the Microsoft Windows Software Development Kit (SDK) header file winerror.h.*</span></span>  <br/> |
|<span data-ttu-id="89acb-110">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="89acb-110">E_OUTOFMEMORY</span></span>  <br/> | <span data-ttu-id="89acb-111">*如 Windows SDK 头文件 winerror.h 中所定义。*</span><span class="sxs-lookup"><span data-stu-id="89acb-111">*As defined in the Windows SDK header file winerror.h.*</span></span>  <br/> |
|<span data-ttu-id="89acb-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="89acb-112">S_FALSE</span></span>  <br/> | <span data-ttu-id="89acb-113">*如 Windows SDK 头文件 winerror.h 中所定义。*</span><span class="sxs-lookup"><span data-stu-id="89acb-113">*As defined in the Windows SDK header file winerror.h.*</span></span>  <br/> |
|<span data-ttu-id="89acb-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="89acb-114">S_OK</span></span>  <br/> | <span data-ttu-id="89acb-115">*如 Windows SDK 头文件 winerror.h 中所定义。*</span><span class="sxs-lookup"><span data-stu-id="89acb-115">*As defined in the Windows SDK header file winerror.h.*</span></span>  <br/> |
   
## <a name="interface-identifiers"></a><span data-ttu-id="89acb-116">接口标识符</span><span class="sxs-lookup"><span data-stu-id="89acb-116">Interface identifiers</span></span>

<span data-ttu-id="89acb-117">对于下列接口标识符, 假定在 Windows SDK 头文件 guiddef.h 中定义的 DEFINE_GUID 宏将 GUID 符号名称与它的值关联。</span><span class="sxs-lookup"><span data-stu-id="89acb-117">For the following interface identifiers, assume the DEFINE_GUID macro defined in the Windows SDK header file guiddef.h to associate the GUID symbolic name with its value.</span></span>
  
<span data-ttu-id="89acb-118">{00067064-0000-0000-C000-000000000046}</span><span class="sxs-lookup"><span data-stu-id="89acb-118">//{00067064-0000-0000-C000-000000000046}</span></span>
  
<span data-ttu-id="89acb-119">DEFINE_GUID (IID_IEnumFBBlock、0x00067064、0x0、0x0、0xc0、0x0、0x0、0x0、0x0、0x0、0x0、0x46);</span><span class="sxs-lookup"><span data-stu-id="89acb-119">DEFINE_GUID(IID_IEnumFBBlock, 0x00067064, 0x0, 0x0, 0xc0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x46);</span></span>
  
<span data-ttu-id="89acb-120">{00067066-0000-0000-C000-000000000046}</span><span class="sxs-lookup"><span data-stu-id="89acb-120">//{00067066-0000-0000-C000-000000000046}</span></span>
  
<span data-ttu-id="89acb-121">DEFINE_GUID (IID_IFreeBusyData、0x00067066、0x0、0x0、0xc0、0x0、0x0、0x0、0x0、0x0、0x0、0x46);</span><span class="sxs-lookup"><span data-stu-id="89acb-121">DEFINE_GUID(IID_IFreeBusyData, 0x00067066, 0x0, 0x0, 0xc0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x46);</span></span>
  
<span data-ttu-id="89acb-122">{00067067-0000-0000-C000-000000000046}</span><span class="sxs-lookup"><span data-stu-id="89acb-122">//{00067067-0000-0000-C000-000000000046}</span></span>
  
<span data-ttu-id="89acb-123">DEFINE_GUID (IID_IFreeBusySupport、0x00067067、0x0、0x0、0xc0、0x0、0x0、0x0、0x0、0x0、0x0、0x46);</span><span class="sxs-lookup"><span data-stu-id="89acb-123">DEFINE_GUID(IID_IFreeBusySupport, 0x00067067, 0x0, 0x0, 0xc0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x46);</span></span>
  

