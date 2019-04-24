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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b76c55fd9ddc3aa7698f75aa6ce965544b2c9aae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317435"
---
# <a name="imscapabilitiesgetcapabilities"></a><span data-ttu-id="50331-103">IMSCapabilities::GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="50331-103">IMSCapabilities::GetCapabilities</span></span>

  
  
<span data-ttu-id="50331-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="50331-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="50331-105">根据指定的选择器获取有关存储区可支持的内容的信息。</span><span class="sxs-lookup"><span data-stu-id="50331-105">Gets information about what a store can support based on the specified selector.</span></span>
  
```cpp
ULONG GetCapabilities( 
MSCAP_SELECTOR mscapSelector 
);
```

## <a name="parameters"></a><span data-ttu-id="50331-106">参数</span><span class="sxs-lookup"><span data-stu-id="50331-106">Parameters</span></span>

 <span data-ttu-id="50331-107">*mscapSelector*</span><span class="sxs-lookup"><span data-stu-id="50331-107">*mscapSelector*</span></span> 
  
> <span data-ttu-id="50331-108">实时指示要返回的功能的选择器。</span><span class="sxs-lookup"><span data-stu-id="50331-108">[in] Selector indicating which capabilities to return.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="50331-109">返回值</span><span class="sxs-lookup"><span data-stu-id="50331-109">Return value</span></span>

<span data-ttu-id="50331-110">MSCAP_SECURE_FOLDER_HOMEPAGES</span><span class="sxs-lookup"><span data-stu-id="50331-110">MSCAP_SECURE_FOLDER_HOMEPAGES</span></span>
  
> <span data-ttu-id="50331-111">对非默认存储区中的文件夹主页的支持。</span><span class="sxs-lookup"><span data-stu-id="50331-111">Support for folder homepages in a non-default store.</span></span> <span data-ttu-id="50331-112">如果在*mscapSelector*中指定了**MSCAP_SEL_FOLDER** , 则可以返回此项。</span><span class="sxs-lookup"><span data-stu-id="50331-112">This can be returned if **MSCAP_SEL_FOLDER** is specified in  *mscapSelector*  .</span></span> 
    
<span data-ttu-id="50331-113">MSCAP_RES_ANNOTATION</span><span class="sxs-lookup"><span data-stu-id="50331-113">MSCAP_RES_ANNOTATION</span></span>
  
> <span data-ttu-id="50331-114">如果限制包含任何无效参数 (如无效属性), 则存储将忽略无效参数, 并仅处理有效参数。</span><span class="sxs-lookup"><span data-stu-id="50331-114">If a restriction contains any invalid arguments such as invalid properties, the store ignores the invalid arguments and processes only the valid arguments.</span></span> <span data-ttu-id="50331-115">如果在*mscapSelector*中指定了**MSCAP_SEL_RESTRICTION** , 则可以返回此项。</span><span class="sxs-lookup"><span data-stu-id="50331-115">This can be returned if **MSCAP_SEL_RESTRICTION** is specified in  *mscapSelector*  .</span></span> 
    
<span data-ttu-id="50331-116">不适</span><span class="sxs-lookup"><span data-stu-id="50331-116">NULL</span></span>
  
> <span data-ttu-id="50331-117">存储区不支持基于给定选择器的任何功能。</span><span class="sxs-lookup"><span data-stu-id="50331-117">The store does not support any capability based on the given selector.</span></span>
    

