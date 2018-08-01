---
title: IMSCapabilitiesGetCapabilities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSCapabilities.GetCapabilities
api_type:
- COM
ms.assetid: c77a8ef1-0730-d458-b35f-451d3f450fac
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 27db5f54f6a6feba77308a4a63fe4c16448550cb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775855"
---
# <a name="imscapabilitiesgetcapabilities"></a><span data-ttu-id="3fbfa-103">IMSCapabilities::GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="3fbfa-103">IMSCapabilities::GetCapabilities</span></span>

  
  
<span data-ttu-id="3fbfa-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3fbfa-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3fbfa-105">获取有关存储可支持信息基于指定的选择器。</span><span class="sxs-lookup"><span data-stu-id="3fbfa-105">Gets information about what a store can support based on the specified selector.</span></span>
  
```cpp
ULONG GetCapabilities( 
MSCAP_SELECTOR mscapSelector 
);
```

## <a name="parameters"></a><span data-ttu-id="3fbfa-106">参数</span><span class="sxs-lookup"><span data-stu-id="3fbfa-106">Parameters</span></span>

 <span data-ttu-id="3fbfa-107">*mscapSelector*</span><span class="sxs-lookup"><span data-stu-id="3fbfa-107">*mscapSelector*</span></span> 
  
> <span data-ttu-id="3fbfa-108">[in]指示要返回哪些功能的选择器。</span><span class="sxs-lookup"><span data-stu-id="3fbfa-108">[in] Selector indicating which capabilities to return.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3fbfa-109">返回值</span><span class="sxs-lookup"><span data-stu-id="3fbfa-109">Return value</span></span>

<span data-ttu-id="3fbfa-110">MSCAP_SECURE_FOLDER_HOMEPAGES</span><span class="sxs-lookup"><span data-stu-id="3fbfa-110">MSCAP_SECURE_FOLDER_HOMEPAGES</span></span>
  
> <span data-ttu-id="3fbfa-111">支持的非默认存储区中的文件夹主页。</span><span class="sxs-lookup"><span data-stu-id="3fbfa-111">Support for folder homepages in a non-default store.</span></span> <span data-ttu-id="3fbfa-112">这可以返回如果**MSCAP_SEL_FOLDER** *mscapSelector*中指定。</span><span class="sxs-lookup"><span data-stu-id="3fbfa-112">This can be returned if **MSCAP_SEL_FOLDER** is specified in  *mscapSelector*  .</span></span> 
    
<span data-ttu-id="3fbfa-113">MSCAP_RES_ANNOTATION</span><span class="sxs-lookup"><span data-stu-id="3fbfa-113">MSCAP_RES_ANNOTATION</span></span>
  
> <span data-ttu-id="3fbfa-114">如果限制包含任何无效的参数，例如无效的属性，存储将忽略参数无效，处理仅的有效参数。</span><span class="sxs-lookup"><span data-stu-id="3fbfa-114">If a restriction contains any invalid arguments such as invalid properties, the store ignores the invalid arguments and processes only the valid arguments.</span></span> <span data-ttu-id="3fbfa-115">这可以返回如果**MSCAP_SEL_RESTRICTION** *mscapSelector*中指定。</span><span class="sxs-lookup"><span data-stu-id="3fbfa-115">This can be returned if **MSCAP_SEL_RESTRICTION** is specified in  *mscapSelector*  .</span></span> 
    
<span data-ttu-id="3fbfa-116">NULL</span><span class="sxs-lookup"><span data-stu-id="3fbfa-116">NULL</span></span>
  
> <span data-ttu-id="3fbfa-117">存储不支持基于给定的选择器任何功能。</span><span class="sxs-lookup"><span data-stu-id="3fbfa-117">The store does not support any capability based on the given selector.</span></span>
    

