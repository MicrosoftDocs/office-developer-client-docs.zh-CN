---
title: ISocialProviderGetCapabilities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f40d5405-12e3-475b-b731-d2223ab70c1d
description: 获取描述提供程序功能的字符串。
ms.openlocfilehash: cf3d1418ac0ecbfc3f67bb550a24ec71781f2637
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285761"
---
# <a name="isocialprovidergetcapabilities"></a><span data-ttu-id="4fb89-103">ISocialProvider::GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="4fb89-103">ISocialProvider::GetCapabilities</span></span>

<span data-ttu-id="4fb89-104">获取描述提供程序功能的字符串。</span><span class="sxs-lookup"><span data-stu-id="4fb89-104">Gets a string that describes provider capabilities.</span></span>
  
```cpp
HRESULT _stdcall GetCapabilities([out, retval] BSTR* result);
```

## <a name="parameters"></a><span data-ttu-id="4fb89-105">参数</span><span class="sxs-lookup"><span data-stu-id="4fb89-105">Parameters</span></span>

<span data-ttu-id="4fb89-106">_result_</span><span class="sxs-lookup"><span data-stu-id="4fb89-106">_result_</span></span>
  
> <span data-ttu-id="4fb89-107">排除一个代表 Outlook Social Connector (.osc) 提供程序的功能的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="4fb89-107">[out] An XML string that represents the capabilities of an Outlook Social Connector (OSC) provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4fb89-108">注解</span><span class="sxs-lookup"><span data-stu-id="4fb89-108">Remarks</span></span>

<span data-ttu-id="4fb89-109">返回的_结果_XML 字符串必须符合 "**功能**" 元素的架构定义 (如在用于 .osc 提供程序扩展性的 XML 架构中定义)。</span><span class="sxs-lookup"><span data-stu-id="4fb89-109">The returned  _result_ XML string must comply with the schema definition for the **capabilities** element, as defined in the XML schema for OSC provider extensibility.</span></span> 
  
<span data-ttu-id="4fb89-110">提供程序必须返回_结果_字符串, 才能使来自 .osc 的后续调用能够正常运行。</span><span class="sxs-lookup"><span data-stu-id="4fb89-110">The provider must return a  _result_ string to enable subsequent calls from the OSC to the provider to operate correctly.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4fb89-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fb89-111">See also</span></span>

- [<span data-ttu-id="4fb89-112">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4fb89-112">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

