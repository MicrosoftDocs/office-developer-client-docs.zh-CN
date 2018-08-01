---
title: 常量 (忙/闲 API)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: ff756bf1-9395-5e50-4f55-1eb0365a84ed
description: 本主题包含忙/闲 api 常量定义、 类标识符和界面标识符。
ms.openlocfilehash: ec909d449dc9075959fc9c047457577efd52ec3a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774178"
---
# <a name="constants-freebusy-api"></a><span data-ttu-id="43068-103">常量 (忙/闲 API)</span><span class="sxs-lookup"><span data-stu-id="43068-103">Constants (Free/busy API)</span></span>

<span data-ttu-id="43068-104">本主题包含忙/闲 api 常量定义、 类标识符和界面标识符。</span><span class="sxs-lookup"><span data-stu-id="43068-104">This topic contains constant definitions, class identifiers, and interface identifiers for the Free/Busy API.</span></span>
  
## <a name="constants"></a><span data-ttu-id="43068-105">常量</span><span class="sxs-lookup"><span data-stu-id="43068-105">Constants</span></span>

|<span data-ttu-id="43068-106">**常量**</span><span class="sxs-lookup"><span data-stu-id="43068-106">**Constant**</span></span>|<span data-ttu-id="43068-107">**定义**</span><span class="sxs-lookup"><span data-stu-id="43068-107">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="43068-108">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="43068-108">E_NOTIMPL</span></span>  <br/> | <span data-ttu-id="43068-109">*Microsoft Windows 软件开发工具包 (SDK) 标头文件 winerror.h 中定义。*</span><span class="sxs-lookup"><span data-stu-id="43068-109">*As defined in the Microsoft Windows Software Development Kit (SDK) header file winerror.h.*</span></span>  <br/> |
|<span data-ttu-id="43068-110">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="43068-110">E_OUTOFMEMORY</span></span>  <br/> | <span data-ttu-id="43068-111">*Windows SDK 标头文件 winerror.h 中定义。*</span><span class="sxs-lookup"><span data-stu-id="43068-111">*As defined in the Windows SDK header file winerror.h.*</span></span>  <br/> |
|<span data-ttu-id="43068-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="43068-112">S_FALSE</span></span>  <br/> | <span data-ttu-id="43068-113">*Windows SDK 标头文件 winerror.h 中定义。*</span><span class="sxs-lookup"><span data-stu-id="43068-113">*As defined in the Windows SDK header file winerror.h.*</span></span>  <br/> |
|<span data-ttu-id="43068-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="43068-114">S_OK</span></span>  <br/> | <span data-ttu-id="43068-115">*Windows SDK 标头文件 winerror.h 中定义。*</span><span class="sxs-lookup"><span data-stu-id="43068-115">*As defined in the Windows SDK header file winerror.h.*</span></span>  <br/> |
   
## <a name="interface-identifiers"></a><span data-ttu-id="43068-116">界面标识符</span><span class="sxs-lookup"><span data-stu-id="43068-116">Interface identifiers</span></span>

<span data-ttu-id="43068-117">以下接口标识符，假定其值与相关联的 GUID 的符号名称 Windows SDK 标头文件 guiddef.h 中定义的 DEFINE_GUID 宏。</span><span class="sxs-lookup"><span data-stu-id="43068-117">For the following interface identifiers, assume the DEFINE_GUID macro defined in the Windows SDK header file guiddef.h to associate the GUID symbolic name with its value.</span></span>
  
<span data-ttu-id="43068-118">{00067064-0000-0000-C000-000000000046}</span><span class="sxs-lookup"><span data-stu-id="43068-118">//{00067064-0000-0000-C000-000000000046}</span></span>
  
<span data-ttu-id="43068-119">DEFINE_GUID (IID_IEnumFBBlock，0x00067064 0x0、 0x0、 0xc0，0x0、 0x0、 0x0、 0x0、 0x0、 0x0、 0x46);</span><span class="sxs-lookup"><span data-stu-id="43068-119">DEFINE_GUID(IID_IEnumFBBlock, 0x00067064, 0x0, 0x0, 0xc0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x46);</span></span>
  
<span data-ttu-id="43068-120">{00067066-0000-0000-C000-000000000046}</span><span class="sxs-lookup"><span data-stu-id="43068-120">//{00067066-0000-0000-C000-000000000046}</span></span>
  
<span data-ttu-id="43068-121">DEFINE_GUID (IID_IFreeBusyData，0x00067066 0x0、 0x0、 0xc0，0x0、 0x0、 0x0、 0x0、 0x0、 0x0、 0x46);</span><span class="sxs-lookup"><span data-stu-id="43068-121">DEFINE_GUID(IID_IFreeBusyData, 0x00067066, 0x0, 0x0, 0xc0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x46);</span></span>
  
<span data-ttu-id="43068-122">{00067067-0000-0000-C000-000000000046}</span><span class="sxs-lookup"><span data-stu-id="43068-122">//{00067067-0000-0000-C000-000000000046}</span></span>
  
<span data-ttu-id="43068-123">DEFINE_GUID (IID_IFreeBusySupport，0x00067067 0x0、 0x0、 0xc0，0x0、 0x0、 0x0、 0x0、 0x0、 0x0、 0x46);</span><span class="sxs-lookup"><span data-stu-id="43068-123">DEFINE_GUID(IID_IFreeBusySupport, 0x00067067, 0x0, 0x0, 0xc0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x0, 0x46);</span></span>
  

